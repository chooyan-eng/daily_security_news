# Microsoft公式「agent-framework」PyPIパッケージが乗っ取られ、1.26.1／1.26.2に認証情報窃取コード

- **日付**: 2026-11-22
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/11/19/microsoft-agent-framework-package-pypi-compromised/)
- **トピック**: [Microsoft agent-framework PyPIパッケージ侵害（2026年11月）](../topics/agent-framework-pypi-compromise-2026.md)
- **分類**: 新規

## 概要

MicrosoftのAIエージェント開発用Pythonパッケージ「agent-framework」の不正なバージョン1.26.1と1.26.2が11月17日にPyPIへ公開された。.pthファイルによる起動フックでPython起動のたびに実行され、Azure ID、CI/CDトークン、AI関連のシークレットを窃取する。1.26.0が最後の正常版。

## 詳細

複数のセキュリティベンダーの報告によると、2026年11月17日、PyPI上のMicrosoft公式パッケージagent-framework（月間ダウンロード約19万件）に不正なバージョン1.26.1と1.26.2が約33分の間に相次いで公開され、21時20分（UTC）ごろまでに削除された。Elasticは1.26.1を20時41分（UTC）に検知したとしており、JFrogは最初のバージョンが隔離された後も攻撃者が1.26.2を公開できた点を指摘している。これは公開に使われた認証情報がその時点で失効していなかったことを示唆する（[出典: JFrog](https://research.jfrog.com/post/agent-framework-hijack/)、[Elastic Security Labs](https://www.elastic.co/security-labs/threat-command/we-caught-the-agent-framework-pypi-compromise-six-minutes-after-it-published)）。

仕組み: 不正リリースはPythonの.pthファイルを使った起動フックを仕込んでいた。site-packages内の.pthファイルにimportで始まる行があると、インタプリタ起動時に自動実行される。このためagent-frameworkをimportしなくても、同じ環境でPythonを起動するたびに窃取コードが動作する。窃取対象はAzureのID・認証情報、CI/CDトークン、AI開発関連のシークレット（各種LLM APIキー等）と報告されている（[出典: Orca Security](https://orca.security/resources/research/microsoft-agent-framework-pypi-supply-chain-attack-versions-1-26-1-and-1-26-2-steal-cloud-credentials/)）。

対応: 1.26.0が最後の正常版。1.26.1または1.26.2が開発端末やビルドエージェントに一度でも入った場合、そのホスト上の全シークレットが露出したものとして扱い、クラウド認証情報、CI/CDトークン、APIキーをローテーションする。パッケージを削除するだけでなく、site-packagesに不審な.pthファイルが残っていないか確認する。

技術的な補足: .pth起動フックは10月のLiteLLM 1.107.0侵害など近年のPyPI侵害で繰り返し使われている持続化手法であり、「importしていないから安全」という判断が成り立たない点が重要である。本件は依存バージョンを範囲指定（>=や~=）しているプロジェクトが公開から数十分の間にCIで自動取得してしまうリスクを改めて示した。対策は、(1) ハッシュ付きロックファイル（pip --require-hashes、uv.lock等）による固定、(2) 公開から一定期間経過したバージョンのみを取り込むクールダウン設定、(3) CIジョブのシークレットを最小権限・短命トークン（OIDCフェデレーション）にすること、(4) ビルド環境からの外向き通信制限、である。侵害の原因（メンテナのトークン窃取か、公開ワークフローの侵害か）は本稿作成時点で確認できていない。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事


