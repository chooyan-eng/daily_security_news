# 医薬品卸大手McKesson、ShinyHuntersのビッシング攻撃でSalesforce/Snowflake侵害 約5,500万ドルの身代金要求

- **日付**: 2026-08-31
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/mckesson-discloses-breach-after-shinyhunters-claims-patient-data-theft/), [HIPAA Journal](https://www.hipaajournal.com/mckesson-data-breach/), [CyberInsider](https://cyberinsider.com/mckesson-data-breach-exposing-284-million-patients/)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 続報

## 概要

米医薬品卸最大手McKessonが、恐喝グループShinyHuntersによる侵害を確認したと公表した。同グループは従業員へのビッシング（音声フィッシング）でOktaシングルサインオンを突破し、SalesforceおよびSnowflake環境から患者データを含む大量情報を窃取したと主張。8月25日にデータ持ち出しを完了したとして約5,500万ドルの身代金を要求しているが、McKessonは応じていない。

## 詳細

ShinyHuntersは、McKessonの複数の従業員に対してビッシング攻撃を仕掛け、認証情報の窃取または不正なアクセス承認を誘導することで、Okta経由のシングルサインオンアカウントを乗っ取ったと主張している。攻撃者はこれを足がかりに、McKessonのSalesforceおよびSnowflake環境へ侵入し、約4日間（8月21日〜25日）にわたって合計約1TB相当のデータを外部へ持ち出したとされる。

ShinyHuntersが窃取を主張するデータには、氏名・住所・社会保障番号・病歴・ホスピスや終末期疾患の詳細・性的指向・予測的健康評価などを含む患者記録のほか、処方薬の発注・請求・出荷データ、医療従事者の氏名や勤務先情報、医師と患者間のメール内容などが含まれるとされる。同グループは「2億8,400万件の患者データ」を窃取したと主張しているが、これは生データの行数であり、実際のユニークな患者数とは異なる点に注意が必要である。

ShinyHuntersはデータ窃取完了後にMcKessonへ接触し、約5,523万ドル（5,523万6,150ドル）の身代金を要求。McKessonは交渉に応じておらず、詳細な調査を継続しているとしている。今回の手口は、Questel、Lumenis、Carhartt、Sharecare、BOK Financial、Optimizely、ReliaQuestなど、同グループが8月を通じて展開してきたSaaS環境（主にSalesforce）を標的としたビッシング型恐喝キャンペーンと共通しており、その最新の被害事例として位置づけられる。

---

## 関連記事

- [ShinyHunters、アパレル大手Carharttへのランサムウェア攻撃を主張しデータ公開](../articles/2026-08-16-shinyhunters-carhartt-breach.md) - 同一脅威アクターによる同種のビッシング型SaaS恐喝の先行事例
- [米金融大手BOK Financial、ShinyHuntersが恐喝の最終期限を8月24日に設定](../articles/2026-08-24-bok-financial-shinyhunters-ransom-deadline.md) - 同キャンペーンの直近の被害事例
