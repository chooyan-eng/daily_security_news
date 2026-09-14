# ShinyHunters、フロリダ州運転免許管理システム「DAVID」侵害を主張 20万件超のレコード窃取か

- **日付**: 2026-09-13
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-hackers-claim-breach-of-florida-david-dmv-database/), [CSO Online](https://www.csoonline.com/article/4220193/shinyhunters-claims-florida-dmv-breach-puts-data-on-the-clock.html), [CyberInsider](https://cyberinsider.com/shinyhunters-claims-breach-of-florida-dmv-threatens-data-leak/)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 関連

## 概要

データ恐喝グループShinyHuntersが、フロリダ州の運転免許・車両情報データベース「DAVID」への侵害を主張し、20万件超のレコードを窃取したと発表した。パスワードリセット機能の脆弱性を悪用して職員やFBI捜査官のアカウントを侵害したとされ、証拠として著名人の記録画像を公開している。

## 詳細

DAVID（Driver and Vehicle Information Database）は、フロリダ州highway安全・自動車局（FLHSMV）が運営し、法執行機関・刑事司法関係者に運転免許・車両情報を提供するシステムである。ShinyHuntersは、パスワードリセット機能の脆弱性を突いてDMV職員やFBI捜査官のものを含む複数アカウントを乗っ取り、レコードIDを連番で列挙してドライバー情報や画像を大量にダウンロードしたと説明している。侵害は2026年9月3日に開始され、脆弱性が修正されアクセスを失うまでに20万件超のレコードを取得したと主張している。

ShinyHuntersは9月7日にリークサイトへ「State of Florida DMV」を掲載し、9月11日を期限とする「最終警告」を通告した。侵害の証拠として、著名な性犯罪者ジェフリー・エプスタインの記録とされるスクリーンショットを公開しており、そこには住所、社会保障番号、生年月日、運転免許証情報、登録車両などが含まれていたとされる。FLHSMVは本稿執筆時点で侵害または不正アクセスの事実を公式には認めていない。

本件は、Salesforce等のSaaS環境を標的としたこれまでのShinyHuntersキャンペーンとは異なり、州政府が運営するWebシステムのパスワードリセット機能という異なる侵入経路を突いた事案だが、同一の脅威アクターによる恐喝の手口（リークサイトでの掲載と期限設定による圧力）は共通しており、ShinyHuntersの攻撃対象が民間SaaS環境から政府系Webシステムへも広がっていることを示す事例といえる。

---

## 関連記事

- [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md) - 同一の恐喝グループによる一連のキャンペーン
