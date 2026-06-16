# ServiceNow APIインシデント2026

## 概要

2026年6月2〜3日に発生したServiceNowの認証バイパスAPIインシデント。Scripted REST Resourceの設定ミスにより特定エンドポイント（/api/now/related_list_edit/create）が認証不要でアクセス可能になり、ITチケット・従業員情報・内部ドキュメント・認証情報などの顧客データが露出した。ServiceNowは6月5日にセキュリティアップデートで修正し、影響顧客に通知中。CVEは未割り当て（評価中）。

**同一性の判断に役立つ情報：**
- インシデント発生日: 2026-06-02〜2026-06-03
- 修正日: 2026-06-05
- 脆弱なエンドポイント: /api/now/related_list_edit/create
- CVE: 未割り当て（記事執筆時点）
- 影響プラットフォーム: Australia リリースおよび特定設定変更済みの旧リリース

## タイムライン

- [2026-06-16 ServiceNow APIの認証バイパス脆弱性でエンタープライズ顧客データが流出](../articles/2026-06-16-servicenow-api-unauthenticated-access.md)
