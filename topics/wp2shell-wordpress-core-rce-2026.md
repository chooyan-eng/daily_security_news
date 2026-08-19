# wp2shell WordPress コア RCE 脆弱性チェーン（2026年）

## 概要

WordPress コア自体に存在する REST API バッチルート処理の混同脆弱性（CVE-2026-63030）と SQL インジェクション（CVE-2026-60137）を連鎖させ、未認証の攻撃者が匿名 HTTP リクエストのみでリモートコード実行を達成できる攻撃チェーン。プラグイン不要の素の WordPress でも悪用可能。研究者・メディアからは「wp2shell」と呼称されている。

**同一性の判断に役立つ情報：**
- 攻撃チェーン名: wp2shell
- 関連 CVE: CVE-2026-63030（REST API バッチルート混同）、CVE-2026-60137（WordPress コア SQL インジェクション）
- 対象: WordPress コア（プラグイン・テーマ不問）
- 発見・分析: Rapid7、Cloudflare（WAF 対応）
- 脆弱性名: wp2shell
- CVE: CVE-2026-63030（REST APIバッチルート混同）、CVE-2026-60137（SQLインジェクション）
- 対象製品: WordPress コア
- 影響バージョン: 6.9.0〜6.9.4、7.0.0〜7.0.1
- 修正バージョン: 7.0.2、6.9.5、6.8.6
- 攻撃経路: `/wp-json/batch/v1`（REST APIバッチエンドポイント）
- 通称: wp2shell
- CVE: CVE-2026-63030（REST APIバッチルート混乱、WordPress 6.9で導入）、CVE-2026-60137（WP_Query author__not_in SQLインジェクション）
- 影響バージョン: WordPress 6.9.0〜7.0.1（チェーン悪用）、6.8.0〜6.8.5（CVE-2026-60137単体）
- 脆弱エンドポイント: `/wp-json/batch/v1`
- パッチ公開日: 2026-07-17
- 対応: WordPress.orgによる強制自動更新

## タイムライン

- [2026-07-20 wp2shell（CVE-2026-63030 + CVE-2026-60137）– WordPress コア REST API 脆弱性チェーンで未認証RCEが野放しで悪用](../articles/2026-07-20-wordpress-wp2shell-rce-chain.md)
- [2026-07-19 「wp2shell」WordPress コア脆弱性、未認証攻撃者によるリモートコード実行が可能に](../articles/2026-07-19-wp2shell-wordpress-core-rce.md)
- [2026-07-18 wp2shell：WordPress コア REST API の未認証 RCE 脆弱性（CVE-2026-63030）](../articles/2026-07-18-wp2shell-wordpress-core-rce.md)
