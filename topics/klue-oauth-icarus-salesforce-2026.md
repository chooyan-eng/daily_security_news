# Klue OAuth 侵害・Icarus による Salesforce データ窃取（2026年6月）

## 概要

市場インテリジェンスプラットフォーム Klue が2026年6月に OAuth 侵害を受け、新興脅威アクター「Icarus」が複数の顧客組織の Salesforce CRM データを窃取・恐喝するキャンペーンを展開。Klue のバックエンドシステムへの侵害を通じて OAuth トークンが窃取され、約24時間にわたり Salesforce に対して自動化された REST API クエリが実行された。Salesforce は Klue Battlecards インテグレーションを無効化して対応中。

**同一性の判断に役立つ情報：**
- 被害ベンダー: Klue（市場インテリジェンス・Battlecards プラットフォーム）
- 脅威アクター: Icarus（2026年4月28日以降活動の新興脅威グループ）
- 攻撃手法: SaaS インテグレーション経由の OAuth トークン窃取 → Salesforce CRM データ抽出
- 影響プラットフォーム: Salesforce CRM（Klue Battlecards 連携を使用する組織）
- 確認組織: Huntress、ReliaQuest 等

## タイムライン

- [2026-06-18 Klue OAuth 侵害で「Icarus」がSalesforce CRM データを複数組織から窃取・恐喝](../articles/2026-06-18-klue-oauth-icarus-salesforce.md)
