# Microsoft公式の「agent-framework」PyPIパッケージが侵害、.pth起動フックで認証情報を窃取する1.26.1／1.26.2が公開

- **日付**: 2026-11-18
- **出典**: [Socket](https://socket.dev/blog/agent-framework-pypi-package-compromised-with-credential-stealer), [Wiz](https://www.wiz.io/blog/malicious-version-of-microsofts-agent-framework-published-to-pypi), [JFrog Security Research](https://research.jfrog.com/post/agent-framework-hijack/), [StepSecurity](https://www.stepsecurity.io/blog/microsoft-agent-framework-pypi-package-compromised), [SecurityWeek](https://www.securityweek.com/microsoft-agent-framework-releases-poisoned-with-credential-stealer/)
- **トピック**: [Microsoft agent-framework PyPIパッケージ侵害（2026年11月）](../topics/microsoft-agent-framework-pypi-compromise-2026.md)
- **分類**: 新規

## 概要

11月17日、Microsoft Agent FrameworkのPythonパッケージ「agent-framework」に、認証情報窃取コードを含む1.26.1と1.26.2が約33分間隔でPyPIへ公開された。.pthファイルによりimportしなくてもPython起動のたびに実行され、Azure・Git・Docker・npm等の認証情報を狙う。両版は隔離済みで、1.26.0が最後の正常版。

## 詳細

### 概要

- 1.26.1は11月17日20:35 UTC頃（Wiz）、1.26.2はその約33分後に公開。PyPIが1.26.1を隔離した後に1.26.2が続いた。現在は両方とも隔離済み。
- パッケージのダウンロード数は月間約19万（JFrogは週間約4万としている）。

### 仕組み

悪性版はインストール時にsite-packagesへ`.pth`ファイルを配置する。Pythonはインタプリタ起動時にsite-packages内の`.pth`を処理し、`import`で始まる行を実行するため、agent-frameworkを一度もimportしなくても、その環境でPythonが起動するたびに窃取コードが動く。

### 窃取対象

- Azure CLIのデータ、Azure DevOpsエージェントの認証情報
- npm／pipの設定、Git認証情報ストア、Docker認証設定
- Hugging Faceトークン、アプリケーションの`.env`ファイル
- Ostorlabによれば256KiB未満の認証情報ファイルを最大80個読み取る。SafeDepによれば、CI上ではAzureやGitHubのOIDCトークンの発行も試みる

### 侵入経路（未確定）

各社の見解が分かれている。JFrogは、Microsoftのビルドパイプラインが侵害されたのではなく、正規wheelをローカルで再パッケージして公開したものと分析。StepSecurityとSafeDepは同日に作成されたメンテナーアカウント経由の公開を指摘し、OpenSourceMalwareはMicrosoft関連のPyPIパブリッシャー経由と述べている。攻撃者の帰属も不明。検索した範囲ではMicrosoftの公式声明は確認できなかった。StepSecurityは、公開に使われた認証情報やアカウントが失効されるまでは再発しうると警告している。

### 対応

- 1.26.0へ戻す（もしくは固定する）。
- 1.26.1／1.26.2を導入した環境は侵害されたものとして扱い、パッケージ削除だけでなくsite-packagesに残る`.pth`の除去、その環境から到達可能だった全認証情報（Azure、GitHub、npm、Docker、HFトークン、.env内のシークレット）のローテーションを行う。
- CI/CDランナーで導入された場合は、当該ジョブで利用可能だったOIDC連携先やシークレットも対象に含める。

### 技術的な補足

`.pth`起動フックは、importを伴わずに常駐的な実行を得られるため、パッケージを削除しても`.pth`が残れば実行が続く点に注意が必要である。バージョン範囲指定（`>=`）や未固定の依存はこの種の攻撃に弱く、ハッシュ付きロックファイル（`pip --require-hashes`、uv.lock等）による固定、公開直後のバージョンを一定期間取り込まないクールダウン設定、CIでのネットワーク送信先制限が有効な緩和策となる。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事
