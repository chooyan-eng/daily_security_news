# Zimbra Classic Web Client 保存型XSS脆弱性（2026年7月）

## 概要

Zimbra Collaboration SuiteのClassic Web Clientに存在した保存型クロスサイトスクリプティング（XSS）脆弱性。特別に細工したメールを受信者が開くだけで、ユーザー操作なしにログイン中のwebmailセッション内で任意のJavaScriptが実行される。発見者はGoogleのThreat Analysis Group（TAG）。Zimbraは2026年7月9日公開のZCS 10.1.19（Daffodil）で修正したが、CVE番号・CVSSスコアは記事執筆時点で未公表。

**同一性の判断に役立つ情報：**
- 対象製品: Zimbra Collaboration Suite（ZCS）Classic Web Client
- 脆弱性種別: 保存型XSS（メール開封のみで発火、クリック不要）
- 発見者: Google Threat Analysis Group（TAG）
- 修正バージョン: ZCS 10.1.19「Daffodil」（2026年7月9日公開）
- CVE番号: 未公表（記事執筆時点）

## タイムライン

- [2026-07-17 Zimbra Classic Web Clientに重大な保存型XSS脆弱性 ― Google TAGが発見、悪意あるメール1通でセッション乗っ取りの恐れ](../articles/2026-07-17-zimbra-classic-web-client-xss.md)
