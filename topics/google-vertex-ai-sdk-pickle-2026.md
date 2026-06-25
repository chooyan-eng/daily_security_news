# Google Vertex AI SDK バケット乗っ取り脆弱性「Pickle in the Middle」（2026年）

## 概要

Palo Alto Networks Unit 42 が発見し「Pickle in the Middle」と命名した Google Cloud Vertex AI SDK for Python の脆弱性（2026年3〜4月修正済み）。攻撃者は被害者のプロジェクト ID（多くの場合公開済み）を利用してモデルアップロード先 Cloud Storage バケット名を予測・先取りし（バケット乗っ取り）、ML モデルを悪意あるものに差し替えることで Google のサービスインフラ上での RCE が可能だった。

**同一性の判断に役立つ情報：**
- 脆弱性名: Pickle in the Middle（通称）
- 発見者: Palo Alto Networks Unit 42
- 影響製品: google-cloud-aiplatform（Vertex AI SDK for Python）v1.144.0 未満
- 攻撃手法: バケット乗っ取り（Bucket Squatting）
- 悪用方法: 被害者のプロジェクト ID のみで実行可能（認証不要）
- 修正バージョン: v1.144.0（部分修正、2026年3月31日）、v1.148.0（完全修正、2026年4月15日）
- CVE: 未発行

## タイムライン

- [2026-06-20 Google Vertex AI SDK「Pickle in the Middle」：バケット乗っ取りでAIモデル汚染とRCEが可能](../articles/2026-06-20-google-vertex-ai-sdk-pickle-in-the-middle.md)
