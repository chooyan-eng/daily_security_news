# CosmosEscape：Azure Cosmos DB プラットフォーム全体キー露出脆弱性（2026年）

## 概要

Wiz Researchが発見した、Microsoft Azure Cosmos DBのゲートウェイ層に存在した脆弱性「CosmosEscape」。悪用によりテナント境界を越えて全顧客のCosmos DBデータベースにアクセス可能なプラットフォーム全体のマスターキーを取得できた。2025年11月にWizがMicrosoftへ報告、同月中に暫定修正、2026年7月に恒久修正が全リージョンへ展開完了。詳細は2026年7月30日公表。

**同一性の判断に役立つ情報：**
- 発見者: Wiz Research
- 名称: CosmosEscape
- 対象: Microsoft Azure Cosmos DB ゲートウェイ層
- 脆弱性内容: クロステナントでのプラットフォーム共有マスターキー露出
- Wiz報告日: 2025年11月20日
- 暫定修正日: 2025年11月22日
- 恒久修正完了: 2026年7月（全リージョン）
- 詳細公表日: 2026年7月30日
- 対応要否: Microsoftは修正完了済みのため顧客側の追加対応不要と発表

## タイムライン

- [2026-07-30 「CosmosEscape」：Azure Cosmos DBのゲートウェイ脆弱性により全データベースへアクセス可能なマスターキーが露出](../articles/2026-08-02-cosmosescape-azure-cosmos-db.md)
