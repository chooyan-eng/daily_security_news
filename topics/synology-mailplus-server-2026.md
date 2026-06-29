# Synology MailPlus Server 重大脆弱性（2026年）

## 概要

Synology NAS 上でプライベートメールインフラを運用する「MailPlus Server」に存在する3件の脆弱性（CVE-2026-13136、CVE-2026-13135、CVE-2025-15660）。リモート攻撃者による任意ファイルの読み書き・内部サービスへの不正アクセス・DoS攻撃が可能。Synology は2026年6月26日にセキュリティアドバイザリ SA-26:11 を公開し MailPlus Server 4.0.1-31663 で修正した。Bitsight が確認したインターネット公開サーバーは2,100件超で、ドイツ・韓国・中国・台湾・米国に集中している。利用可能な緩和策はなく、パッチ適用のみが対策。

**同一性の判断に役立つ情報：**
- CVE: CVE-2026-13136（Critical）、CVE-2026-13135（Critical）、CVE-2025-15660（High）
- 影響製品: Synology MailPlus Server（DSM v7.3、7.2.2、7.2.1上）
- 修正バージョン: MailPlus Server 4.0.1-31663
- 公開日: 2026年6月26日（Synology Security Advisory SA-26:11）
- 公開サーバー数: 2,100件超（Bitsight調査）

## タイムライン

- [2026-06-29 Synology MailPlus Server 重大脆弱性（CVE-2026-13136 他）— 2100超の公開サーバーに緊急パッチ](../articles/2026-06-29-synology-mailplus-server-vulnerabilities.md)
