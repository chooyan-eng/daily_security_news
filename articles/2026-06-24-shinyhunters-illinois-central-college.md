# ShinyHunters、イリノイ・セントラル・カレッジにランサムウェア攻撃：教育機関を継続して標的に

- **日付**: 2026-06-24
- **出典**: [SharkStriker - June 2026 Data Breaches](https://sharkstriker.com/blog/june-2026-data-breaches/)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 関連

## 概要

ShinyHunters ランサムウェアグループが、米国イリノイ州のイリノイ・セントラル・カレッジ（Illinois Central College）を新たな標的としてランサムウェア攻撃を実施。2026年6月23日に侵害が主張された。同グループは Oracle PeopleSoft ゼロデイを悪用した大学侵害キャンペーン（CVE-2026-35273）に続き、引き続き教育機関を重点ターゲットとしている。

## 詳細

### 事案の概要

ShinyHunters は 2026年6月23日、イリノイ・セントラル・カレッジへの侵害を主張した。同グループは既に Oracle PeopleSoft ゼロデイを悪用した大規模な大学ハッキングキャンペーン（2026年5月27日〜6月9日）を展開しており、今回はその延長線上または独立した新たな攻撃と見られる。

### イリノイ・セントラル・カレッジについて

イリノイ州イースト・ピオリアに本拠を置くコミュニティカレッジで、学生・教職員の個人情報、成績データ、財務情報等を保持している。大学・カレッジは一般的にサイバーセキュリティの投資が低い傾向があり、攻撃者にとって侵入しやすいターゲットとなりやすい。

### ShinyHunters の教育機関への攻撃パターン

ShinyHunters は Oracle PeopleSoft キャンペーンで大学を中心に100社以上に侵入した実績を持つ。教育機関への攻撃は以下の理由から継続している：

1. **多量の個人情報**: 学生・教職員の大量な個人情報・財務情報を保有
2. **セキュリティ投資不足**: 企業に比べてセキュリティ予算が限られている
3. **ソフトウェアの多様性**: ERP（PeopleSoft 等）から各種 SaaS まで多様なシステムを利用
4. **支払い能力**: 学生データを盾にした恐喝が機能しやすい

### Oracle PeopleSoft キャンペーンとの関連

今回の攻撃が Oracle PeopleSoft（CVE-2026-35273）を悪用したものかは不明だが、ShinyHunters が教育機関への侵害手法を継続的に洗練させており、同一の TTP（戦術・技術・手順）が使用された可能性がある。

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 同一脅威アクターによる大学侵害キャンペーンの起点
- [ShinyHunters、Canvas LMS（Instructure）を二度侵害：2億7500万件の学生・教職員データを要求](../articles/2026-06-16-shinyhunters-canvas-lms-breach.md) - 同一脅威アクターによる教育機関への別途侵害
