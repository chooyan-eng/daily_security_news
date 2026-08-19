# Microsoft 2026年7月Patch Tuesday：過去最大621件のCVEを修正、悪用済みゼロデイ2件含む

- **日付**: 2026-07-14
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-july-2026-patch-tuesday-fixes-massive-570-flaws-3-zero-days/), [SecurityAffairs](https://securityaffairs.com/195347/security/patch-tuesday-security-updates-for-july-2026-the-largest-update-ever-621-cves-in-one-month.html)
- **トピック**: [Microsoft Patch Tuesday 2026年7月](../topics/microsoft-patch-tuesday-july-2026.md)
- **分類**: 新規

## 概要

Microsoftは2026年7月のPatch Tuesdayで過去最大となる621件のCVEを修正した（一部報道では570〜622件とばらつきあり）。うち3件はゼロデイ脆弱性で、Active Directory Federation Services（AD FS）の権限昇格（CVE-2026-56155）とSharePoint Serverの認証欠如による権限昇格（CVE-2026-56164）の2件は既に実際の攻撃で悪用が確認されている。SharePoint、RDP、Hyper-Vにも重大な脆弱性が含まれる。

## 詳細

### 過去最大規模の月例更新

今回のリリースは、これまでの月間最多記録（6月の198件）を大幅に上回る規模となった。Microsoftは、この件数急増の一因として、Windowsのコードベースを脅威アクターに先んじてスキャンするAI駆動の脆弱性発見システムを新たに導入したことを挙げている。

### 悪用が確認されたゼロデイ

**CVE-2026-56155（AD FS 権限昇格）**
Active Directory Federation Services に存在するアクセス制御の粒度不足に起因する脆弱性（CVSSv3: 7.8、重要度: Important）。悪用に成功すると攻撃者は管理者権限を取得できる。Microsoftは実際の攻撃での悪用（in the wild）を確認済み。

**CVE-2026-56164（SharePoint Server 権限昇格）**
重要機能に対する認証の欠如に起因する脆弱性（CVSSv3: 5.3、重要度: Moderate）。認証されていないネットワーク攻撃者が権限を昇格できる。こちらもMicrosoftが実際の悪用を確認している。

両CVEは、CISAが2026年7月14日付でKnown Exploited Vulnerabilities（KEV）カタログに追加しており、連邦機関に対して期限内のパッチ適用を義務付けている。

### その他の重大な脆弱性

SharePoint、リモートデスクトッププロトコル（RDP）、Hyper-Vにおいても複数の重大な脆弱性が修正されている。件数の多さから、企業のパッチ適用計画では優先度付けが重要になるとセキュリティ各社が指摘している。

### 対応

Microsoft製品を利用する組織は、特にAD FSおよびSharePoint Serverについて、実際の悪用が確認されているため最優先でのパッチ適用が推奨される。日本国内でもIPAが2026年7月15日付でMicrosoft製品の脆弱性対策情報を公開し、注意を呼びかけている。

---

## 関連記事

なし（新規トピック）
