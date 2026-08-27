# ShinyHunters、セキュリティ企業ReliaQuestへの侵害を主張も同社は限定的な社会工学攻撃と説明

- **日付**: 2026-08-24
- **出典**: [The Register](https://www.theregister.com/cyber-crime/2026/08/24/shinyhunters-and-reliaquest-trade-blows-over-claimed-breach/5291702) / [BleepingComputer](https://www.bleepingcomputer.com/news/security/reliaquest-confirms-failed-data-theft-attack-after-shinyhunters-breach/) / [Cybernews](https://cybernews.com/security/shinyhunters-reliaquest-breach-okta/)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 続報

## 概要

データ恐喝グループShinyHuntersは2026年8月23日、米セキュリティ企業ReliaQuestを自社のリークサイトに掲載し、同社のOkta管理画面へのアクセスを示すスクリーンショットを公開した。ReliaQuestは8月22日に社会工学攻撃を受けたことを認めたものの、実際の侵害は1つのIDが一時的に露出した程度の「失敗した攻撃」であり、顧客データやシステムへのアクセスはなかったと反論している。

## 詳細

### 発端

ReliaQuestは8月17日、ShinyHuntersが偽ドメインを大量登録して社会工学攻撃を仕掛けている広範なキャンペーンについてX（旧Twitter）で注意喚起の投稿を行った。これに対しShinyHunters側のアカウント「@odysseusgroup」が、ReliaQuest自身のOkta管理画面と見られるスクリーンショットを添えて「誰が誰を狩っているのか（Who's hunting who?）」と皮肉る返信を行い、対立が表面化した。

### 攻撃の技術的手口

ShinyHuntersは、コンテンツデリバリーネットワーク（CDN）の背後にホストした偽のOkta SSOログインページを用意し、なりすまし電話でReliaQuestの従業員を欺いて多要素認証（MFA）のプッシュ通知を承認させる手口を用いたとされる。これによりID管理画面へのビュー専用アクセス権を持つ単一のセッションを取得したものの、ReliaQuestは異常を検知し速やかにアクセスを遮断したという。

### 双方の主張の相違

ShinyHuntersは侵害の成立を主張し証拠としてスクリーンショットを提示したが、盗んだ顧客データそのものは一切公開していない。セキュリティ企業SOCRadarも、検証済みのデータサンプル、身代金要求、顧客への実害を示す証拠は確認できなかったとしている。一方ReliaQuestは、内部監査の結果としてアクセスは「閲覧のみ」に限定され、同社のアプリケーションやシステム、顧客データには一切到達していないと説明している。

### 位置づけ

本件は、ShinyHuntersがビッシング（音声フィッシング）やOAuth悪用によりSaaS環境を標的とする一連のキャンペーンの最新の展開である。標的がセキュリティベンダー自身であった点、および攻撃側・被害側の双方が公開の場で応酬を行った点で、従来のQuestel SASやLumenis、Sharecare、Carharttといった事業会社を狙った事例とは性質が異なる。セキュリティベンダーであっても、なりすまし電話によるMFAプッシュ通知の誤承認という古典的な弱点は変わらず有効であることを改めて示した事案である。
