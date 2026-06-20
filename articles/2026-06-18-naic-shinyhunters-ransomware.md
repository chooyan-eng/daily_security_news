# ShinyHunters、全米保険監督官会議（NAIC）を標的に 3.1TB の保険規制データを窃取

- **日付**: 2026-06-18
- **出典**: [RedPacket Security](https://www.redpacketsecurity.com/shinyhunters-ransomware-victim-naic-org/), [Ransomware.live](https://www.ransomware.live/), [Quasar Cyber Tech QPulse](https://qpulse.quasarcybertech.com/news/4161/shinyhunters-claims-compromise-of-national-association-of-insurance-commissioners-naic-data)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 関連

## 概要

脅威アクター ShinyHunters が2026年6月18日、全米保険監督官会議（NAIC: National Association of Insurance Commissioners）に対する攻撃を主張し、3.1テラバイト・105,000件以上のファイルを含む保険規制データを窃取したと発表。6月22日を交渉期限とし、応答がなければデータ公開とデジタル妨害を行うと脅迫している。

## 詳細

### 侵害されたシステムと流出データ

ShinyHunters が主張するデータには以下のシステムから取得されたものが含まれるとされる：
- **INSData**: 保険会社規制申告 PDF（210万件）
- **Vision**: 信用格付けフィード
- **SERFF（System for Electronic Rate and Form Filing）**: 保険商品申請システム
- **OPTINS**: 保険監督情報システム
- **UCAA（Uniform Certificate of Authority Application）**: 免許申請システム
- **EDP / RDC**: 規制データ収集システム
- **州保険局向け報告システム**

その他の流出データ：
- 四半期統計 CSV（4万件、連邦 EIN 含む）
- 格付け機関免許ファイル（4万5000件以上）：Moody's、Fitch、S&P、Kroll、DBRS、AM Best の記録

### NAIC の役割と影響の深刻性

NAIC は米国50州・DC・5つの領土の保険監督官で構成される非営利団体で、保険規制の標準化・調整を行う機関。保有するデータは保険業界の規制申告、信用格付け、統計データという極めて機微な情報を含む。

CUSIP/ISIN 識別子、詳細な財務諸表、連邦 EIN の流出は、数千の認可保険会社・格付け機関に対する下流詐欺やターゲット型攻撃を引き起こすリスクがある。

### タイムライン

- 2026年6月18日: Ransomware.live トラッカーに掲載、ShinyHunters が攻撃を主張
- 2026年6月22日: ShinyHunters が設定した交渉期限

### ShinyHunters の2026年攻撃パターンとの関連

ShinyHunters は2026年に大規模な攻撃キャンペーンを展開中。Kodak（220万件）、DentaQuest（260万件PHI/PII）、Canvas LMS（Instructure、2億7500万件）など多数の組織を標的にしている。Oracle PeopleSoft のゼロデイ悪用（CVE-2026-35273）とは異なる攻撃手法が用いられているが、同一脅威アクターによる継続的な大規模攻撃の一部と見られる。

### 推奨対応

- NAIC システムを利用する保険会社・規制機関は EIN・財務データの不正利用を監視
- NAIC が提供するセキュリティ通知に注意を払う
- 格付け機関は自社のライセンスファイルが悪用されていないか確認

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 同一脅威アクターによる大規模キャンペーン
- [ShinyHunters、Canvas LMS（Instructure）を二度侵害：2億7500万件の学生・教職員データを要求](../articles/2026-06-16-shinyhunters-canvas-lms-breach.md) - 同一脅威アクターによる教育機関攻撃
- [Kodak データ侵害：ShinyHunters が 220 万件の窃取を主張、6月18日期限の恐喝](../articles/2026-06-18-kodak-shinyhunters-breach.md) - 同日同一脅威アクターによる別組織への攻撃
