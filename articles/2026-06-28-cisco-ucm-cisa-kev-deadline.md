# Cisco UCM CVE-2026-20230 SSRF：CISA KEV 対応期限が本日（June 28）到来

- **日付**: 2026-06-28
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/cisa-sets-urgent-deadline-to-fix-cisco-flaw-exploited-in-attacks/amp/) / [SecurityAffairs](https://securityaffairs.com/194290/security/u-s-cisa-adds-cisco-and-ptc-windchill-and-flexplm-flaws-to-its-known-exploited-vulnerabilities-catalog.html)
- **トピック**: [Cisco Unified CM CVE-2026-20230 SSRF 積極的悪用（2026年6月）](../topics/cisco-ucm-cve-2026-20230-ssrf.md)
- **分類**: 続報

## 概要

CISA が Known Exploited Vulnerabilities（KEV）カタログに Cisco Unified Communications Manager の SSRF 脆弱性 CVE-2026-20230 を追加し、連邦機関に対して**本日2026年6月28日**を修正期限として設定した。BleepingComputer が改めて緊急性を報道し、未対応の連邦・民間組織への注意喚起が行われている。

## 詳細

### 期限の経緯

| 日付 | 内容 |
|------|------|
| 2026-06-24 | Defused Cyber が積極的悪用を確認、CISA が KEV 追加 |
| 2026-06-28 | CISA が設定した連邦機関のパッチ適用期限（本日） |

### 脆弱性のリマインダー

- **CVE**: CVE-2026-20230（CVSS 8.6）
- **種別**: サーバーサイドリクエストフォージェリ（SSRF）
- **対象**: Cisco Unified CM、Unified CM SME
- **悪用前提**: 未認証・リモート
- **影響**: 内部ネットワーク探索・SSRF 経由の内部システムへのアクセス

### 未対応機関へのリスク

企業のテレフォニーシステムや UC インフラ全体が侵害の起点となるリスクがある。特に Cisco UCM をコーポレートネットワークのコアに置いている組織では、SSRF を経由した内部システムアクセスが侵害を深刻化させる可能性がある。

期限を迎えた本日（2026年6月28日）時点でパッチ未適用の場合は至急対応すること。
