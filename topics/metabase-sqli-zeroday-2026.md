# Metabase 未認証SQLインジェクション ゼロデイ（2026年8月）

## 概要

BIツール「Metabase」のパスワードリセットエンドポイント `POST /api/session/reset_password` に存在する未認証SQLインジェクション（CVSS 10.0、CVE番号未割当）。Metabase Cloud自体が2026年8月3日にこの脆弱性で侵害され、顧客企業のFrameworkとTallyが顧客データ窃取被害を公表した。バージョン58〜63の全リリース（Cloud/セルフホスト）に影響。

**同一性の判断に役立つ情報：**
- 対象製品: Metabase（BI/分析プラットフォーム）
- 脆弱性箇所: POST /api/session/reset_password
- CVSS: 10.0（CVE番号は本記事時点で未割当）
- 影響バージョン: 58〜63（Cloud・セルフホスト両方）
- Metabase Cloud侵害日: 2026年8月3日
- 被害公表企業: Framework, Tally

## タイムライン

- [2026-08-08 Metabaseの未認証SQLインジェクション ゼロデイが実際に悪用、Framework・Tallyが顧客データ窃取を公表](../articles/2026-08-09-metabase-sqli-zeroday-framework-tally.md)
