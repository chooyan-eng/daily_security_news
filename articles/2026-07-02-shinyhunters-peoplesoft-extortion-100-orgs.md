# ShinyHunters、Oracle PeopleSoftゼロデイ（CVE-2026-35273）で100組織超から金銭恐喝を継続

- **日付**: 2026-07-01
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/shinyhunters-exploits-oracle-peoplesoft.html) / [CyberScoop](https://cyberscoop.com/oracle-peoplesoft-zero-day-vulnerability-shinyhunters-extortion/)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 続報

## 概要

金銭目的ハッカー集団ShinyHuntersが、Oracle PeopleSoftのゼロデイ脆弱性（CVE-2026-35273）を悪用し、高等教育機関を中心に100組織・300インスタンス超からデータを窃取したキャンペーンについて、被害組織への恐喝連絡がまだ始まったばかりであることが判明した。今後さらに被害組織名が公表される見込み。

## 詳細

### 被害状況のアップデート

既存トピックで報告済みのCVE-2026-35273（CVSS 9.8、Oracle PeopleSoft Enterprise PeopleTools の無認証RCE）を悪用したキャンペーンについて、被害組織が100組織・300インスタンス超に及ぶことが改めて確認された。攻撃は少なくとも2026年5月27日から確認されている。

確認済みの被害者としてノッティンガム大学（英国）があり、約50万人分の学生記録を含む40GB超のデータが既に公開されている。被害組織の約68%が高等教育機関で、大半が米国の組織。

### 攻撃手法

ShinyHuntersはBleepingComputerに対し、既知の脆弱性と複数のゼロデイを組み合わせた「ガジェットチェーン」を用いてPeopleSoftサーバーを攻撃したと説明している。

### 恐喝の状況

被害組織への金銭恐喝の連絡は現時点でまだ始まったばかりとされ、今後数週間から数ヶ月にわたって追加の被害組織名が公表される可能性が高い。

### 攻撃者背景

ShinyHunters（Mandiantの追跡名: UNC6240）は、Scattered Spider・LAPSUS$との合流により形成された「Scattered LAPSUS$ Hunters」連合の一角とされ、2025年後半からのSalesforce/Gainsight/Salesloft-Drift恐喝キャンペーンの延長線上で新たな標的（Oracle PeopleSoft）に攻撃対象を広げている。

---

## 関連記事

なし（続報）
