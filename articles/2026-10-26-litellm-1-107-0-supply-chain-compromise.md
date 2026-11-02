# LiteLLM 1.107.0がPyPI・Dockerで侵害、認証情報窃取マルウェアとRATを配布

- **日付**: 2026-10-26
- **出典**: [LiteLLM公式インシデントレポート / The Hacker News](https://docs.litellm.ai/blog/security-incident-oct-21-2026)
- **トピック**: [LiteLLM 1.107.0 サプライチェーン侵害（2026年10月）](../topics/litellm-1-107-0-supply-chain-compromise-2026.md)
- **分類**: 関連

## 概要

AIゲートウェイLiteLLMのバージョン1.107.0が2026年10月21日にPyPIとDockerイメージで侵害され、Python起動時に動く認証情報窃取マルウェアとRATが含まれていた。エンジニア3名のGitHubアカウント経由（OAuthトークン窃取とみられる）で公開されたとされる。

## 詳細

## 概要

LiteLLMの公式報告によると、PyPIのv1.107.0 wheelは2026-10-21 11:39〜13:23 UTC、Dockerイメージ（v1.107.0／latest／main-latest／main-stable）は11:46〜14:20 UTCの間、悪意あるものに差し替えられていた。SafeDep、Socket、StepSecurity、Upwindなど複数社が、クラウド・開発者・AIツール・ブラウザ・LiteLLM proxyの認証情報を狙うインフォスティーラーと、第二段階のRAT（バックドア）を確認している。

## 侵入経路

エンジニア3名のGitHubアカウントが使われ、GitHub CLIのOAuthトークンが盗まれたとみられるが、最初の侵入点は未確認で調査中。公開されたマスターキーが失効されておらずリリースパイプラインへのアクセスを許したとの報道もある。

## 対応

- 旧バージョンは安全、該当リリースは取り下げ済み。エンタープライズ版は影響なし。
- 当該期間にインストール／コンテナ実行した環境は侵害されたものとみなし、隔離・クリーンイメージでの再構築・到達可能な全認証情報のローテーションが必要。
- 今年2度目のLiteLLM侵害（前回1.82.7／1.82.8はTeamPCP関連）。両者の関連は未確認。

AIゲートウェイはWeb・モバイルアプリのバックエンドでLLM呼び出しを仲介するため、APIキー漏えいの波及が大きい。

出典: https://docs.litellm.ai/blog/security-incident-oct-21-2026 , https://thehackernews.com/2026/10/litellm-compromised-in-supply-chain.html , https://securitylabs.datadoghq.com/articles/litellm-compromised-pypi-docker/

---

## 関連記事

- [LiteLLM・TeamPCP認証情報漏えい](../articles/2026-08-13-litellm-teampcp-credential-leak-153gb.md) - 過去のLiteLLM侵害（TeamPCP）
- [LiteLLM脆弱性チェーン](../articles/2026-06-16-litellm-ai-gateway-vulnerability-chain.md) - 同一製品の脆弱性
