# Kodak データ侵害：ShinyHunters が 220 万件の窃取を主張、6月18日期限の恐喝

- **日付**: 2026-06-18
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/kodak-confirms-data-breach-claimed-by-shinyhunters-extortion-gang/), [SecurityWeek](https://www.securityweek.com/kodak-admits-data-breach-after-shinyhunters-hack-claims/), [Malwarebytes](https://www.malwarebytes.com/blog/news/2026/06/kodak-confirms-breach-as-shinyhunters-leak-threat-reaches-deadline)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 関連

## 概要

映像技術大手 Eastman Kodak が、ShinyHunters による 220 万件以上の顧客 PII と社内データの窃取主張を受けてセキュリティインシデントを確認した。6月18日が ShinyHunters の設定した最終期限であり、期限内に交渉しなければデータ公開と「デジタル妨害」を行うと脅迫されている。

## 詳細

### インシデントの概要

- **最初の主張**: 2026年6月15日、ShinyHunters が自社のダークウェブリークサイトに Kodak を掲載
- **恐喝期限**: 2026年6月18日（本日）
- **主張されるデータ規模**: 220万件以上の顧客 PII および社内企業データ

### Kodak の公式声明

Kodak は「未承認の第三者が限定的な量の会社データに一時的にアクセスした」と認め、外部のサイバーセキュリティ専門家と法執行機関と連携して調査を継続していると発表した。ただし ShinyHunters の主張する全体的な侵害規模は独自に確認できていないとしている。

### ShinyHunters の2026年拡大キャンペーン

Kodak への攻撃は ShinyHunters が2026年に展開している急速な多組織攻撃の一部。今年の被害組織には Charter Communications、7-Eleven、Medtronic、Vimeo、Instructure（Canvas LMS）、ADT、Vercel、DentaQuest が含まれ、さらに本日 NAIC（全米保険監督官会議）への攻撃も主張されている。

### Oracle PeopleSoft 攻撃との関連性

ShinyHunters は今年5月〜6月にかけて Oracle PeopleSoft のゼロデイ（CVE-2026-35273）を悪用した攻撃も実施している（大学等100社以上が被害）。Kodak への攻撃では異なる攻撃手法が用いられているが、同一脅威グループの継続的な恐喝活動の一環として捉えられている。

### 影響評価

Kodak の声明によれば、顧客向けシステムへの影響はないとされているが、220万件の顧客 PII が流出している場合はプライバシー通知義務が発生する可能性がある。

### 推奨対応

- Kodak の顧客・パートナー組織は公式通知を注視
- Kodak との取引で使用したメールアドレスのフィッシング詐欺に警戒
- 状況が進展した場合のデータ侵害通知の受信に備える

---

## 関連記事

- [ShinyHunters、全米保険監督官会議（NAIC）を標的に 3.1TB の保険規制データを窃取](../articles/2026-06-18-naic-shinyhunters-ransomware.md) - 同日同一脅威アクターによる別組織への攻撃
- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 同一脅威アクターによる大規模キャンペーン
