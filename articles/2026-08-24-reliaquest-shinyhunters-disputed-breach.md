# セキュリティ企業ReliaQuest、ShinyHuntersのリークサイト掲載を否定 – ビッシング攻撃は「未遂」と説明

- **日付**: 2026-08-24
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/reliaquest-confirms-failed-data-theft-attack-after-shinyhunters-breach/) / [The Register](https://www.theregister.com/cyber-crime/2026/08/24/shinyhunters-and-reliaquest-trade-blows-over-claimed-breach/5291702)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 続報

## 概要

データ恐喝グループShinyHuntersが2026年8月23日、セキュリティ企業ReliaQuestを新たな被害者としてリークサイトに掲載した。しかしReliaQuestは、8月22日に発生したソーシャルエンジニアリング攻撃を確認したものの、閲覧限定権限を持つ1つのID情報が一時的に露出した以外に自社のアプリケーション・システム・顧客データへの侵入は確認されておらず、攻撃は失敗に終わったと反論している。

## 詳細

### 攻撃の経緯

2026年8月22日、攻撃者はReliaQuestのセキュリティチームメンバーを装い、複数の従業員に電話をかけるビッシング（音声フィッシング）攻撃を実行した。攻撃者は、コンテンツデリバリーネットワーク（CDN）の背後に構築した偽のReliaQuestシングルサインオン（SSO）ページへ従業員を誘導し、認証情報を入力させようと試みた。

### ReliaQuest側の説明

ReliaQuestは調査の結果、この攻撃によって閲覧限定（view-only）権限を持つ1件のID情報が一時的に露出したのみであり、同社のアプリケーション・システム・顧客データへの不正アクセスは確認されなかったと公表した。同社はこれを「失敗した攻撃」と位置づけている。

### ShinyHunters側の主張との相違

一方、ShinyHuntersは8月23日にReliaQuestを自社のリークサイトへ新たな被害者として掲載しており、両者の主張には食い違いが見られる。この種の「侵害の有無・範囲を巡る攻撃者と被害企業の対立」は、ShinyHuntersが関与する複数の案件で共通して見られるパターンである。

### 背景：ShinyHuntersの活動傾向

ShinyHuntersは2026年8月を通じて、ビッシングやOAuth連携の悪用によりSaaS環境（主にSalesforce）から情報を窃取し、リークサイトでの公開を材料に金銭を要求する二重恐喝型のキャンペーンを継続している。セキュリティ企業自体が標的となった今回の事案は、防御側の組織であっても同種のソーシャルエンジニアリング攻撃の対象から外れないことを改めて示すものとなった。

---

## 関連記事

- [2026-08-16 ShinyHunters、ヘルスケア企業Sharecareを標的に Salesforceレコード340万件超が流出か](../articles/2026-08-16-shinyhunters-sharecare-breach.md) - 同一脅威アクターによる別事案
