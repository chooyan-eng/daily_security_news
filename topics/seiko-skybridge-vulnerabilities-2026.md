# セイコーソリューションズ SkyBridge/SkySpider 脆弱性（2026年）

## 概要

セイコーソリューションズ製ルーター「SkyBridge」シリーズ（MB-A100/A110/A200/BASIC MB-A130）およびSkySpider（MB-R210）に確認された複数の脆弱性。特にSkyBridge BASIC MB-A130（v1.5.8以前）はWeb管理画面から認証なしで任意のOSコマンドを実行可能（CVSSv3で9.8）。MB-A100/MB-A110はサポート終了済みで修正パッチ提供予定なし。

**同一性の判断に役立つ情報：**
- 対象製品: SkyBridge MB-A100/A110/A200/BASIC MB-A130、SkySpider MB-R210
- 最重要脆弱性: SkyBridge BASIC MB-A130の認証なしOSコマンドインジェクション
- CVSS: v3.0で9.8、v4.0で9.3
- 修正版: v1.6.0以降（BASIC MB-A130）
- サポート終了・パッチなし: MB-A100、MB-A110

## タイムライン

- [2026-07-03 セイコーソリューションズ製ルーター「SkyBridge」シリーズに複数の脆弱性、一部は無償修正パッチなし](../articles/2026-07-03-seiko-skybridge-os-command-injection.md)
