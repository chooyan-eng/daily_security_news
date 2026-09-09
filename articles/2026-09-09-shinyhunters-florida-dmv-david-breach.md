# ShinyHunters、フロリダ州DMVの運転者情報データベース「DAVID」侵害を主張 20万件超のデータ流出警告

- **日付**: 2026-09-09
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-hackers-claim-breach-of-florida-david-dmv-database/), [CSO Online](https://www.csoonline.com/article/4220193/shinyhunters-claims-florida-dmv-breach-puts-data-on-the-clock.html)
- **分類**: 関連

## 概要

データ恐喝グループShinyHuntersが、米フロリダ州自動車安全・自動車局（FLHSMV）が運用する運転者・車両情報データベース「DAVID」への侵害を主張し、20万件超の記録を窃取したと公表した。パスワードリセット機能の不備を突いて複数のアカウントを乗っ取ったとされ、9月11日を期限とする恐喝を進めている。

## 詳細

「DAVID」（Driver and Vehicle Information Database）は、フロリダ州の法執行機関や行政職員が運転者情報を照会するために利用する内部システムで、運転免許証の申請情報、写真、署名、住所、車両履歴、保険情報などの機微な記録を保有している。ShinyHuntersはBleepingComputerに対し、パスワードリセット機能の脆弱性を悪用して複数のアカウントを侵害したと説明しており、被害を受けたアカウントの中にはDMV職員に加えFBI捜査官のものも含まれていたと主張している。

攻撃は2026年9月3日に開始されたとみられ、ShinyHuntersは9月7日に自身のリークサイトへ「State of Florida DMV」を掲載。侵害の証拠として、故ジェフリー・エプスタイン氏のDMV記録（住所・登録車両情報を含むスクリーンショット）を公開し、注目を集めた。同グループは9月11日を期限とする「最終警告」を発し、連絡がなければ窃取データを公開すると恐喝している。

本件は、2026年8月以降に本リポジトリで継続的に追跡しているShinyHuntersによるSaaS環境（主にSalesforce）を狙った一連のビッシング・OAuth悪用型恐喝キャンペーンとは侵入経路が異なる（今回はパスワードリセット機能の不備）ものの、同一の脅威アクターによる継続的な標的拡大の一環として位置づけられる。政府系データベースが標的となった点は、これまでの民間企業SaaS環境中心の攻撃パターンからの広がりを示しており、公共部門におけるアカウント復旧機能の堅牢性確認が急務となっている。

---

## 関連記事

- [ShinyHunters、医薬品卸大手McKessonへのビッシング攻撃でSalesforce/Snowflake侵害](../articles/2026-08-31-mckesson-shinyhunters-breach.md) - 同一脅威アクターによる継続的なSaaS/データ恐喝キャンペーンの一環
- [ShinyHunters、アパレル大手Carharttへのランサムウェア攻撃を主張しデータ公開](../articles/2026-08-16-shinyhunters-carhartt-breach.md) - 同一脅威アクターの恐喝手口（リークサイト掲載・期限設定）が共通
