# Klue OAuth 侵害で「Icarus」がSalesforce CRM データを複数組織から窃取・恐喝

- **日付**: 2026-06-18
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/klue-oauth-breach-linked-to-icarus-salesforce-data-theft-attacks/), [Huntress](https://www.huntress.com/blog/klue-breach-investigation), [ReliaQuest](https://reliaquest.com/blog/threat-spotlight-integration-abused-in-crm-data-theft)
- **トピック**: [Klue OAuth 侵害・Icarus による Salesforce データ窃取（2026年6月）](../topics/klue-oauth-icarus-salesforce-2026.md)
- **分類**: 新規

## 概要

市場インテリジェンスプラットフォーム Klue が OAuth 侵害を受け、「Icarus」と名乗る新興脅威アクターが複数の顧客組織の Salesforce CRM データを窃取する被害が発生した。攻撃者は Klue のバックエンドシステムを侵害し悪意あるコード更新をプッシュして OAuth トークンを窃取、Salesforce CRM に対して約24時間にわたり自動化されたデータ抽出を実施した。Salesforce は調査中として Klue Battlecards インテグレーションを無効化した。

## 詳細

### 攻撃の手口

攻撃者（Icarus）は以下の手順でデータを窃取した：

1. **Klue バックエンドシステムの侵害**: Klue の内部システムに不正アクセス
2. **悪意あるコード更新のプッシュ**: Klue の Battlecards 製品が第三者プラットフォームと連携するために使用する OAuth トークンを窃取するコードを注入
3. **サービスアカウント経由の認証**: 侵害された Klue インテグレーションサービスアカウントを通じて認証し、OAuth トークンを生成
4. **自動化された REST API クエリ**: Salesforce 環境に対して約24時間にわたり Python スクリプトを使用した REST API クエリを実行してデータを抽出

### 技術的詳細

攻撃者が実行した Salesforce REST API クエリのパターン：
- 標準オブジェクト（Contact、Account、Lead、Opportunity）への大量クエリ
- 約24時間の継続的なデータ抽出
- 正規の OAuth トークンを悪用するため、API ゲートウェイのレート制限を迂回

### 被害組織の範囲

Huntress を含む複数のセキュリティ会社が自社の Salesforce データが窃取されたことを確認。ReliaQuest も独立した分析を公開し、継続的な恐喝キャンペーンを確認した。Icarus は複数の Klue 顧客に対して恐喝メールを送信中。

### Icarus について

- **活動開始**: 2026年4月28日（自称）
- **特徴**: 比較的新興の脅威アクター、ダークウェブサイトでの活動とメール恐喝を組み合わせる
- **被害実績**: Klue 侵害以前に2件の被害組織を掲載済み

### Salesforce の対応

Salesforce は調査中として Klue Battlecards インテグレーションをプラットフォーム上で無効化した。これにより既存の Klue + Salesforce 連携は一時停止されている。

### サプライチェーン型 OAuth 攻撃の意義

このインシデントはサードパーティ SaaS インテグレーションが新たな攻撃ベクターとなっている状況を示す。OAuth トークンベースのインテグレーションは多くの企業に浸透しており、一つのプロバイダーが侵害されるとダウンストリームの複数企業が連鎖的に被害を受けるリスクがある。

### 推奨対応

1. Klue の Battlecards インテグレーションを使用している組織は Salesforce の接続アプリを確認し、不審な API アクセス履歴を調査
2. Salesforce のイベントモニタリングで不審な大量クエリ（特に外部アプリからのもの）を検索
3. 第三者インテグレーションに付与している OAuth スコープを最小権限に見直す
4. 侵害が疑われる場合は OAuth トークンを即時失効（Salesforce の Connected Apps 設定から実施可能）

---

## 関連記事
