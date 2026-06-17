# LiteSpeed cPanelプラグイン CVE-2026-48172 がCISA KEV追加・root権限昇格に悪用

- **日付**: 2026-06-17
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/cisa-flags-litespeed-cpanel-plugin-flaw.html) / [BleepingComputer](https://www.bleepingcomputer.com/news/security/cisa-warns-of-another-actively-exploited-cpanel-plugin-flaw/) / [SecurityWeek](https://www.securityweek.com/cisa-urges-immediate-patching-of-exploited-litespeed-cpanel-plugin-zero-day/)
- **トピック**: [LiteSpeed cPanel プラグイン root 権限昇格脆弱性（2026年6月）](../topics/litespeed-cpanel-plugin-2026.md)
- **分類**: 新規

## 概要

LiteSpeed Web サーバの cPanel プラグインに深刻な特権昇格脆弱性（CVE-2026-48172、CVSS 9.8）が発見され、CISA が KEV カタログに追加した。cPanel 認証済みユーザーが標準 JSON API 経由で root 権限を取得できる。修正期限は 2026年6月18日（FCEB 機関向け）。

## 詳細

### 脆弱性の技術的詳細

本件では主に2件の脆弱性が報告されている：

| CVE | 説明 | CVSS |
|-----|------|------|
| CVE-2026-48172 | 誤った権限割り当て、cPanel 認証済みユーザーが root として任意スクリプトを実行可能 | 9.8 |
| CVE-2026-54420 | シンボリックリンク悪用によるroot権限昇格（FTP または Web シェルアクセスが前提） | 8.5 |

**CVE-2026-48172** の根本原因は、LiteSpeed WHM Plugin の `lsws.redisAble` 関数にある誤った権限設定。この関数は cPanel の標準 JSON API 経由で呼び出し可能であり、認証済みの cPanel ユーザーであれば誰でも root 権限でスクリプトを実行できる。

### 影響を受ける環境

- 対象製品: LiteSpeed WHM Plugin v2.4.8 未満
- 対象プラットフォーム: CloudLinux または CageFS を使用した共有ホスティングサーバ
- 修正バージョン: LiteSpeed WHM Plugin v5.3.2.1（cPanel Plugin v2.4.8 同梱）

### 攻撃シナリオ

共有ホスティング環境における攻撃シナリオが特に深刻：

1. 共有ホスティング上に低権限の cPanel アカウントを保有する攻撃者
2. cPanel JSON API 経由で `lsws.redisAble` 関数を呼び出し
3. root 権限でサーバ全体を制御
4. 同一サーバ上の他ユーザーのデータや設定にアクセス

### CISA 対応

- CISA が KEV カタログに追加
- 2026年6月18日: 連邦文民行政機関（FCEB）への修正期限
- 「プラグインバージョン 2.4.8 未満のすべてのユーザーに対してリスクがある」と明記

### 推奨対応

- LiteSpeed WHM Plugin を v5.3.2.1 以上（cPanel Plugin v2.4.8 以上）に即時アップグレード
- 共有ホスティングプロバイダーへの影響確認
- 異常な root 権限実行のログ調査
- cPanel JSON API の呼び出し履歴を確認
