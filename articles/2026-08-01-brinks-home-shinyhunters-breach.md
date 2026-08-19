# ShinyHunters、住宅向けセキュリティ大手Brinks Homeへの侵害を主張——Microsoft Entraビッシングで初期侵入、490万件超のSalesforceデータ窃取を主張

- **日付**: 2026-08-01
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-brinks-home-breach-threatens-to-leak-stolen-data/)
- **トピック**: [Brinks Home ShinyHuntersビッシング侵害（2026年7月）](../topics/brinks-home-shinyhunters-breach-2026.md)
- **分類**: 新規

## 概要

住宅向けセキュリティ企業Brinks Homeが、システムへの侵害を公表した。恐喝グループShinyHuntersは、Microsoft Entraを標的としたビッシング（音声フィッシング）により7月13日に初期侵入したと主張し、490万件超のSalesforceデータを窃取したとしてデータ漏洩サイトで「最終警告」を出している。

## 詳細

ShinyHuntersの主張によれば、攻撃者は7月13日、従業員に電話をかけMicrosoft Entraの認証・登録プロセスを完了させるよう仕向ける「ビッシング」攻撃によって、対象アカウントへのアクセス権を取得した。Brinks Home側は7月20日に侵害を検知し、直ちにインシデントレスポンス手続きを開始したとしている。

ShinyHuntersは、SalesforceのContactsオブジェクトから110万件超の顧客データ行、従業員PII（氏名・メールアドレス・役職・電話番号）4,000件超、さらにBrinks CareのCrestaインスタンスから380万件超のカスタマーサポートチャットログを窃取したと主張している。BleepingComputerは窃取データの内容自体は確認できておらず、ShinyHuntersの主張の正確性は未検証としている。

Brinks HomeのCEO William Niles氏は、フォレンジック専門家と連携して対応にあたっていると述べ、警報監視システムなど本業のセキュリティサービス機能への影響はなかったとしている。ShinyHuntersは7月27日、Brinks Homeに加えてErnst & Young（EY）、RingCentralについてもデータ漏洩サイトに「最終警告」を掲載し、7月30日から31日にかけての交渉期限を設定してデータ公開を予告している。SalesforceのCRMデータを標的とするソーシャルエンジニアリング型の侵害が同時多発的に発生している点が特徴で、Salesforce連携を持つ組織は多要素認証やEntra認証フローの見直しが求められる。
