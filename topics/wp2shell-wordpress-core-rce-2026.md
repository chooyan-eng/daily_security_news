# wp2shell WordPress コア RCE 脆弱性チェーン（2026年）

## 概要

WordPress コア自体に存在する REST API バッチルート処理の混同脆弱性（CVE-2026-63030）と SQL インジェクション（CVE-2026-60137）を連鎖させ、未認証の攻撃者が匿名 HTTP リクエストのみでリモートコード実行を達成できる攻撃チェーン。プラグイン不要の素の WordPress でも悪用可能。研究者・メディアからは「wp2shell」と呼称されている。

**同一性の判断に役立つ情報：**
- 攻撃チェーン名: wp2shell
- 関連 CVE: CVE-2026-63030（REST API バッチルート混同）、CVE-2026-60137（WordPress コア SQL インジェクション）
- 対象: WordPress コア（プラグイン・テーマ不問）
- 発見・分析: Rapid7、Cloudflare（WAF 対応）

## タイムライン

- [2026-07-19 「wp2shell」WordPress コア脆弱性、未認証攻撃者によるリモートコード実行が可能に](../articles/2026-07-19-wp2shell-wordpress-core-rce.md)
