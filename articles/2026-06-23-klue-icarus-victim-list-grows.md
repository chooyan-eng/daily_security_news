# Klue OAuth侵害 続報：Icarus の被害組織リストが拡大、複数のサイバーセキュリティ企業が被害確認

- **日付**: 2026-06-23
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/klue-oauth-breach-victim-list-grows-as-icarus-hackers-claim-attack/)
- **トピック**: [Klue OAuth侵害と「Icarus」キャンペーン（2026年6月）](../topics/klue-icarus-salesforce-oauth-2026.md)
- **分類**: 続報

## 概要

2026年6月22日、Klue の OAuth トークン侵害に起因する Salesforce データ窃取キャンペーンの被害組織リストが拡大していることが判明。脅威アクター「Icarus」が攻撃を公式に主張し、Huntress・Recorded Future・Tanium・Jamf 等の著名なサイバーセキュリティ企業を含む複数組織が被害を確認した。

## 詳細

### 被害組織の拡大

6月22日時点で確認されている被害組織には以下が含まれる：

- **Huntress**（EDRサービス企業）
- **Recorded Future**（脅威インテリジェンス企業）
- **Tanium**（エンドポイントセキュリティ企業）
- **Jamf**（Apple デバイス管理企業）
- **Sprout Social**（ソーシャルメディア管理企業）
- **Gong**（会話インテリジェンスプラットフォーム）
- **Insurity**（保険テックソフトウェア企業）

いずれの組織も Klue の競合インテリジェンスプラットフォームを Salesforce と連携させていた。

### 攻撃手法の詳細

Icarus グループは侵害の起点として、Klue が以前にプロトタイプとして作成した後に放棄された旧来の認証情報を悪用した。この認証情報は無効化されず長期間有効なまま残存していた。攻撃者はこの認証情報でKlueのインフラに侵入し、顧客の OAuth トークンを窃取、さらにそのトークンを使って各組織の Salesforce CRM に直接クエリを発行してデータを収集した。

### 窃取データの種類

- ビジネスコンタクト情報
- 営業通信記録
- 価格情報
- 商談メモ（Salesforce オポチュニティデータ）

### Klue の対応

Klue は以下の技術的対応を実施した：

1. 影響を受けた認証情報と OAuth トークンの即時無効化
2. Salesforce、Gong、HubSpot、SharePoint、Zoom、Chorus、Clari、Google Drive、Slack App 等との連携無効化
3. 不正コードの除去
4. CrowdStrike をインシデントレスポンスに起用
5. 法執行機関への通報

### Salesforce の対応

Salesforce は2026年6月19日に全顧客環境で Klue Battlecards アプリの接続を無効化した。

### Icarus グループの正体

Icarus は2026年4月下旬から活動を開始した新興の恐喝グループ。リークサイトを持ち、被害組織に恐喝メールを送付することで知られる。GMS.net など Klue インシデント以外の標的への攻撃も確認されている（関連記事参照）。

---

## 関連記事

- [GMS.net 侵害：Icarus グループによる新たな攻撃](../articles/2026-06-23-gms-icarus-breach.md) - 同一脅威アクター Icarus による別組織への攻撃
