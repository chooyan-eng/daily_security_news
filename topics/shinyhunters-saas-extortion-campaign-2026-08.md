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
- 新たな標的: セキュリティ企業ReliaQuest（2026年8月23日、リークサイトに掲載）― 同社は「閲覧のみ」の限定的アクセスと反論、顧客データの窃取・公開は確認されず
- ReliaQuest事案の手口: 偽Okta SSOページ＋なりすまし電話によるMFAプッシュ通知の誤承認誘導

## タイムライン

- [2026-08-24 ShinyHunters、セキュリティ企業ReliaQuestへの侵害を主張も同社は限定的な社会工学攻撃と説明](../articles/2026-08-24-shinyhunters-reliaquest-breach-claim.md)
- [2026-08-14 ShinyHunters、ヘルスケア企業Sharecareを標的に Salesforceレコード340万件超が流出か](../articles/2026-08-16-shinyhunters-sharecare-breach.md)
- [2026-08-14 ShinyHunters、アパレル大手Carharttへのランサムウェア攻撃を主張しデータ公開](../articles/2026-08-16-shinyhunters-carhartt-breach.md)
- [2026-08-07 ShinyHunters、仏Questel SASを標的に – Salesforceから2,100万件超のレコードを窃取したと主張](../articles/2026-08-07-shinyhunters-questel-sas-breach.md)
- [2026-08-07 ShinyHunters、医療機器メーカーLumenisも被害に – 110万件超のPII・176GB超の内部データ窃取を主張](../articles/2026-08-07-shinyhunters-lumenis-breach.md)
