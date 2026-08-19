# Adobe ColdFusion / Campaign Classic 重大脆弱性（2026年7月）

## 概要

2026年7月にAdobeが公開したColdFusionおよびCampaign Classic向けセキュリティ更新。CVSS 10.0の重大脆弱性7件（ColdFusion 6件、Campaign Classic 1件）を含み、任意コード実行につながる恐れがある。悪用は未確認。

**同一性の判断に役立つ情報：**
- ベンダー: Adobe
- 対象製品: ColdFusion（2025/2023）、Campaign Classic（オンプレミス版）
- 公開日: 2026-07-01
- 主要CVE: CVE-2026-48276, -48277, -48281, -48316, -48282, -48283（ColdFusion、CVSS10.0）、CVE-2026-48286（Campaign Classic、CVSS10.0）
- 修正版: ColdFusion 2025 Update 10 / 2023 Update 21、ACC v7.4.3 build 9397
- 対象製品: Adobe ColdFusion 2023／2025、Campaign Classic v7（オンプレミス）
- 脆弱性件数: 9件（うちCVSS 10.0が7件）
- 主なCVE: CVE-2026-48276、48277、48281、48282、48283、48316（ColdFusion）、CVE-2026-48286（Campaign Classic）
- 公開日: 2026年7月1日
- 修正バージョン: ColdFusion 2023 Update 21／2025 Update 10、Campaign Classic 7.4.3 build 9397
- 悪用確認: CVE-2026-48282が公開後数時間で実悪用
- CVE: CVE-2026-48282
- CVSSスコア: 10.0（最大深刻度）
- 対象製品: Adobe ColdFusion 2025.9、2023.20 およびそれ以前
- 脆弱コンポーネント: RDS（Remote Development Services）FILEIOハンドラ
- 悪用条件: RDS有効 + RDS認証無効
- 修正版: ColdFusion 2025 Update 10 / ColdFusion 2023 Update 21
- 悪用開始: 詳細公開から約2時間後
- CVSS: 10.0
- 脆弱性種別: パストラバーサル
- 影響製品: Adobe ColdFusion 2025.9、2023.20 以前
- CISA KEV 追加日: 2026年7月7日
- 連邦機関修正期限: 2026年7月10日（BOD 26-04）
- CVE: CVE-2026-48282（Adobe ColdFusion、パストラバーサル、CVSS 10.0）
- 開示日: 2026年7月7日／実悪用確認: 開示から数時間後
- CISA KEV追加: 2026年7月8日頃、同時にCVE-2026-56290（Joomlackページビルダー）、CVE-2026-55255（Langflow）も追加
- 影響: 現在のユーザー権限でのリモートコード実行
- CVSS: 10.0（最大深刻度）
- 対象製品: Adobe ColdFusion 2025.9、2023.20 以前
- 脆弱性種別: パストラバーサル（RDS FILEIOハンドラ経由のRCE）
- 悪用前提条件: RDS有効 + RDS認証無効
- 技術詳細公開: watchTowr Labs
- 悪用初観測: 2026年7月2日（KEVIntelハニーポット）
- FCEB 機関修正期限: 2026年7月10日
- CVE: CVE-2026-48449（関連: CVE-2026-48286）
- 対象製品: Adobe Campaign Classic（オンプレミス・ハイブリッドのみ、Adobeホスト型は対象外）
- 公開日: 2026年7月30日
- 修正バージョン: ACC v7 7.4.3 build 9397

## タイムライン

- [2026-07-30 Adobe、Campaign Classic に最大深刻度（CVSS 10.0）の認可不備 RCE 脆弱性（CVE-2026-48449）を修正](../articles/2026-07-31-adobe-campaign-classic-coldfusion-cve-2026-48449.md)
- [2026-07-09 Adobe ColdFusionの最大深刻度パストラバーサル脆弱性（CVE-2026-48282）、CISA KEVに追加・積極的悪用を確認](../articles/2026-07-09-adobe-coldfusion-cve-2026-48282-kev.md)
- [2026-07-08 CISA、積極的に悪用されているAdobe ColdFusionの最大深刻度パストラバーサル脆弱性(CVE-2026-48282)を巡り連邦機関に金曜日までの修正を指示](../articles/2026-07-08-adobe-coldfusion-cve-2026-48282-kev.md)
- [2026-07-07 Adobe ColdFusion 最大深刻度10.0の脆弱性が積極的悪用 — CISAが連邦機関へ7月10日までの緊急パッチ適用を指示](../articles/2026-07-10-adobe-coldfusion-cve-2026-48282-kev.md)
- [2026-07-07 Adobe ColdFusion 最大深刻度パストラバーサル脆弱性（CVE-2026-48282）が野放し状態で悪用中](../articles/2026-07-07-adobe-coldfusion-cve-2026-48282.md)
- [2026-07-06 Adobe、ColdFusionとCampaign Classicに最大深刻度CVSS 10.0の脆弱性7件を含む緊急パッチ](../articles/2026-07-06-adobe-coldfusion-campaign-classic-cvss10.md)
- [2026-07-01 Adobe、ColdFusionとCampaign Classicに存在するCVSS10.0の重大脆弱性7件を修正](../articles/2026-07-01-adobe-coldfusion-campaign-classic-july-2026.md)
