# LiteSpeed cPanel プラグイン root 権限昇格脆弱性（2026年6月）

## 概要

LiteSpeed Web サーバの cPanel プラグインに誤った権限割り当て脆弱性（CVE-2026-48172、CVSS 9.8）が発見され、積極的な悪用が確認されている。cPanel 認証済みユーザーが標準の cPanel JSON API 経由でプラグインの `lsws.redisAble` 関数を呼び出し、root 権限で任意スクリプトを実行できる。共有ホスティング環境で特に深刻。CISA が KEV カタログに追加、連邦機関の修正期限は 2026年6月18日。

**同一性の判断に役立つ情報：**
- 主要 CVE: CVE-2026-48172（CVSS 9.8）、CVE-2026-54420（CVSS 8.5）
- 対象製品: LiteSpeed WHM Plugin（cPanel 用）
- 影響バージョン: v2.4.8 未満
- 修正バージョン: LiteSpeed WHM Plugin v5.3.2.1（cPanel Plugin v2.4.8）
- CISA KEV 追加日: 2026年6月15日頃
- FCEB 修正期限: 2026年6月18日

## タイムライン

- [2026-06-17 LiteSpeed cPanelプラグイン CVE-2026-48172 がCISA KEV追加・root権限昇格に悪用](../articles/2026-06-17-litespeed-cpanel-plugin-privilege-escalation.md)
