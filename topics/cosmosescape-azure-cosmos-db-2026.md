# CosmosEscape：Azure Cosmos DB プラットフォーム全体の乗っ取り脆弱性

## 概要

Wizが発見したAzure Cosmos DBのGremlin APIにおける重大脆弱性「CosmosEscape」。カスタムGremlinクエリエンジンの.NETリフレクション制限不備を突くことで、プラットフォーム全体の「Cosmos Master Key」を取得し、任意のCosmos DBアカウント（Microsoft内部システム含む）への完全な読み書きアクセスが可能だった。2025年11月報告、2026年7月に恒久修正完了。

**同一性の判断に役立つ情報：**
- 通称: CosmosEscape
- 発見者: Wiz
- 対象製品: Microsoft Azure Cosmos DB（Gremlin API）
- 報告日: 2025年11月／恒久修正完了: 2026年7月
- 影響: プラットフォーム全体のマスターキー取得によるクロステナント攻撃の可能性（顧客影響の証跡なしとMicrosoftは表明）
- 脆弱性名: CosmosEscape
- 発見者: Wiz Research
- 報告日: 2025年11月20日／恒久対策完了: 2026年7月
- 悪用の証拠: Microsoftの調査では開示前の悪意ある悪用は未確認

## タイムライン

- [2026-08-01 「CosmosEscape」— Azure Cosmos DB のGremlin API経由でプラットフォーム全体の乗っ取りが可能だった脆弱性チェーン（Wiz Research）](../articles/2026-08-01-cosmosescape-azure-cosmosdb.md)
- [2026-07-30 「CosmosEscape」— Azure Cosmos DB のほぼ全データベースを乗っ取り可能だった重大脆弱性、Wiz が詳細公開](../articles/2026-07-31-cosmosescape-azure-cosmos-db.md)
