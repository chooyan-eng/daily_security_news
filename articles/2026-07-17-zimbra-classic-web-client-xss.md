# Zimbra Classic Web Clientに重大な保存型XSS脆弱性 ― Google TAGが発見、悪意あるメール1通でセッション乗っ取りの恐れ

- **日付**: 2026-07-17
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/zimbra-urges-customers-to-patch-critical-web-client-xss-flaw/) / [The Hacker News](https://thehackernews.com/2026/07/critical-zimbra-flaw-could-let-crafted_0483473395.html)
- **トピック**: [Zimbra Classic Web Client 保存型XSS脆弱性（2026年7月）](../topics/zimbra-classic-web-client-xss-2026.md)
- **分類**: 新規

## 概要

Zimbra Collaboration SuiteのClassic Web Clientに、特別に細工したメールを開くだけでログイン中セッション内で任意のJavaScriptが実行される保存型クロスサイトスクリプティング（XSS）脆弱性が存在することが判明した。発見はGoogle Threat Analysis Group（TAG）で、高度な標的型攻撃の調査過程で発見されたとみられる。Zimbraは2026年7月9日公開のZCS 10.1.19（Daffodil）で修正パッチを提供したが、記事執筆時点でCVE番号・CVSSスコアは未公表。

## 詳細

### 脆弱性の技術詳細

Classic Web Clientのメール表示処理に保存型XSSの欠陥があり、特別に細工されたメールメッセージを受信者が開いた瞬間に悪意あるJavaScriptがログイン中のwebmailセッションのコンテキストで実行される。クリック等のユーザー操作は不要で、メールを開封するだけで発火する点が特に危険視されている。成功した場合、攻撃者はセッションデータ・アカウント設定・メールボックス内情報を窃取できる可能性がある。

### 発見の経緯

本脆弱性はGoogleのThreat Analysis Group（TAG）によって発見された。TAGは国家的な攻撃者による標的型攻撃の調査を専門とするチームであり、この経緯は本脆弱性が高価値な標的に対する実際の攻撃活動と関連している可能性を示唆している。ただし現時点で実際の悪用が確認されたとの公式発表はない。

### 修正内容

Zimbraは2026年7月9日、zimbra-patchおよびzimbra-mbox-webclient-warパッケージを通じてZCS 10.1.19（コードネーム「Daffodil」）をリリースし、この脆弱性を修正した。

### 対策推奨

- Classic Web Clientを利用する全ての組織は直ちにZCS 10.1.19以降へアップデート
- インターネットに公開されている全てのZimbraシステムが最新化されていることを確認
- メールクライアントのJavaScript実行を伴う不審な挙動を監視

---

## 関連記事

なし（新規トピック）
