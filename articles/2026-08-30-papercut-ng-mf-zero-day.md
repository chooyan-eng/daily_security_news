# PaperCut NG/MF に未認証の重大ゼロデイ脆弱性、実際の顧客環境で悪用を確認

- **日付**: 2026-08-30
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/08/27/papercut-ng-mf-vulnerability-attack/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/papercut-releases-second-emergency-patch-for-exploited-flaws/), [SecurityWeek](https://www.securityweek.com/papercut-releases-emergency-patch-for-exploited-zero-day/)
- **トピック**: [PaperCut NG/MF ゼロデイ脆弱性 CVE-2026-82078／CVE-2026-81578（2026年8月）](../topics/papercut-ng-mf-zero-day-2026.md)
- **分類**: 新規

## 概要

印刷管理ソフトウェアPaperCut NG／MFの全バージョンに影響する未認証の重大脆弱性2件（CVE-2026-82078、CVE-2026-81578）が実環境で悪用されていることが判明した。PaperCutは8月27日に確認済みの顧客インシデントがあるとして緊急アドバイザリを公開し、28日と30日の2度にわたり緊急パッチをリリースした。

## 詳細

PaperCut Softwareは2026年8月27日、自社の印刷管理製品PaperCut NGおよびPaperCut MFの全バージョンに影響する2件のゼロデイ脆弱性を公表した。CVSSスコア9.4のCVE-2026-82078は、PaperCutアプリケーションのデータベース接続ユーティリティにおける安全でない動的クラスロード欠陥で、任意のJavaコードの実行につながる可能性がある。CVSSスコア8.8のCVE-2026-81578は、Web管理インターフェースにおけるアクセス制御の不備で、未認証のリモート攻撃者がシステム設定を変更できる。両脆弱性を連鎖させることで、未認証のリモートコード実行（RCE）が可能になるとされる。

PaperCutは「確認済みの顧客インシデント」があるとして、実際の悪用が既に発生していることを認めた。同社は2026年8月28日午前2時10分（オーストラリア東部標準時）に、バージョン25および26向けの緊急パッチを最初にリリースし、同日中にバージョン24向けのパッチも公開した。しかしその後、初回パッチでは緩和が不十分なケースが確認されたため、8月30日に第2弾の緊急パッチを追加でリリースしている。

PaperCutは、インターネットに公開されているPaperCut NG／MFのアプリケーションサーバーについて、信頼できるIPアドレスからのアクセスのみに制限するよう強く推奨している。PaperCutをめぐっては過去にもCVE-2023-27350など重大な未認証RCE脆弱性が悪用され、ランサムウェア攻撃の侵入口として利用された前例があり、教育機関や自治体など印刷インフラを広く利用する組織にとって深刻なリスクとなる。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
