# ShinyHunters SaaS恐喝キャンペーン（2026年8月）

## 概要

データ恐喝グループShinyHuntersが2026年8月初旬、複数企業のSaaS環境（主にSalesforce）を標的にリークサイトへ掲載した一連のキャンペーン。フランスの知財サービス大手Questel SAS（Salesforceから2,100万件超のレコード・147GB超の内部データ窃取を主張、8月2日公表）、医療機器メーカーLumenis Ltd.（110万件超のレコード・176GB超のデータ窃取を主張）などが被害者として名指しされた。暗号化被害の証拠はなく、データ窃取と公開の脅迫による二重恐喝型。MicrosoftはShinyHunters関連の脅威アクターがビッシングやOAuth連携の悪用を通じてSaaSアプリを狙っていると報告している。2026年6月のKlue発「Icarus」キャンペーンとは別の攻撃・攻撃者。

**同一性の判断に役立つ情報：**
- 脅威アクター: ShinyHunters
- 手口: SaaS（主にSalesforce）環境からのデータ窃取＋リークサイトでの公開脅迫（二重恐喝）
- 想定される侵入手口: ボイスフィッシング（ビッシング）、OAuth連携の悪用
- 被害組織: Questel SAS（仏、8月2日公表）、Lumenis Ltd.（イスラエル）、Alcon 等
- 関連するが別キャンペーン: Klue発「Icarus」OAuthキャンペーン（2026年6月、別の攻撃者）
- 脅威アクター: ShinyHunters（データ恐喝グループ）
- 手口: ランサムウェア／データ窃取＋恐喝（リークサイトでのデータ公開）
- 被害企業: Carhartt, Inc.（2026年8月13日攻撃、8月14日公表）、Sharecare, Inc.（2026年8月13日攻撃、8月14日公表）
- Carharttの身代金要求額: 330万ドル（交渉不成立によりデータ公開）
- Sharecareの被害規模: Salesforceレコード340万件超、社内データ28GB超
- 関連の可能性: 2026年に相次ぐSalesforce連携アプリのOAuthトークン窃取型データ恐喝キャンペーンとの関連が疑われる
- 被害企業（追加）: BOK Financial（米金融、2026年8月22日攻撃主張・8月24日を支払い最終期限に設定）
- セキュリティ企業自体が標的になった事例: ReliaQuest（2026年8月22日ビッシング攻撃、8月23日リークサイト掲載）。ReliaQuest側は閲覧限定ID1件の一時露出のみで侵害は未遂と主張し、ShinyHuntersの掲載内容と食い違いあり
- ReliaQuest事案の手口: 偽Okta SSOページ＋なりすまし電話によるMFAプッシュ通知の誤承認誘導

- 被害企業（追加）: Optimizely（米アドテク大手、2026年2月11日接触・8月下旬公表、ビッシング経由で基本的な事業連絡先情報を窃取）
- Carharttの実被害規模検証: 第三者研究者による検証で実際の影響アカウントは1,293万3,413件と判明（ShinyHunters主張の約半分、合成データの混入が判明）
- 被害企業（追加）: McKesson Corporation（米医薬品卸最大手、2026年8月21〜25日にビッシング経由でOktaアカウントを乗っ取りSalesforce/Snowflakeから約1TB窃取、身代金要求額 約5,523万ドル）

## タイムライン

- [2026-08-31 医薬品卸大手McKesson、ShinyHuntersのビッシング攻撃でSalesforce/Snowflake侵害 約5,500万ドルの身代金要求](../articles/2026-08-31-mckesson-shinyhunters-breach.md)
- [2026-08-27 アドテク大手Optimizely、ビッシング攻撃によるデータ侵害を公表 ― ShinyHuntersの関与か](../articles/2026-08-27-optimizely-vishing-data-breach.md)
- [2026-08-27 Carharttのデータ侵害、実被害は1,290万件超とShinyHunters主張の約半分と判明](../articles/2026-08-27-carhartt-breach-scope-confirmed-129m.md)
- [2026-08-26 ShinyHunters、セキュリティ企業ReliaQuestへのビッシング攻撃を主張も同社は「被害は限定的」と反論](../articles/2026-08-26-shinyhunters-reliaquest-social-engineering.md)
- [2026-08-24 米金融大手BOK Financial、ShinyHuntersが恐喝の最終期限を8月24日に設定](../articles/2026-08-24-bok-financial-shinyhunters-ransom-deadline.md)
- [2026-08-24 セキュリティ企業ReliaQuest、ShinyHuntersのリークサイト掲載を否定 – ビッシング攻撃は「未遂」と説明](../articles/2026-08-24-reliaquest-shinyhunters-disputed-breach.md)
- [2026-08-24 ShinyHunters、セキュリティ企業ReliaQuestへの侵害を主張も同社は限定的な社会工学攻撃と説明](../articles/2026-08-24-shinyhunters-reliaquest-breach-claim.md)
- [2026-08-14 ShinyHunters、ヘルスケア企業Sharecareを標的に Salesforceレコード340万件超が流出か](../articles/2026-08-16-shinyhunters-sharecare-breach.md)
- [2026-08-14 ShinyHunters、アパレル大手Carharttへのランサムウェア攻撃を主張しデータ公開](../articles/2026-08-16-shinyhunters-carhartt-breach.md)
- [2026-08-07 ShinyHunters、仏Questel SASを標的に – Salesforceから2,100万件超のレコードを窃取したと主張](../articles/2026-08-07-shinyhunters-questel-sas-breach.md)
- [2026-08-07 ShinyHunters、医療機器メーカーLumenisも被害に – 110万件超のPII・176GB超の内部データ窃取を主張](../articles/2026-08-07-shinyhunters-lumenis-breach.md)
