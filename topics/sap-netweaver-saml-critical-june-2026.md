# SAP NetWeaver クリティカル脆弱性（2026年6月）

## 概要

2026年6月のパッチで公開された SAP NetWeaver AS ABAP および関連製品の複数のクリティカル脆弱性。CVE-2026-44748（CVSS 9.9）は SAML 認証における XML 署名ラッピング（XSW）攻撃を可能にし、未認証で任意ユーザーとして SAP システムにログイン可能。CVE-2026-27671（CVSS 9.8）はメモリ破壊、CVE-2026-22732（CVSS 9.1）は Spring Security の脆弱性を SAP Commerce Cloud に持ち込む。SAP NetWeaver は世界の大企業・政府機関の ERP/基幹業務を担うため影響範囲が広大。

**同一性の判断に役立つ情報：**
- 主要 CVE: CVE-2026-44748（CVSS 9.9）、CVE-2026-27671（CVSS 9.8）、CVE-2026-22732（CVSS 9.1）
- 対象製品: SAP NetWeaver AS ABAP、SAP Application Server ABAP、SAP Commerce Cloud、SAP Data Hub
- 攻撃タイプ: CVE-2026-44748 は XML 署名ラッピング（XSW）、CVE-2026-27671 はメモリ破壊
- パッチ公開: 2026年6月

## タイムライン

- [2026-06-21 SAP NetWeaver SAML 認証バイパス CVE-2026-44748（CVSS 9.9）— XML 署名ラッピング攻撃](../articles/2026-06-21-sap-netweaver-saml-cve-2026-44748.md)
