# Kodak、ShinyHuntersによる220万件の顧客情報窃取を確認 - データ公開期限超過

- **日付**: 2026-06-19
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/kodak-confirms-data-breach-claimed-by-shinyhunters-extortion-gang/)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 関連

## 概要

ShinyHuntersグループが写真機器・印刷企業のKodakから220万件以上の顧客PII（個人情報）と社内データを窃取したと主張。Kodakは侵害の事実を認めたが規模の詳細は不明のまま。6月18日のデータ公開期限を超過したが、データサンプルの公開はなく恐喝戦術の一環との見方がある。

## 詳細

### 侵害の発覚

2026年6月15日、ShinyHuntersグループがダークウェブのリークサイトにKodakを掲載した。グループは220万件以上の記録を窃取したと主張し、6月18日を最終警告の期限として設定した。期限到達後、「追加の問題」（additional "annoying (digital) problems"）を予告した。

### Kodakの公式回答

Kodakは「権限のない第三者が限られた量の会社データに一時的にアクセスした」ことを認めた。ただし、ShinyHuntersが主張する220万件という規模は独自に確認していないとしている。調査継続中であり、外部サイバーセキュリティ専門家および法執行機関と協力して対応している。

### 証拠の信憑性

今回の侵害でShinyHuntersはデータサンプルや証拠を公開していない。これはShinyHuntersが過去に使用してきた圧力戦術であり、実際の被害規模とは乖離している可能性もある。しかしKodak自身が侵害を認めている点は注目に値する。

### ShinyHuntersの最近の活動との関連

ShinyHuntersは2026年に複数の大規模侵害キャンペーンを展開している。本件はOracle PeopleSoft（CVE-2026-35273）への攻撃キャンペーン（UNC6240）とは直接の関連は確認されていないが、同一のグループによる継続的な恐喝活動の一環とみられる。また2026年4月には、Oracle PeopleSoftで使用した手法と類似した形でCanvas LMS（Instructure）から2億7500万件のデータを窃取したとも主張している。

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 同一脅威アクターによる大学等への大規模攻撃
- [ShinyHunters、Canvas LMS（Instructure）を二度侵害：2億7500万件の学生・教職員データを要求](../articles/2026-06-16-shinyhunters-canvas-lms-breach.md) - 同一脅威アクターによる教育機関への攻撃
