# Klue OAuth侵害を起点とする「Icarus」キャンペーン - Salesforce CRMデータが多数企業から窃取

- **日付**: 2026-06-19
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/klue-oauth-breach-linked-to-icarus-salesforce-data-theft-attacks/)
- **トピック**: [Klue OAuth侵害と「Icarus」キャンペーン（2026年6月）](../topics/klue-icarus-salesforce-oauth-2026.md)
- **分類**: 新規

## 概要

競合インテリジェンスプラットフォームKlueへの侵害を起点に、脅威アクター「Icarus」グループが多数の企業のSalesforce CRMデータを窃取する攻撃キャンペーン。6月11日にKlueのバックエンドへの不正アクセスが発生し、OAuthトークンを収集する悪意あるコードが展開された。Salesforceは6月19日にパートナーアプリ「Klue Battlecards」の接続を無効化した。

## 詳細

### 攻撃の経緯

2026年6月11日、攻撃者はKlueのバックエンドインフラに長期休眠状態だったAPIクレデンシャルを使用してアクセス。このクレデンシャルは廃棄されたサードパーティ統合プロトタイプ用に作成されたものだった。そこから、顧客がSalesforce等のサービスと接続するために使用するOAuthトークンを収集する悪意あるコードアップデートを展開した。

### 影響を受けたサービス

窃取されたOAuthトークンにより、以下のサービスのデータが不正アクセスされた可能性がある：
- Salesforce
- HubSpot
- SharePoint
- Zoom
- Gong / Chorus / Clari
- Google Drive
- Slack

### 攻撃の技術的手法

Huntressの報告によれば、攻撃者はOAuthトークンと自動化されたPythonスクリプトを使用し、正規のAPIチャネルを通じてSalesforce CRMのデータをバルクで引き出した。これにより、Klueのバックエンドインフラへの直接アクセスを超えた被害が拡大した。

### 流出データの内容

Salesforceが開示した情報によると、影響を受けた可能性のある情報は以下の通り：
- 企業名と連絡先情報
- 使用している製品
- 価格情報

Huntressのような複数の企業が被害を報告しており、より広範な顧客データが含まれていた可能性がある。

### 脅威アクター「Icarus」

HuntressはこのキャンペーンをIcarusグループ（2026年4月下旬から活動開始）に帰属させた。根拠は、恐喝メールとダークウェブリークサイトの両方に同一のSession Messenger IDが発見されたことである。

### Salesforceの対応

Salesforceのセキュリティチームは、Klue Battlecardsアプリを通じた顧客データへの不正アクセスを示す異常な活動を検出。6月19日、すべての影響を受けた顧客環境でKlue Battlecardsアプリの接続を無効化した封じ込め措置を実施。Salesforceは、問題の根本原因はKlueの統合レイヤーにあり、コアプラットフォームの脆弱性ではないと確認した。

### より広い文脈：OAuthエコシステムの脆弱性

このインシデントは、サードパーティSaaS統合を通じたOAuth脆弱性の悪用という手法を再び浮き彫りにした。攻撃者はプラットフォーム本体の脆弱性を突くのではなく、信頼された統合アプリの侵害を通じて大規模なデータ窃取を実現した。

---

## 関連記事

なし（新規トピック）
