# Oracle Critical Security Patch Update 2026年6月：245件のパッチで10件のクリティカル脆弱性を修正

- **日付**: 2026-06-18
- **出典**: [Oracle Security Alerts](https://www.oracle.com/security-alerts/cspujun2026.html), [SecurityWeek](https://www.securityweek.com/oracles-second-monthly-security-updates-deliver-245-patches/), [Feedly CVE Advisory](https://feedly.com/cve/security-advisories/oracle/2026-06-16-oracle-critical-security-patch-update-advisory-june-2026-10-critical-vulnerabilities-amid-67-cves)
- **トピック**: [Oracle Critical Security Patch Update 2026年6月](../topics/oracle-cspu-june-2026.md)
- **分類**: 新規

## 概要

Oracle が2026年6月16〜17日に Critical Security Patch Update（CSPU）June 2026 をリリースした。245件の新しいセキュリティパッチを複数の製品ファミリーに適用し、うち10件がクリティカル評価。これは Oracle の第2回月次セキュリティアップデートで、ShinyHunters に積極的に悪用された Oracle PeopleSoft のゼロデイ CVE-2026-35273 に対する恒久的なパッチも含まれる。

## 詳細

### 更新の規模

- **新規パッチ数**: 245件
- **クリティカル**: 約10件
- **高深刻度（High）**: 多数（詳細は Oracle アドバイザリ参照）
- **リモートから認証なしで悪用可能な脆弱性**: 100件近く
- **Oracle Fusion Middleware**: 100件以上のパッチ（大部分がクリティカルまたは高深刻度）

### 主要製品への影響

**Oracle PeopleSoft（CVE-2026-35273）**  
CVE-2026-35273（CVSS 9.8）は PeopleSoft Enterprise PeopleTools に存在し、認証なしにリモートからのコード実行を可能にした。ShinyHunters が5月27日〜6月9日にかけてこのゼロデイを悪用し、100社以上（68%が高等教育機関）に侵入した。Oracle は6月10日に緊急セキュリティアラートとしてパッチを先行リリースしており、今回の CSPU でも正式に組み込まれた。

**Oracle Fusion Middleware**  
最も多くのパッチが適用された製品ファミリー。Oracle WebLogic Server、Oracle HTTP Server、Oracle SOA Suite 等が含まれる。多数のパッチがリモートから認証なしで悪用可能なクリティカルな RCE 脆弱性に対応している。

**Communications 製品**  
Oracle Communications アプリケーション・セッションコントローラ等の通信系製品にも多数の修正。

**Oracle Database**  
Oracle Database Server 自体にも複数のパッチが適用されている。

### 月次パッチ体制への移行

Oracle はこれまでの四半期ごとの CPU（Critical Patch Update）から月次の CSPU（Critical Security Patch Update）に移行している。2026年6月のアップデートは「Oracle の第2回月次セキュリティアップデート」と説明されており、より迅速なセキュリティ対応を目的としている。

### 優先対応が必要な脆弱性

1. **CVE-2026-35273**（PeopleSoft、CVSS 9.8）: ShinyHunters による積極的な悪用実績あり、最優先
2. Oracle Fusion Middleware のクリティカル RCE 脆弱性群: リモートから認証不要での悪用可能性
3. Oracle WebLogic Server の既知の攻撃対象: 過去の悪用実績からも優先度が高い

### 推奨対応

1. Oracle が推奨するアクティブサポートバージョンへのアップグレードを確認
2. CVE-2026-35273（PeopleSoft）のパッチを最優先で適用
3. Oracle Fusion Middleware のパッチを速やかに評価・適用
4. 外部に公開されている Oracle アプリケーションは特に緊急に対応
5. Oracle の CPU アドバイザリを定期的に確認し、遅延なくパッチを適用するプロセスを整備

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 本パッチで恒久修正された脆弱性の悪用事例
