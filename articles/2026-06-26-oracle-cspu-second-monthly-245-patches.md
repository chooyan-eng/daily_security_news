# Oracle 第2回月次セキュリティパッチ：245件のパッチを提供、CVE-2026-35273 の悪用続く

- **日付**: 2026-06-26
- **出典**: [SecurityWeek](https://www.securityweek.com/oracles-second-monthly-security-updates-deliver-245-patches/)
- **トピック**: [Oracle Critical Security Patch Update 2026年6月](../topics/oracle-cspu-june-2026.md)
- **分類**: 関連

## 概要

Oracle が 2026年6月26日、月次セキュリティパッチ（CSPU）の第2弾を公開した。243の一意なCVEに対する245件のパッチが提供され、約半数がクリティカル評価。Fusion Middleware に100件超のクリティカル・高評価パッチが集中しており、並行して ShinyHunters グループによる Oracle PeopleSoft CVE-2026-35273 の積極的悪用（100組織以上が標的）が継続中。

## 詳細

**パッチ概要**

Oracle が月次パッチサイクル（2026年から四半期毎から月次へ移行）の第2弾として 245件のセキュリティパッチを提供。対象プロダクト：
- Communications
- E-Business Suite
- Enterprise Manager
- Fusion Middleware（100件超、大多数がCritical/High）
- JD Edwards
- MySQL
- PeopleSoft
- Siebel CRM
- Supply Chain
- Systems
- Virtualization

**深刻度の内訳**

- 合計：243の一意なCVE を対象とした245件のパッチ
- クリティカル評価：約120件（全体の約49.8%）
- 認証不要でリモート悪用可能：100件以上

**CVE-2026-35273：PeopleSoft ゼロデイ（積極的悪用継続）**

ShinyHunters サイバー犯罪グループが Mandiant の調査で確認された Oracle PeopleSoft の重大脆弱性 CVE-2026-35273（CVSSv3.1 9.8）を引き続き悪用中。2026年5月27日〜6月9日の間に少なくとも100組織（主に高等教育機関）が標的とされた。本脆弱性は認証なしでリモートから RCE が可能な最大深刻度のゼロデイで、今回のパッチアップデートに修正が含まれる。

**Oracle の月次パッチサイクルへの移行**

Oracle は 2026年より従来の四半期毎（年4回）のパッチサイクルから月次サイクルに移行した。今回は 2026年6月リリースの第2弾にあたる。月次対応により脆弱性の修正速度は向上したが、IT チームのパッチ適用負担も増大している。

**Web・エンタープライズアプリへの影響**

Fusion Middleware（Oracle WebLogic、ADF 等を含む）への100件超のクリティカルパッチは、Oracle 技術スタックを使用する Web アプリケーションやエンタープライズシステムの管理者に即時対応を求める。特に PeopleSoft を使用する教育・政府機関は CVE-2026-35273 の積極的悪用継続を踏まえ最優先でパッチを適用すること。

---

## 関連記事

- [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../articles/2026-06-17-shinyhunters-oracle-peoplesoft-zero-day.md) — CVE-2026-35273 を悪用した ShinyHunters による高等教育機関への積極的攻撃
