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
- 総称: WP2Shell
- 対象製品: WordPress コア（プラグイン不問）
- 修正バージョン: 6.9.5、7.0.2
- 実悪用観測日: 2026-07-20（Coalition）
- エクスプロイト名: WP2Shell
- 対象: WordPress Core（外部プラグイン不要）
- 関連CVE: CVE-2026-60137（SQLインジェクション、高深刻度）、CVE-2026-63030（任意コード実行、重大）
- 修正版: 6.9.5、7.0.2
- 悪用開始: 2026年7月17日 米東部時間19時ごろ
- KEV追加日: 2026年7月21日
- CVE: CVE-2026-63030（REST APIバッチルート混同）、CVE-2026-60137（WP_Query SQLi）
- CISA KEV追加日: 2026年7月21日（CVE-2026-63030）
- 連邦機関対応期限: 2026年7月24日（CVE-2026-63030）／8月4日（CVE-2026-60137）
- 推定影響範囲: 世界で約9,000万件のWordPressインストール
- 悪用の特徴: 正規プラグイン「CMSmap」を偽装した約150KBのWebシェル設置

## タイムライン

- [2026-07-25 WordPress コア脆弱性チェーン「wp2shell」、公開エクスプロイトで大規模スキャンが拡大](../articles/2026-07-25-wp2shell-wordpress-rce.md)
- [2026-07-22 WordPress核心部の未認証RCE「WP2Shell」、CISA KEVカタログに追加され積極的悪用が確定](../articles/2026-07-22-wordpress-wp2shell-kev-cve-2026-63030.md)
- [2026-07-21 WP2Shell – WordPress コア脆弱性チェーン（CVE-2026-63030 / CVE-2026-60137）が未認証RCEとして実悪用](../articles/2026-07-21-wp2shell-wordpress-rce-chain.md)
- [2026-07-20 wp2shell（CVE-2026-63030 + CVE-2026-60137）– WordPress コア REST API 脆弱性チェーンで未認証RCEが野放しで悪用](../articles/2026-07-20-wordpress-wp2shell-rce-chain.md)
- [2026-07-19 「wp2shell」WordPress コア脆弱性、未認証攻撃者によるリモートコード実行が可能に](../articles/2026-07-19-wp2shell-wordpress-core-rce.md)
- [2026-07-18 wp2shell：WordPress コア REST API の未認証 RCE 脆弱性（CVE-2026-63030）](../articles/2026-07-18-wp2shell-wordpress-core-rce.md)
