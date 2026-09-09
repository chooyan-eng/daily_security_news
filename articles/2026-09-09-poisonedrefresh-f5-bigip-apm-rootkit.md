# F5 BIG-IP APM機器を狙うファイルレスLinuxルートキット「PoisonedRefresh」、メモリ上にPHP Webシェルを常駐

- **日付**: 2026-09-09
- **出典**: [Security Affairs](https://securityaffairs.com/198746/malware/poisonedrefresh-a-fileless-linux-rootkit-that-injects-php-web-shells-into-f5-big-ip-apm-server-memory.html), [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-breach-f5-big-ip-apm-devices-to-deploy-linux-rootkit/), [Help Net Security](https://www.helpnetsecurity.com/2026/09/09/f5-big-ip-apm-rootkit-hides-web-shell-in-memory/)
- **トピック**: [PoisonedRefresh F5 BIG-IP APM ファイルレスルートキット（2026年）](../topics/poisonedrefresh-f5-bigip-apm-rootkit-2026.md)
- **分類**: 新規

## 概要

SophosLabsは2026年9月8日、F5 BIG-IP Access Policy Manager（APM）環境を標的とするファイルレスのLinuxルートキット「PoisonedRefresh」（ESET命名。Sophosは「Linux/Agnt-IC」として追跡）に関する詳細な技術分析を公表した。PHPの処理に介入しメモリ上にWebシェルを注入する手口で、ディスク上に痕跡を残さない点が特徴。

## 詳細

PoisonedRefreshは、侵害されたF5 BIG-IP APM環境で確認された二段階攻撃の第2段ペイロードである。第1段は、改変されたLinuxの`umount`バイナリ内に隠されたマルウェアで、`/usr/sbin/httpd`（Apache）に感染し、SELinuxの設定を変更した上で、BIG-IPのアップグレードイメージ自体に自身を埋め込むことで、デバイスのファームウェア更新後も生存し続ける仕組みを持つ。

第2段のPoisonedRefreshは、PHPのロード処理に介入し、ファイルレスのWebシェルを直接メモリ上へ注入する。このWebシェルは特殊な形式（「マジック」パターン）に合致したリクエストのみを受け付け、その内容を復号した上でPHPの`eval()`関数を通じて実行、レスポンスはCSSコンテンツを装ったHTTP 201として返される。ディスクに実体ファイルを残さないため、従来型のファイル完全性監視やアンチウイルスによる検知が困難とされる。

F5は、この一連の活動（同社が「c05d5254」として追跡する攻撃キャンペーン）を、アクセスポリシーが設定された仮想サーバー上のBIG-IP APMに影響する未認証RCE脆弱性CVE-2025-53521の悪用と関連付けている。標的となる環境はApache、libphp、APRモジュールのロード機構、BIG-IP APMのWebtopコンポーネント、BIG-IPのアップグレードワークフローに特化しており、攻撃者が特定の製品構成を綿密に研究した上で開発したマルウェアであることがうかがえる。

BIG-IP APMを運用する組織には、該当CVEのパッチ適用状況の確認に加え、ファームウェアイメージの完全性検証、メモリフォレンジックを含む侵害調査の実施が推奨される。
