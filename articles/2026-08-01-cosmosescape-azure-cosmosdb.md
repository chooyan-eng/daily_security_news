# 「CosmosEscape」— Azure Cosmos DB のGremlin API経由でプラットフォーム全体の乗っ取りが可能だった脆弱性チェーン（Wiz Research）

- **日付**: 2026-08-01
- **出典**: [Wiz Blog](https://www.wiz.io/blog/cosmosescape-taking-over-every-database-in-azure-cosmos-db) / [The Hacker News](https://thehackernews.com/2026/07/azure-cosmos-db-flaw-exposed-platform.html) / [SecurityWeek](https://www.securityweek.com/critical-flaw-led-to-azure-cosmos-db-pwnage/)
- **トピック**: [CosmosEscape — Azure Cosmos DB 脆弱性チェーン（2026年）](../topics/cosmosescape-azure-cosmosdb-2026.md)
- **分類**: 新規

## 概要

Wiz Researchは、Microsoft Azure Cosmos DBのGremlin APIを起点にサンドボックスを脱出し、テナントを跨いで任意のデータベースへ完全な読み書きアクセスを得られる脆弱性チェーン「CosmosEscape」を発見した。Microsoftは2026年7月に恒久対策を全リージョンで完了した。

## 詳細

攻撃チェーンは、攻撃者が管理するGremlinデータベースに対する細工クエリから開始する。ここからマルチテナントのゲートウェイ上でコード実行を達成し、プラットフォーム全体で共有される署名シークレットとリージョンのアカウントディレクトリへのアクセスを取得。これにより任意のターゲットを特定し、そのCosmos DBアカウントのプライマリキー（Cosmosマスターキー）を取得できた。

このマスターキーには2つの強力な能力があった。1つは「Takeover」——任意のCosmos DBアカウントのプライマリキーをオンデマンドで取得し、完全な読み書きアクセスを得ること。もう1つは「Enumeration」——サブスクリプションIDやテナントIDでフィルタしながらサービス上の全データベースを列挙できることである。

MicrosoftはEntra ID、Teams、Copilotなどの内部データストアにもCosmos DBを利用しているため、この脆弱性は理論上Microsoft自身のデータベースを含むサービス上の全データベースを危険にさらしていた。

Wizは2025年11月20日にMicrosoftへ報告し、Microsoftは同日中に受領を確認。48時間以内（11月22日）に脆弱なGremlin APIのエントリポイントを遮断する暫定的なホットフィックスを展開した。その後、より長期的なアーキテクチャ修正が進められ、2026年7月に全Azureリージョンでの恒久対応が完了。この対応により、Cosmos DBのアーキテクチャからマスターキーという概念自体が撤廃された。Microsoftの調査では、開示前に悪意ある形で本脆弱性が悪用された証拠は確認されていない。
