# SonicWall SMA1000シリーズ、2件のゼロデイ脆弱性が実際に悪用中と警告

- **日付**: 2026-07-14
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-sma1000-flaws-exploited-in-zero-day-attacks-patch-now/), [The Hacker News](https://thehackernews.com/2026/07/two-sonicwall-sma-1000-zero-days.html), [Help Net Security](https://www.helpnetsecurity.com/2026/07/14/sonicwall-sma-attacks-via-cve-2026-15409-cve-2026-15410/)
- **トピック**: [SonicWall SMA1000 ゼロデイ悪用（CVE-2026-15409/15410）](../topics/sonicwall-sma1000-cve-2026-15409.md)
- **分類**: 新規

## 概要

SonicWallは2026年7月14日、SMA1000シリーズ（SMA6210・SMA7210・SMA8200v）に影響する2件のゼロデイ脆弱性CVE-2026-15409（CVSS 10.0、SSRF）とCVE-2026-15410（CVSS 7.2、認証後コードインジェクション）が実際の攻撃で悪用されていると警告した。両脆弱性を連鎖させることで、未認証の遠隔攻撃者が管理者権限で任意のOSコマンドを実行できる。CISAは即日KEVカタログに追加している。

## 詳細

### 脆弱性の技術的詳細

**CVE-2026-15409（SSRF、CVSS 10.0）**
SMA1000の Appliance Work Place インターフェースに存在するサーバーサイドリクエストフォージェリ（SSRF）脆弱性。未認証の遠隔攻撃者がアプライアンスに対して意図しない宛先へのリクエストを強制的に発行させることが可能。CVSS満点の最大深刻度。

**CVE-2026-15410（認証後コードインジェクション、CVSS 7.2）**
SMA1000の Appliance Management Console に存在する認証後のコードインジェクション脆弱性。遠隔の認証済み管理者が任意のOSコマンドを実行できる。

### 悪用の連鎖

SonicWallは複数のインシデントを調査した結果、両脆弱性が組み合わせて悪用されていることを確認した。未認証の攻撃者がCVE-2026-15409のSSRFを起点にCVE-2026-15410へアクセスし、管理者権限でのコマンド実行に至る攻撃チェーンが成立する。

### 対象製品とパッチ

影響を受けるのはSMA6210、SMA7210、SMA8200vの各アプライアンス。SonicWallはホットフィックスリリース12.4.3-03453および12.5.0-02835を提供しており、早急な適用が推奨されている。

### 政府機関への対応要求

CISAはKEVカタログへの追加に伴い、連邦機関に対しBinding Operational Directive（BOD）26-04に基づき2026年7月17日までに対象システムを保護するか、緩和策が適用できない場合は製品の利用を中止するよう義務付けた。

---

## 関連記事

なし（新規トピック）
