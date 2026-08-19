# Metabase SQLインジェクションゼロデイ（CVSS 10.0、2026年8月）

## 概要

オープンソースBIツールMetabase（1.58以降）に存在する未認証SQLインジェクションの脆弱性（CVSS 10.0、開示時点で正式CVE番号未採番）がゼロデイ攻撃で悪用され、Framework・Tallyなど複数企業のMetabaseインスタンスが侵害され顧客データが窃取された事案。Metabase Cloudはパッチ済みだが、自己ホスト型インスタンスは管理者による手動アップデートが必要。

**同一性の判断に役立つ情報：**
- 対象製品: Metabase（オープンソースBIツール）バージョン1.58以降
- 脆弱性種別: 未認証SQLインジェクション → 管理者権限奪取（CVSS 10.0）
- 悪用時期: 2026年8月3日（Framework・Tallyともに）
- 被害企業: Framework（PC自作キットメーカー）、Tally（オンラインフォームビルダー）
- 漏洩データ: 氏名・メールアドレス・住所・電話番号（Tallyはパスワードハッシュも含む）
- Metabase Cloud: パッチ適用済み／自己ホスト型: 手動アップデート必要
- 対象製品: Metabase（BI/分析プラットフォーム）
- 脆弱性箇所: POST /api/session/reset_password
- CVSS: 10.0（CVE番号は本記事時点で未割当）
- 影響バージョン: 58〜63（Cloud・セルフホスト両方）
- Metabase Cloud侵害日: 2026年8月3日
- 被害公表企業: Framework, Tally
- 対象製品: Metabase（BIツール） v1.58以降
- 脆弱性: 未認証SQLインジェクション、CVSS 10.0、CVE番号未採番
- 悪用エンドポイント: `POST /api/session/reset_password`
- 安全な最小バージョン: 0.58.24 / 0.59.21 / 0.60.17 / 0.61.11 / 0.62.9 / 0.63.5
- 確認済み被害組織: n8n（顧客136件）、Framework、Kilo Code 等
- CVE: CVE-2026-72898（CVSS 10.0、パスワードリセットエンドポイントのSQLi）
- 影響バージョン: 自己ホスト型 Metabase 0.58〜0.63.4
- 公開日: 2026-08-06、CISA KEV追加日: 2026-08-11
- 既知の被害: 開示時点で確認された侵害企業 5社以上
- CVE: CVE-2026-72898
- 種別: 未認証SQLインジェクション（CWE-89）→ 管理者権限奪取
- CVSS: 10.0
- 対象バージョン: 自己ホスト型 Metabase 0.58〜0.63.4（Enterprise 1.x系列含む）
- 悪用起点: パスワードリセットエンドポイント
- CISA KEV登録日: 2026年8月11日

## タイムライン

- [2026-08-17 Metabase CVE-2026-72898：未認証SQLインジェクションで管理者権限奪取、CISA KEVに追加](../articles/2026-08-17-metabase-cve-2026-72898-sqli-kev.md)
- [2026-08-12 Metabase SQL インジェクション（CVE-2026-72898、CVSS 10.0）で少なくとも5社が侵害 – 接続先データベースの認証情報が根こそぎ流出](../articles/2026-08-12-metabase-cve-2026-72898-sqli.md)
- [2026-08-11 n8n・Framework 等がMetabaseゼロデイ経由で顧客情報漏洩を確認](../articles/2026-08-11-n8n-framework-metabase-breach.md)
- [2026-08-11 Metabase 認証不要SQLインジェクション・ゼロデイ（CVSS 10.0）が実悪用、管理者権限奪取が可能に](../articles/2026-08-11-metabase-sqli-zero-day.md)
- [2026-08-10 Metabase未認証SQLインジェクションゼロデイが悪用、Framework・Tallyの顧客データが流出](../articles/2026-08-10-metabase-sqli-zeroday.md)
- [2026-08-08 Metabaseの未認証SQLインジェクション ゼロデイが実際に悪用、Framework・Tallyが顧客データ窃取を公表](../articles/2026-08-09-metabase-sqli-zeroday-framework-tally.md)
