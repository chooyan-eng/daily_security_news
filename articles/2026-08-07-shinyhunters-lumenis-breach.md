# ShinyHunters、医療機器メーカーLumenisも被害に – 110万件超のPII・176GB超の内部データ窃取を主張

- **日付**: 2026-08-07
- **出典**: [BreachNews](https://breachnews.com/breaches/shinyhunters-lists-questel-alcon-and-lumenis-on-leak-site-with-new-extortion-claims/)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 続報

## 概要

ShinyHuntersはQuestel SASと同時期に、医療機器メーカーLumenis Ltd.もリークサイトに掲載した。顧客・従業員のPIIを含む110万件超のレコードと176GB超の内部企業データを窃取したと主張しており、Questel SASと並行して展開された同グループのSaaS環境を標的とした恐喝キャンペーンの一部と位置付けられる。

## 詳細

### 概要

ShinyHuntersは2026年8月2日頃、イスラエルに拠点を置く医療機器メーカーLumenis Ltd.をランサムウェア／データ恐喝の被害者としてリークサイトに掲載した。同グループは顧客および従業員のPIIを含む110万件超のレコードと、176GB超の内部企業データを窃取したと主張している。

同時期にShinyHuntersはQuestel SAS、Alconなど複数の企業を同様の手口でリークサイトに掲載しており、SaaS環境（特にSalesforceなどのCRM）を標的とした一連の恐喝キャンペーンの一環とみられる。

### Questel SAS事案との関連性

Questel SASの事案と同じタイミングで公表され、同一の脅威アクター（ShinyHunters）による攻撃であることから、本トピックでは一連のSaaS恐喝キャンペーンとして扱う。個別の初期侵入経路の詳細は現時点で明らかにされていないが、Microsoftが報告するOAuth悪用・ビッシングを組み合わせた手口との関連が推測される。

### 対策

Questel SAS事案の対策と同様、SaaS連携アプリ・OAuthトークンの棚卸し、異常なデータエクスポートの監視、ボイスフィッシング対策の強化が推奨される。

---

## 関連記事

- [ShinyHunters、仏Questel SASを標的に – Salesforceから2,100万件超のレコードを窃取したと主張](../articles/2026-08-07-shinyhunters-questel-sas-breach.md) - 同一脅威アクターによる並行キャンペーン
