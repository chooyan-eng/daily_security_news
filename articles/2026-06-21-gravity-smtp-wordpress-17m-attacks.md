# Gravity SMTP WordPress プラグイン CVE-2026-4020 — 1700万回超の攻撃試みを記録

- **日付**: 2026-06-21
- **出典**: [TechTimes](https://www.techtimes.com/articles/318768/20260621/wordpress-email-plugin-flaw-triggers-17-million-attacks-gravity-smtp-leaks-live-api-keys.htm) / [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-exploit-info-disclosure-bug-in-gravity-smtp-wordpress-plugin/) / [The Hacker News](https://thehackernews.com/2026/06/hackers-exploit-gravity-smtp-wordpress.html)
- **トピック**: [Gravity SMTP WordPress CVE-2026-4020 大規模悪用（2026年6月）](../topics/gravity-smtp-wordpress-cve-2026-4020.md)
- **分類**: 新規

## 概要

約10万サイトで利用されている WordPress プラグイン「Gravity SMTP」の情報漏洩脆弱性 CVE-2026-4020 を悪用した攻撃が爆発的に拡大。Wordfence が6月21日時点で累計1700万回以上のエクスプロイト試みをブロックしたと発表。認証なしで API キー・OAuth トークン・サーバー設定一式が窃取可能で、修正版（2.1.5以降）への即時更新が必要。

## 詳細

### 脆弱性の概要

CVE-2026-4020 は Gravity SMTP プラグイン（バージョン 2.1.4 以前）の REST API エンドポイント `GET /wp-json/gravitysmtp/v1/tests/mock-data` に存在する情報漏洩脆弱性。エンドポイントの `permission_callback` が無条件で `true` を返すため、一切の認証なしにアクセス可能。

### 漏洩する情報

クエリパラメータ `?page=gravitysmtp-settings` を付加するとシステムレポート（約365 KB の JSON）が返却され、以下の情報がすべて含まれる：

- PHP バージョン・拡張モジュール一覧
- Web サーバーバージョンとドキュメントルート
- MySQL バージョン・テーブル名
- WordPress バージョン・アクティブプラグイン全一覧
- **Gravity SMTP に設定された API キー / OAuth トークン（SendGrid・Mailgun・Gmail 等）**
- データベース接続情報（一部設定）

### 攻撃の拡大経緯

| 日付 | イベント |
|------|---------|
| 2026-03-31 | CVE-2026-4020 公表 |
| 2026-05-22 | CrowdSec が検出シグネチャを公開 |
| 2026-05-27 | 初の野生での悪用を観測（Wordfence） |
| 2026-06-06 | 1日あたり400万件超のリクエストに急増 |
| 2026-06-21 | 累計1700万件超をブロック（Wordfence 発表） |

### 攻撃者の手口

攻撃者は窃取した API キーを使い、

1. 正規ドメインから大量スパムを送信
2. SendGrid / Mailgun アカウントの残高を消費
3. 取得した OAuth トークンで接続先サービスへ横移動

というキャンペーンを展開していることが確認されている。

### 修正・対応

- **修正版**: Gravity SMTP 2.1.5 以降に即時更新
- **API キーのローテーション**: プラグインを利用していたサイトはすべてのメール送信サービス API キー・OAuth トークンをローテーション
- **WAF ルール**: Wordfence の無料ルールで当該エンドポイントへのアクセスを遮断可能

---

## 関連記事

なし
