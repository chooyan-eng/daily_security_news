# Adobe、ColdFusion・Campaign Classic 等5製品で51件の脆弱性を修正 – CVSS10.0のコマンドインジェクション等、最優先パッチ指定

- **日付**: 2026-08-12
- **出典**: [SecurityWeek](https://www.securityweek.com/adobe-urges-immediate-patching-of-critical-coldfusion-campaign-classic-flaws/), [The Hacker News](https://thehackernews.com/2026/08/adobe-campaign-classic-cvss-100-flaw.html)
- **トピック**: [Adobe 2026年8月定例セキュリティ更新（ColdFusion・Campaign Classic）](../topics/adobe-coldfusion-campaign-classic-2026.md)
- **分類**: 新規

## 概要

Adobe は8月11日（8月定例パッチ）、ColdFusion、Commerce、Lightroom Classic、Content Credentials SDK、Campaign Classic の5製品に対し、合計51件の脆弱性を修正するセキュリティ更新をリリースした。うち33件が「クリティカル」評価。ColdFusion と Campaign Classic の更新は最優先度「Priority 1」に指定され、即時パッチ適用が強く求められている。

## 詳細

### ColdFusion（Priority 1）

15件の脆弱性を修正し、うち3件がクリティカル。
- CVE-2026-48362（CVSS 10.0）: OSコマンドインジェクション
- CVE-2026-48273（CVSS 9.9）: eval インジェクション
- CVE-2026-71384（CVSS 9.6）: 不適切な認可

いずれも任意コード実行またはサービス拒否（DoS）につながる恐れがある。

### Campaign Classic（Priority 1）

任意コード実行に至る3件のクリティカルな脆弱性を修正。
- CVE-2026-71398、CVE-2026-27302（いずれもCVSS 10.0）: 不適切な認可
- CVE-2026-48381（CVSS 9.0）: SQLインジェクション

### Commerce

7件の脆弱性を修正。うち CVE-2026-71362（CVSS 9.1）は不適切な認可による権限昇格に該当する。

### 対応方針

Adobe は ColdFusion・Campaign Classic の更新を最優先度「Priority 1」として位置付けており、影響を受ける組織は速やかにパッチを適用することが求められる。特にコマンドインジェクション（CVSS 10.0）やSQLインジェクションを含む脆弱性は、インターネットに公開されたサーバーで悪用された場合の被害が大きく、優先対応が必要。

### 対策

- ColdFusion・Campaign Classic の更新を最優先で適用
- インターネットに公開している ColdFusion サーバーの棚卸しと露出範囲の見直し
- Commerce における権限昇格脆弱性を踏まえ、管理者アカウントの権限設定を確認

---

## 関連記事

なし（新規トピック）
