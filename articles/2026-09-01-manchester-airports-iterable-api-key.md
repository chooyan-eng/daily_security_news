# Manchester Airports Group侵害、原因はクライアント側JavaScriptに露出したIterable APIキーと判明

- **日付**: 2026-09-01
- **出典**: [TechNadu](https://www.technadu.com/manchester-airports-group-data-breach-fulcrumsec-claims-the-theft-of-86-gb-via-exposed-iterable-api-credentials/634395/), [Breached.Company](https://breached.company/manchester-airports-fulcrumsec-iterable-api-key-8-7-million-2026/)
- **トピック**: [Manchester Airports Group データ侵害（2026年8月）](../topics/manchester-airports-group-breach-2026.md)
- **分類**: 続報

## 概要

英Manchester Airports Group（MAG）の顧客データ侵害について、犯行を主張する恐喝集団FulcrumSecが、空港専用のIterable（マーケティング配信サービス）API認証情報がクライアント側JavaScriptに露出していたことを侵入経路として利用したと説明していることが判明した。窃取データには2026年内の今後の渡航予定に関する約20万件の予約情報が含まれるとされ、影響顧客数は870万人に上る。

## 詳細

MAGは2026年8月27日、駐車場・ラウンジ・ファストトラック予約および空港Wi-Fi登録システムを通じて顧客データが窃取されたことを公表し、影響を受けた顧客は870万人に上ると説明していた。多くの顧客はメールアドレスのみの露出とされていたが、恐喝集団FulcrumSecがBleepingComputerに提供したサンプルには、より詳細な個人識別情報や予約履歴が含まれていた。

今回新たに明らかになったのは侵入経路の詳細である。FulcrumSecは、空港専用に発行されたIterable（メール・マーケティング配信サービス）のAPI認証情報が、Webサイトのクライアント側（ブラウザ上で動作する）JavaScriptコード内にそのまま露出していたことを悪用してアクセスを得たと主張している。ブラウザの開発者ツールでコードを閲覧できる利用者であれば誰でもこの認証情報を確認できる状態だったことになる。FulcrumSecは、窃取したデータの中に2026年内の今後の渡航予定に関連する予約情報が約20万件含まれるとしている。

BleepingComputerは、FulcrumSecが提供したサンプルの1件について、実際の旅行者の過去のファストトラック購入履歴・予約時刻・利用ターミナル・支払金額・購入目的などと突き合わせて内容が正確であることを確認したと報じている。MAG側は依然として具体的な主張内容へのコメントを控えているが、クライアント側コードにおける認証情報のハードコーディングという典型的な設計上の不備が、大規模な顧客データ侵害につながった事例として注目される。

---

## 関連記事

- [恐喝集団FulcrumSec、Manchester Airports Groupから86GBのデータ窃取を主張](../articles/2026-08-30-manchester-airports-fulcrumsec-claim.md) - 同一事案の先行報道
