# iCagenda・Balbooa Forms（Joomla拡張機能）がゼロデイとして悪用、CISAがKEVに追加

- **日付**: 2026-07-13
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/icagenda-and-balbooa-forms-joomla-flaws.html), [SecurityAffairs](https://securityaffairs.com/195164/security/u-s-cisa-adds-icagenda-and-balbooa-forms-flaws-to-its-known-exploited-vulnerabilities-catalog.html)
- **分類**: 関連

## 概要

CISAがJoomla用拡張機能「iCagenda」（CVE-2026-48939）と「Balbooa Forms」（CVE-2026-56291）の2件の最大深刻度（CVSS 10.0）脆弱性をKEVカタログに追加した。いずれもファイルアップロード機能の不備によりPHPファイルをアップロード・実行できる未認証RCEで、iCagendaは2026年6月15日からゼロデイとして自動化攻撃に悪用されていたことが判明している。

## 詳細

### iCagenda（CVE-2026-48939）

イベント管理用Joomla拡張機能「iCagenda」に存在する脆弱性で、ファイル添付機能の検証不備により任意ファイルのアップロードが可能。攻撃者はこれを悪用してPHPファイルをアップロードし、Webサーバー上でコードを実行できる。修正版は4.0.8（および3.9.15）で、2026年6月15〜16日にリリースされた。しかし、公開の遥か前の2026年6月15日時点で、既に自動化された攻撃キャンペーンによってゼロデイとして悪用されていたことが確認されている。

### Balbooa Forms（CVE-2026-56291）

フォーム作成用Joomla拡張機能「Balbooa Forms」に存在する同種の脆弱性で、2.4.0以下のバージョンが影響を受ける。ファイルアップロード機能の不備を突いて任意ファイルをアップロードでき、リモートコード実行につながる。修正版は2.4.1。

### 共通する攻撃パターン

両脆弱性ともCVSSスコアは10.0（最大深刻度）で、未認証の攻撃者がファイルアップロード機能を悪用してPHPコードを実行できる点が共通している。CISAはKEVカタログへの追加とともに、連邦機関に対して速やかな修正を求めている。Joomlaは人気の高いCMSであり、サードパーティ拡張機能の脆弱性は過去にも繰り返し悪用の標的となってきた。

### 対策

- iCagendaを4.0.8（または3.9.15）以降に、Balbooa Formsを2.4.1以降にアップデートすること
- 侵害の痕跡（不審なPHPファイルの設置、Webシェル）がないか既存サイトを確認すること
- ファイルアップロード機能を持つJoomla拡張機能全般について、最小権限化やWAFによる追加防御を検討すること

---

## 関連記事

- [Joomla JCEプラグイン CVE-2026-48907（CVSS 10.0）がCISA KEVに追加・PHPコード実行に悪用](../articles/2026-06-17-joomla-jce-cve-2026-48907-cisa-kev.md) - 同じくJoomla拡張機能のファイルアップロード脆弱性がCVSS 10.0でKEV追加された事例。攻撃手法（未認証PHPファイルアップロード→RCE）が酷似しており、Joomlaエコシステム全体で拡張機能の脆弱性悪用が継続していることを示す。
