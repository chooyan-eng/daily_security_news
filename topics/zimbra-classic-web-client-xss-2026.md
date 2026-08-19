# Zimbra Classic Web Client 保存型XSS脆弱性（2026年）

## 概要

Zimbra Collaboration Suite の Classic Web Client に存在する重大な保存型クロスサイトスクリプティング（XSS）脆弱性。細工されたメールを閲覧するだけでセッション乗っ取り等につながる。Google Threat Analysis Group（TAG）が報告し、Zimbraは2026年7月7日に修正版10.1.19をリリースした。CVE番号は本稿時点で未割当。Zimbra製品はこれまでWinter VivernやAPT29など国家支援型ハッカーに繰り返し悪用されてきた経緯がある。

**同一性の判断に役立つ情報：**
- 製品: Zimbra Collaboration Suite（Classic Web Client）
- 脆弱性種別: 保存型XSS（メール経由）
- 報告者: Google Threat Analysis Group（TAG）
- 修正版: Zimbra 10.1.19（2026年7月7日リリース）
- CVE: 本稿時点で未割当

## タイムライン

- [2026-07-12 Zimbra、Classic Web Client の重大な保存型XSS脆弱性に対するパッチ適用を呼びかけ](../articles/2026-07-12-zimbra-classic-web-client-xss.md)
