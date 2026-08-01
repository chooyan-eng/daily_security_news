# Adobe Campaign Classic 重大脆弱性群（2026年）

## 概要

Adobe Campaign Classic（ACC）に2026年6月末以降相次いで発見されている最大深刻度クラスの脆弱性群。7月30日にはCVSS満点10.0の認可不備脆弱性（CVE-2026-48449）とCVSS8.6のSQLインジェクション脆弱性（CVE-2026-48448）が公開された。これに先立ち6月末〜7月上旬にも別の最大深刻度脆弱性（CVE-2026-48286、任意コード実行）が修正されている。主にオンプレミス導入環境が影響対象。

**同一性の判断に役立つ情報：**
- 対象製品: Adobe Campaign Classic（ACC）v7.4.3 build 9397以前
- 関連CVE: CVE-2026-48449（認可不備、CVSS10.0）、CVE-2026-48448（SQLi、CVSS8.6）、CVE-2026-48286（任意コード実行）
- 影響範囲: 完全オンプレミス環境／ハイブリッド環境のオンプレミスコンポーネント（Adobeホスト型インスタンスは対策済み）

## タイムライン

- [2026-08-01 Adobe Campaign Classic にCVSS満点10.0の認可不備・重大SQLインジェクション脆弱性](../articles/2026-08-01-adobe-campaign-classic-critical-vulnerabilities.md)
