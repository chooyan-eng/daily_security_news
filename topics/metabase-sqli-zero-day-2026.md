# Metabase 認証不要SQLi ゼロデイ（CVSS 10.0）実悪用（2026年8月）

## 概要

BIツール Metabase（v1.58以降）の未認証エンドポイント `POST /api/session/reset_password` に存在するSQLインジェクションのゼロデイ脆弱性（CVSS 10.0、CVE番号未採番）が実際の攻撃で悪用され、攻撃者が管理者権限を奪取し接続先データベースの認証情報や顧客データを窃取する被害が複数の組織で発生している。

**同一性の判断に役立つ情報：**
- 対象製品: Metabase（BIツール） v1.58以降
- 脆弱性: 未認証SQLインジェクション、CVSS 10.0、CVE番号未採番
- 悪用エンドポイント: `POST /api/session/reset_password`
- 安全な最小バージョン: 0.58.24 / 0.59.21 / 0.60.17 / 0.61.11 / 0.62.9 / 0.63.5
- 確認済み被害組織: n8n（顧客136件）、Framework、Kilo Code 等

## タイムライン

- [2026-08-11 n8n・Framework 等がMetabaseゼロデイ経由で顧客情報漏洩を確認](../articles/2026-08-11-n8n-framework-metabase-breach.md)
- [2026-08-11 Metabase 認証不要SQLインジェクション・ゼロデイ（CVSS 10.0）が実悪用、管理者権限奪取が可能に](../articles/2026-08-11-metabase-sqli-zero-day.md)
