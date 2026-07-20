# WordPress wp2shell REST API 脆弱性チェーン（2026年7月）

## 概要

WordPressコアの2つの脆弱性、CVE-2026-63030（REST APIバッチルート処理の route confusion）とCVE-2026-60137（WP_Queryの`author__not_in`パラメータSQLインジェクション）を連鎖させ、未認証の攻撃者がWordPress 6.9〜7.0.1のサイトで匿名アクセスから管理者権限奪取・RCEに到達できる「wp2shell」攻撃チェーン。2026年7月17日にパッチ公開、WordPress.orgは強制自動更新を実施。

**同一性の判断に役立つ情報：**
- 通称: wp2shell
- CVE: CVE-2026-63030（REST APIバッチルート混乱、WordPress 6.9で導入）、CVE-2026-60137（WP_Query author__not_in SQLインジェクション）
- 影響バージョン: WordPress 6.9.0〜7.0.1（チェーン悪用）、6.8.0〜6.8.5（CVE-2026-60137単体）
- 脆弱エンドポイント: `/wp-json/batch/v1`
- パッチ公開日: 2026-07-17
- 対応: WordPress.orgによる強制自動更新

## タイムライン

- [2026-07-20 wp2shell（CVE-2026-63030 + CVE-2026-60137）– WordPress コア REST API 脆弱性チェーンで未認証RCEが野放しで悪用](../articles/2026-07-20-wordpress-wp2shell-rce-chain.md)
