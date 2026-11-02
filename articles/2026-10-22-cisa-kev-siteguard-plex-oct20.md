# CISA、SiteGuard Server EditionのOSコマンドインジェクション（CVE-2026-106931）やPlex Media Serverの脆弱性などKEVに6件追加

- **日付**: 2026-10-22（CISA発表は10月20日）
- **出典**: [CISA](https://www.cisa.gov/news-events/alerts/2026/10/20/cisa-adds-six-known-exploited-vulnerabilities-catalog)
- **トピック**: [SiteGuard WAF CVE-2026-106931 OSコマンドインジェクション悪用（2026年10月）](../topics/siteguard-waf-cve-2026-106931.md)
- **分類**: 続報

## 概要

CISAが10月20日、悪用が確認された6件の脆弱性をKEVカタログに追加した。EG Secure SolutionsのSiteGuard Server Editionのコマンドインジェクション（CVE-2026-106931）のほか、Plex Media Serverの2件（CVE-2026-96652、CVE-2026-96656）、Siemens Software Centerの検索パス問題（CVE-2026-110936）などが含まれる。

## 詳細

- CVE-2026-106931: SiteGuard Server EditionのOSコマンドインジェクション。ベンダー・JVNが実攻撃での悪用を確認済みの事案で、今回CISAのKEVにも掲載された。パッチ適用前のログ保全が推奨されている。
- CVE-2026-96656: Plex Media Serverのファイル名/パスの外部制御。CVE-2026-96652（SSRF）と連鎖する「Plex2Shell」でマイニングマルウェア配布などが観測されている（単一研究者のハニーポット観測が中心との報道）。修正版は1.43.3.10861。
- CVE-2026-110936: Siemens Software Centerの信頼できない検索パス要素。
- 米連邦機関にはKEV掲載脆弱性への期限内対応が求められるが、民間組織でも優先的なパッチ適用の指標になる。WAF等の境界機器や、Webからアクセス可能なメディアサーバーは特に露出状況の確認が望ましい。
- 掲載6件のうち上記以外の2件の詳細は今回確認できていない。

---

## 関連記事

- [Plex Media ServerのCVE-2026-96652（SSRF）・CVE-2026-96651（パストラバーサル）がCVE採番、1.43.3.10861で修正](../articles/2026-10-20-plex-ssrf-cve-2026-96652.md) - Plex側のCVE
