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

## タイムライン

- [2026-08-10 Metabase未認証SQLインジェクションゼロデイが悪用、Framework・Tallyの顧客データが流出](../articles/2026-08-10-metabase-sqli-zeroday.md)
- [2026-08-08 Metabaseの未認証SQLインジェクション ゼロデイが実際に悪用、Framework・Tallyが顧客データ窃取を公表](../articles/2026-08-09-metabase-sqli-zeroday-framework-tally.md)
