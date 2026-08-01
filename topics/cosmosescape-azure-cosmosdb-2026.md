# CosmosEscape — Azure Cosmos DB 脆弱性チェーン（2026年）

## 概要

Wiz Researchが発見した、Microsoft Azure Cosmos DBのGremlin APIを起点とするサンドボックス脱出・テナント横断アクセス脆弱性チェーン「CosmosEscape」。攻撃者が管理するGremlinデータベースへの細工クエリからマルチテナントゲートウェイ上でコード実行を達成し、プラットフォーム全体の署名シークレット（Cosmosマスターキー）を取得することで、任意のCosmos DBアカウントに対する完全な読み書きアクセスとテナント横断的なデータベース列挙が可能だった。2025年11月20日にWizがMicrosoftへ報告し、48時間以内に暫定対策、2026年7月に恒久対策（マスターキー概念自体の撤廃）を全リージョンで完了。

**同一性の判断に役立つ情報：**
- 脆弱性名: CosmosEscape
- 対象製品: Microsoft Azure Cosmos DB（Gremlin API）
- 発見者: Wiz Research
- 報告日: 2025年11月20日／恒久対策完了: 2026年7月
- 悪用の証拠: Microsoftの調査では開示前の悪意ある悪用は未確認

## タイムライン

- [2026-08-01 「CosmosEscape」— Azure Cosmos DB のGremlin API経由でプラットフォーム全体の乗っ取りが可能だった脆弱性チェーン（Wiz Research）](../articles/2026-08-01-cosmosescape-azure-cosmosdb.md)
