# フロリダ州DMV侵害、原因は警察官個人端末に保存されていた認証情報の窃取と判明

- **日付**: 2026-09-14
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/florida-confirms-dmv-database-breached-via-stolen-police-account/), [Hoodline](https://hoodline.com/2026/09/florida-dmv-breach-traced-to-plant-city-officer-s-password-hackers-claim-200-000-records/), [SOFX](https://www.sofx.com/florida-confirms-david-breach-traced-to-stolen-police-login/)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 続報

## 概要

フロリダ州highway安全・自動車局（FLHSMV）は、運転免許・車両情報データベース「DAVID」への不正アクセスについて調査結果を公表し、原因がプラントシティ警察署の一職員が私用端末に保存していた認証情報の窃取にあったと確認した。データ恐喝グループShinyHuntersが主張していた20万件超のレコード窃取についてFLHSMVはまだ数値を確認していないが、侵害の発生自体は正式に認めた形となる。

## 詳細

FLHSMVは9月4日に国際的なサイバー犯罪組織による侵害を把握したと発表していたが、今回の調査結果により、侵害の原因が特定の一組織のシステム侵害ではなく、プラントシティ警察署職員1名の認証情報が同職員の私用電子端末に不適切に保存されていたことに起因すると判明した。すなわちプラントシティ警察署自体の内部システムが侵害されたわけではなく、業務用ではない個人端末上の認証情報漏えいが発端だったことになる。

DAVID（Driver and Vehicle Information Database）は、フロリダ州の法執行機関・裁判所・許可を受けた政府機関のパートナーが運転免許記録や車両登録情報等の個人情報を照会するために利用するバックエンドの検索システムである。ShinyHuntersは侵害の証拠として、著名な性犯罪者ジェフリー・エプスタインの記録とされるDAVIDのスクリーンショット（社会保障番号、運転免許証番号、旧住所、登録車両などを含む）を公開しており、20万件超のドライバー記録を窃取したと主張しているが、この件数についてFLHSMVは確認していない。

FLHSMVはフロリダ州司法長官室に本件を通報し、フロリダ・デジタルサービス局およびフロリダ州法執行局（FDLE）と連携して対応を進めているという。一職員の私用端末という業務システムの管理外にある経路が、州全体の機微な個人情報データベースへの侵害につながった事例であり、法執行機関等の職員による私用端末での認証情報保存・利用に対する管理強化の必要性を改めて示している。

---

## 関連記事

- [ShinyHunters、フロリダ州運転免許管理システム「DAVID」侵害を主張 20万件超のレコード窃取か](../articles/2026-09-13-shinyhunters-florida-dmv-david-breach.md) - 同一事案の初報
