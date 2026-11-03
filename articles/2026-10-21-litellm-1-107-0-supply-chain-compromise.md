# LiteLLM 1.107.0が窃取されたGitHubトークン経由で汚染、PyPI・Dockerで約2時間配布

- **日付**: 2026-10-21
- **出典**: [Datadog Security Labs](https://securitylabs.datadoghq.com/articles/litellm-compromised-pypi-docker/) / [Rescana](https://www.rescana.com/post/litellm-1-107-0-supply-chain-compromise-october-2026) / [RuntimeWire](https://runtimewire.com/article/berriai-stolen-github-tokens-apparently-used-to-publish-compromised-litellm-1-10)
- **トピック**: [LiteLLM AIゲートウェイ脆弱性チェーン](../topics/litellm-ai-gateway-vulnerabilities.md)
- **分類**: 関連

## 概要

AIゲートウェイ「LiteLLM」のバージョン1.107.0が、PyPIと公式Dockerイメージで約2時間にわたり悪意あるコード入りで配布された。BerriAIによると、エンジニア3名のGitHub CLI OAuthトークンが盗まれ、リリースワークフローが悪用されたとみられる。

## 詳細

- 配布内容: Python起動時に動作する認証情報窃取コードと、第二段のRATバックドア。Datadogによれば、クラウド、開発者、AIツール、ブラウザ、LiteLLMプロキシの認証情報が標的。
- 侵入経路: 窃取したGitHubトークンで非公開のリリースワークフローを起動し、正規パイプラインを名称の似た偽フォークに対して実行したとされる。3人目のアカウントでリリース後にワークフロー実行履歴が削除された。トークン窃取の原因は1件で推定ベクタが判明しているのみで、全容は未確定。
- 2026年内で2回目のLiteLLM供給網侵害。3月のv1.82.7／1.82.8（TeamPCP関連）との関連は現時点で確認されていない。
- 対策: 1.107.0をインストール・起動した環境は侵害前提で隔離・クリーンイメージから再構築し、到達可能な全認証情報をローテーション。CI/CDではGitHub CLIトークンの権限最小化と有効期限短縮、ワークフロー実行元の検証を徹底する。
- 注: 一部で「LiteLLMのマスターキー漏えいでGitHubトークンが盗まれた」との見出しもあるが、裏付けは確認できなかった。

---

## 関連記事

- [LiteLLM・TeamPCP サプライチェーン攻撃の続報](../articles/2026-08-18-litellm-supply-chain-teampcp-followup.md) - 同プロジェクトに対する過去の供給網侵害
