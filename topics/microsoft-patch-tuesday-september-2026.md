# Microsoft Patch Tuesday 2026年9月

## 概要

Microsoftが2026年9月8日に実施した月例セキュリティ更新（Patch Tuesday）。過去最多となる974件の脆弱性を修正し、うち113件がCritical、実際の攻撃で悪用が確認されているゼロデイを2件（CVE-2026-85880: Windows ALPC、CVE-2026-81963: Windows Update Stack）含む。

**同一性の判断に役立つ情報：**
- 対象: Windows、Microsoft Office、SQL Server、Exchange Server、SharePoint、Azure、開発者向けツール
- 修正件数: 974件（Critical 113件、うちRCE 81件、権限昇格20件、情報漏洩2件、セキュリティ機能バイパス1件）
- 実悪用ゼロデイ: CVE-2026-85880（Windows ALPC、ヒープバッファオーバーフロー＋未初期化リソース使用）、CVE-2026-81963（Windows Update Stack、リンク解決不備）
- いずれもローカル権限昇格（SYSTEM権限取得）

## タイムライン

- [2026-09-08 Microsoft、2026年9月のPatch Tuesdayで過去最多974件の脆弱性を修正、実悪用中のゼロデイ2件を含む](../articles/2026-09-08-microsoft-patch-tuesday-september-2026.md)
