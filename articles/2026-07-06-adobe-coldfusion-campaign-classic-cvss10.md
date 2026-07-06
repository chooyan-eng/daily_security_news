# Adobe、ColdFusionとCampaign Classicに最大深刻度CVSS 10.0の脆弱性7件を含む緊急パッチ

- **日付**: 2026-07-06
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/adobe-patches-7-cvss-100-flaws-in.html)
- **トピック**: [Adobe ColdFusion・Campaign Classic 最大深刻度脆弱性（2026年7月）](../topics/adobe-coldfusion-campaign-classic-cve-2026.md)
- **分類**: 新規

## 概要

Adobeは2026年7月1日、ウェブアプリケーションサーバーColdFusion（2023／2025）とオンプレミス版Campaign Classic v7に対し、合計9件の脆弱性を修正する緊急パッチを公開した。うち7件がCVSS最大値10.0を記録し、いずれも任意コード実行につながる。Adobeは公開時点で悪用報告はないとしていたが、うち1件は公開後わずか数時間で実悪用が確認された。

## 詳細

### 脆弱性の内訳

**ColdFusion（CVSS 10.0、6件）**
- CVE-2026-48276、CVE-2026-48283：危険な種類のファイルの無制限アップロード
- CVE-2026-48277、CVE-2026-48281、CVE-2026-48316：不適切な入力検証
- CVE-2026-48282：パストラバーサル

**Campaign Classic（CVSS 10.0、1件）**
- CVE-2026-48286：不適切な認可

いずれも認証なしまたは低難度で任意コード実行（RCE）に至る可能性がある。

### 悪用状況

Adobeはパッチ公開時点でこれら9件の脆弱性いずれについても悪用の報告はないとしていた。しかし、パストラバーサル脆弱性CVE-2026-48282については、公開からわずか数時間で実際の悪用が確認されている。

### 修正バージョン

- ColdFusion 2023：Update 21
- ColdFusion 2025：Update 10
- Campaign Classic：ACC v7 7.4.3 build 9397

### 背景

ColdFusionはCISAのKEVカタログに既に16件のCVEが登録されている「悪用の常連」製品であり、今回の大量の最大深刻度脆弱性も同様の即時悪用リスクを抱える。ウェブアプリケーションサーバーとして稼働しているColdFusionインスタンスは早急なパッチ適用が求められる。

### 対策

- ColdFusion 2023 Update 21／2025 Update 10 の即時適用
- Campaign Classic ACC v7 7.4.3 build 9397 への更新
- インターネット公開されたColdFusion/Campaign Classicサーバーの棚卸しとアクセス制限

---

## 関連記事

なし（新規トピック）
