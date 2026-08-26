# ShinyHunters、セキュリティ企業ReliaQuestへのビッシング攻撃を主張も同社は「被害は限定的」と反論

- **日付**: 2026-08-26
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/08/25/reliaquest-breach-social-engineering/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/reliaquest-confirms-failed-data-theft-attack-after-shinyhunters-breach/), [The Register](https://www.theregister.com/cyber-crime/2026/08/24/shinyhunters-and-reliaquest-trade-blows-over-claimed-breach/5291702)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 続報

## 概要

データ恐喝グループShinyHuntersが、セキュリティ企業ReliaQuestのリークサイト掲載と攻撃成功を主張。しかしReliaQuestは、従業員1名がビッシング（音声フィッシング）攻撃に応じてしまったものの、デバイス信頼制御により被害はIDダッシュボードの一時的な閲覧権限のみに限定され、顧客データやシステムへの侵入は確認されていないと反論した。

## 詳細

ReliaQuestは、自社セキュリティチームを装った攻撃者からのビッシング攻撃を受けた事実を認めた。攻撃者は実在する自社セキュリティ担当者の氏名を語って従業員に電話をかけ、なりすましドメイン「reliaquest[.]claims」上に用意した偽のシングルサインオン（SSO）ページへ誘導した。

このうち1名の従業員が騙され、認証情報を入力しMFAプッシュ通知を承認してしまったことで、攻撃者はReliaQuestのID管理ダッシュボードへの一時的な閲覧専用アクセス権を取得した。ただし、その後のアプリケーションへのアクセス試行はデバイス信頼制御によりブロックされ、システム・アプリケーション・顧客データのいずれにもアクセスされなかったと同社は説明している。侵害検知後、該当セッションの強制終了、パスワードの失効、トークンのリセットを実施済みという。

一方、恐喝グループShinyHuntersは自身のリークサイトにReliaQuest, LLCを掲載し、スクリーンショットを公開して大きな戦果を主張した。しかし公開された資料からは、同グループが主張するような顧客アプリケーションやデータへのアクセスを実際に得たことを示す証拠は確認されていない。攻撃が発生した8月22日は、ReliaQuestが「.claims」ドメインを使ったShinyHuntersの類似ソーシャルエンジニアリングキャンペーンについて注意喚起を公表した直後というタイミングだった。

本件は、セキュリティ企業自身も標的となり得ることを示す事例であるとともに、ShinyHuntersによる誇張された恐喝主張と実際の侵害範囲との乖離を検証する重要性を改めて示している。

---

## 関連記事

- [ShinyHunters、ヘルスケア企業Sharecareを標的に Salesforceレコード340万件超が流出か](../articles/2026-08-16-shinyhunters-sharecare-breach.md) - 同一脅威アクターによるSaaS環境を狙った一連の恐喝キャンペーンの一環
