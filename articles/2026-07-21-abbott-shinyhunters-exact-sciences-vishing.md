# Abbott傘下Exact Sciences、ShinyHuntersによるビッシング経由の侵害を主張される

- **日付**: 2026-07-21
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/abbott-laboratories-probes-two-cyber-incidents-amid-extortion-claims/)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 続報

## 概要

医療機器大手Abbott Laboratoriesは、傘下のがん診断事業Exact Sciencesのレガシーシステムに対する不正アクセスを調査していることを明らかにした。恐喝グループShinyHuntersが、従業員を狙ったビッシング（音声フィッシング）攻撃によりMicrosoft Entra SSOアカウントを侵害し、大量の医療・個人データを窃取したと主張している。

## 詳細

### 攻撃手法

ShinyHuntersは、Abbott傘下Exact Sciencesの従業員を標的にしたビッシング攻撃を実施し、Microsoft Entra（旧Azure AD）のシングルサインオンアカウントを侵害することで社内レガシーシステムへアクセスしたと主張している。

### 主張されている窃取データ

ShinyHuntersがBleepingComputerに伝えた内容によると、以下のデータを窃取したとされる。
- 社内文書・契約書・顧客情報
- 2200万件超の医師・患者間の診療メモ
- 2000万件超の医療オーダー
- 100万件超の米国社会保障番号（SSN）
- 氏名・住所・生年月日・メールアドレス・電話番号等の個人識別情報

ただし、BleepingComputerはこれらの主張内容を独立して検証できていない。

### 恐喝の状況

ShinyHuntersは7月18日、Abbottに対し7月21日までに応じなければ窃取したとされるデータを公開すると通告した。7月20日時点でデータの公開（リーク）は確認されていない。

### 事業への影響

Abbottは、本件を含む2件のインシデントについて、Exact Sciences事業以外への影響はなく、事業運営・製品供給・製造/検査業務・患者対応能力への影響はないとしている。

### 既存トピックとの関係

ShinyHunters（Mandiant追跡名: UNC6240）は、2026年5〜6月にOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上へ侵入したキャンペーンや、Canvas LMSの二重侵害でも活動が確認されている恐喝グループであり、本件は同一脅威アクターによる新たな標的への攻撃として位置づけられる。

---

## 関連記事

なし
