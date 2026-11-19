# Microsoft公式「agent-framework」PyPIパッケージが改ざん、1.26.1／1.26.2に認証情報窃取マルウェア

- **日付**: 2026-11-19
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/11/19/microsoft-agent-framework-package-pypi-compromised/)
- **トピック**: [Microsoft agent-framework PyPIパッケージ侵害（2026年11月）](../topics/agent-framework-pypi-compromise-2026.md)
- **分類**: 新規

## 概要

MicrosoftのAIエージェント開発用Pythonパッケージ「agent-framework」の1.26.1と1.26.2が11月17日に約33分間隔でPyPIへ公開され、クラウド／CI認証情報を盗むマルウェアが混入していた。.pthファイルを使うため、パッケージをimportしなくてもPython起動のたびに実行される。両版は隔離済みで、1.26.0が最後の正常版。

## 詳細

### タイムライン

- 2026年11月17日: 悪性の1.26.1が公開。PyPIが隔離した後に、攻撃者が1.26.2を公開（両者の間隔は約33分）。1.26.2も隔離
- 最後の正常版は1.26.0。`agent-framework-core` など22の関連パッケージは影響なしと報告されている
- 月間ダウンロード数は約19万2,000

### 動作

- wheelに `.pth` ファイルが追加され、site-packagesに配置される。Pythonはインタプリタ起動時に `.pth` 内の `import` 行を実行するため、agent-frameworkを一度もimportしなくても、`pip` を含む全てのPython起動でペイロードが走る
- クラウド（Azureなど）およびCI/CDの認証情報、環境変数、設定ファイルを収集し、webhook.site のエンドポイントへ送信する

### 原因（見解が分かれる）

- JFrog: 攻撃者は正規wheelを手元で再パッケージしており、Microsoftのビルドパイプライン自体の侵害ではないとみる
- 別の分析: プロジェクトの正規の公開用IDで公開されたとする
- 1.26.1の隔離後に1.26.2を公開できたことから、PyPIの公開用資格情報が有効なまま残っていたと考えられる。バージョン単位の隔離では資格情報は失効しない
- 本稿執筆時点でMicrosoftの公式声明は確認できていない

### 対応

- 該当版を入れたホスト／CIランナーは侵害済みとみなし、隔離してクリーンなベースから再構築する
- 1.26.0に固定する
- `pip uninstall` の前に、site-packages内の該当 `.pth` ファイルを手動で削除する（pipの起動自体がPythonを起動し、収集処理を再実行するため）
- 当該環境から到達できた全ての認証情報（クラウドキー、CIトークン、PyPI／npmトークン、LLM APIキー）をローテーションする

### 技術的な補足

- `.pth` を使う手口はPyPIのサプライチェーン攻撃で繰り返し使われている永続化手法で、「importしなければ安全」という前提を崩す。`pip install --require-hashes` とロックファイルによるハッシュ固定、公開から一定期間を置くクールダウン（最小リリース経過時間）の設定が有効。
- 公開側はPyPI Trusted Publishing（OIDC）へ移行し、長期有効なAPIトークンを廃止することで、資格情報窃取による不正公開を抑止できる。

参考: [Socket](https://socket.dev/blog/agent-framework-pypi-package-compromised-with-credential-stealer)、[StepSecurity](https://www.stepsecurity.io/blog/microsoft-agent-framework-pypi-package-compromised)、[JFrog](https://research.jfrog.com/post/agent-framework-hijack/)、[Wiz](https://www.wiz.io/blog/malicious-version-of-microsofts-agent-framework-published-to-pypi)

> 注: 本セッションでは外部サイト本文を直接取得できず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事


