# SAP、2026年9月セキュリティパッチデーでCVSS10.0の最高深刻度脆弱性を含む20件を修正

- **日付**: 2026-09-08
- **出典**: [Cyber Security News](https://cybersecuritynews.com/sap-security-updates-september-2026/)
- **トピック**: [SAP 2026年9月セキュリティパッチデー](../topics/sap-security-patch-day-september-2026.md)
- **分類**: 新規

## 概要

SAPは2026年9月のセキュリティパッチデーで、新規19件・既存ノート更新1件の計20件のセキュリティノートを公開した。最も深刻な脆弱性は、SAP Extended Passport Processingに存在するメモリ破損の脆弱性CVE-2026-44756で、CVSSスコアは最高値の10.0と評価されている。修正対象はSAP NetWeaver、SAP S/4HANA、SAP Integration Suite、SAP Commerce Cloudなど主要製品群に及ぶ。

## 詳細

今回のセキュリティパッチデーで最も注目されるのは、CVE-2026-44756として採番されたSAP Extended Passport Processingのメモリ破損脆弱性である。CVSSスコアは脆弱性評価として最高値となる10.0を記録しており、影響を受けるシステムでは深刻な結果を招く可能性がある。メモリ破損系の脆弱性は、悪用の手法次第でリモートコード実行やサービス停止（DoS）につながりやすく、企業の基幹業務システムに直結するSAP製品においては、特に迅速な対応が求められる。

今回の更新は、SAP NetWeaver、SAP Extended Passport Processing、SAP Cloud Application Programming Model、SAP S/4HANA、SAP Integration Suite、SAP Commerce Cloudなど、企業の基幹業務（ERP・EC・統合基盤）を支える主要製品を横断して適用される。これらの製品はいずれも大企業のミッションクリティカルな業務プロセス（会計、サプライチェーン管理、eコマース等）を支えており、パッチ未適用の状態が続くと、業務停止や機密データの窃取につながるリスクが高い。

SAP製品はその性質上、インターネットに直接公開されることは比較的少ないものの、一度侵害されると企業の財務データ・顧客データ・サプライチェーン情報など機微な情報に直結するため、脅威アクターにとって高い価値を持つ標的となっている。過去にもSAP NetWeaverやSAP Commerce Cloudの脆弱性が実際の攻撃キャンペーンで悪用された例があり、SAP環境を運用する組織には、月次パッチデーでの修正内容を速やかに確認し、特にCVSS10.0と評価されたCVE-2026-44756を含む重大な脆弱性から優先的に対応することが推奨される。
