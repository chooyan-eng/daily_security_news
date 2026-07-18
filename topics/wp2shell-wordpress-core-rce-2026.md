# wp2shell WordPress コア 未認証RCE（CVE-2026-63030）

## 概要

WordPress コアに存在する未認証リモートコード実行の脆弱性チェーン「wp2shell」。REST API バッチエンドポイント（`/wp-json/batch/v1`）のルート混同（CVE-2026-63030）と `WP_Query` の `author__not_in` パラメータにおけるSQLインジェクション（CVE-2026-60137）を連鎖させることで、認証・ユーザー操作不要で任意コード実行が可能になる。影響バージョンは6.9.0〜6.9.4・7.0.0〜7.0.1。WordPress.orgは2026年7月17日に7.0.2（および6.9.5・6.8.6へのバックポート）で修正した。

**同一性の判断に役立つ情報：**
- 脆弱性名: wp2shell
- CVE: CVE-2026-63030（REST APIバッチルート混同）、CVE-2026-60137（SQLインジェクション）
- 対象製品: WordPress コア
- 影響バージョン: 6.9.0〜6.9.4、7.0.0〜7.0.1
- 修正バージョン: 7.0.2、6.9.5、6.8.6
- 攻撃経路: `/wp-json/batch/v1`（REST APIバッチエンドポイント）

## タイムライン

- [2026-07-18 wp2shell：WordPress コア REST API の未認証 RCE 脆弱性（CVE-2026-63030）](../articles/2026-07-18-wp2shell-wordpress-core-rce.md)
