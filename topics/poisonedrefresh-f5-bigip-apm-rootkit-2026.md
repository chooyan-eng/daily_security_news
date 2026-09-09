# PoisonedRefresh F5 BIG-IP APM ファイルレスルートキット（2026年）

## 概要

F5 BIG-IP Access Policy Manager（APM）環境を標的とするファイルレスのLinuxルートキット。ESETが「PoisonedRefresh」と命名（Sophosは「Linux/Agnt-IC」として追跡）。PHPのロード処理に介入し、メモリ上にWebシェルを直接注入することでディスク上に痕跡を残さない。第1段のマルウェア（改変された`umount`バイナリ）が`/usr/sbin/httpd`に感染しBIG-IPアップグレードイメージに自身を埋め込むことで永続化する二段階構成。F5が追跡するキャンペーン「c05d5254」は、BIG-IP APMの未認証RCE脆弱性CVE-2025-53521の悪用と関連付けられている。

**同一性の判断に役立つ情報：**
- マルウェア名: PoisonedRefresh（ESET命名）／Linux/Agnt-IC（Sophos追跡名）
- 対象製品: F5 BIG-IP Access Policy Manager（APM）
- 関連CVE: CVE-2025-53521（BIG-IP APM 未認証RCE、アクセスポリシー設定済み仮想サーバーが対象）
- 攻撃キャンペーン名（F5追跡）: c05d5254
- 特徴: ファイルレス（メモリ常駐型）Webシェル、PHPの`eval()`実行、HTTP 201偽装レスポンス（CSSを装う）
- 永続化手法: 改変`umount`バイナリによる`/usr/sbin/httpd`感染、SELinux設定変更、BIG-IPアップグレードイメージへの埋め込み
- 公表: SophosLabsが2026年9月8日に技術分析を公開

## タイムライン

- [2026-09-09 F5 BIG-IP APM機器を狙うファイルレスLinuxルートキット「PoisonedRefresh」、メモリ上にPHP Webシェルを常駐](../articles/2026-09-09-poisonedrefresh-f5-bigip-apm-rootkit.md)
