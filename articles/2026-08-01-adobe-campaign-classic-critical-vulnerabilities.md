# Adobe Campaign Classic にCVSS満点10.0の認可不備・重大SQLインジェクション脆弱性

- **日付**: 2026-08-01
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/adobe-patches-7-cvss-100-flaws-in.html) / [BleepingComputer](https://www.bleepingcomputer.com/news/security/adobe-patches-seven-max-severity-coldfusion-campaign-flaws/) / [TheHackerWire](https://www.thehackerwire.com/adobe-campaign-classic-critical-rce-via-incorrect-authorization-cve-2026-48449/)
- **トピック**: [Adobe ColdFusion / Campaign Classic 重大脆弱性（2026年7月）](../topics/adobe-coldfusion-campaign-classic-2026.md)
- **分類**: 続報
## 概要

Adobeは2026年7月30日、Campaign Classic（ACC）向けにCVSSスコア10.0の認可不備の脆弱性（CVE-2026-48449）とCVSS8.6のSQLインジェクション脆弱性（CVE-2026-48448）を含む複数の重大パッチを公開した。オンプレミス導入環境が主な影響対象。

## 詳細

CVE-2026-48449は「Incorrect Authorization」に分類される脆弱性で、CVSSスコアは最大値の10.0。適切な認可チェックが欠如していることで、攻撃者が本来許可されていない操作を実行できる可能性がある。CVE-2026-48448は「High」severity（CVSS 8.6）のSQLインジェクション脆弱性で、細工したリクエストによりバックエンドのデータベースに不正なクエリを実行される恐れがある。

両脆弱性はAdobe Campaign Classic v7.4.3 build 9397以前のバージョン（Windows/Linux両プラットフォーム）に影響し、完全オンプレミス環境およびハイブリッド環境のオンプレミスコンポーネントが特に影響を受ける。Adobeがホストするインスタンスは既に対策済みとされている。

これに先立ち、6月末から7月上旬にかけてもCampaign Classicの別の最大深刻度脆弱性（CVE-2026-48286）が修正されており、認証済みユーザーのコンテキストで任意コード実行に繋がる恐れがあった。同時にAdobeはColdFusionについても複数の最大深刻度（CVSS 10.0を含む）脆弱性を修正しており、パッチ公開後に一部で悪用の兆候が報告されている。Campaign ClassicはマーケティングオートメーションのWebベース基盤であり、顧客データベースへの直接アクセスを持つため、悪用時の影響は個人情報漏洩に直結する。オンプレミス運用組織は速やかなパッチ適用が強く推奨される。
