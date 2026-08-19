# CISA KEVにAdobe ColdFusion・JoomShaper SP Page Builder・Langflowの4脆弱性を追加

- **日付**: 2026-07-16
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/cisa-adds-4-actively-exploited-adobe.html), [Security Affairs](https://securityaffairs.com/194927/hacking/u-s-cisa-adds-adobe-coldfusion-joomlack-page-builder-langflow-and-joomshaper-sp-page-builder-flaws-to-its-known-exploited-vulnerabilities-catalog.html), [SC Media](https://www.scworld.com/news/cisa-adds-coldfusion-langflow-and-two-joomla-bugs-to-known-exploited-vulnerabilities-list)
- **トピック**: [Langflow RCE脆弱性（CVE-2026-5027）](../topics/langflow-rce-cve-2026-5027.md)
- **分類**: 関連

## 概要

CISAが既知悪用脆弱性（KEV）カタログに、実際に悪用が確認された4件の脆弱性を追加。Adobe ColdFusionのパストラバーサル（CVE-2026-48282）、JoomShaper SP Page Builderの2件（CVE-2026-56290、CVE-2026-48908）、そしてAI開発プラットフォームLangflowの認可不備（CVE-2026-55255）が対象。連邦機関には7月10日までの対応が義務付けられた。

## 詳細

CISAは2026年7月7日、以下4件の脆弱性をKEVカタログに追加したと発表した。

- **CVE-2026-48282**（CVSS 10.0）：Adobe ColdFusionのパストラバーサル脆弱性。悪用されると現在のユーザー権限のコンテキストで任意コードが実行される可能性がある。
- **CVE-2026-56290**（CVSS 10.0）：JoomShaper SP Page Builder（Joomla用プラグイン）の不適切なアクセス制御脆弱性。未認証の任意ファイルアップロードを通じたリモートコード実行につながる。
- **CVE-2026-48908**（CVSS 10.0）：同じくJoomShaper SP Page Builderの危険なファイル種別の無制限アップロード脆弱性。未認証ユーザーが任意ファイルをアップロードでき、最終的にPHPコードのアップロード・実行に至る。
- **CVE-2026-55255**（CVSS 6.1）：Langflowのユーザー制御キーによる認可バイパス脆弱性。認証済み攻撃者が、被害者のフローIDをリクエストに指定するだけで他ユーザー所有のフローを実行できる。

このうちLangflowのCVE-2026-55255は、2026年6月に本リポジトリでも取り上げたパストラバーサル型RCE脆弱性CVE-2026-5027（KEV追加日2026-06-08）とは別のCVEだが、同一プラットフォームであるLangflowで短期間のうちに2件目の悪用確認・KEV追加が行われたことになり、AIワークフロー開発基盤の脆弱性対応が引き続き大きな課題であることを示している。

また、JoomShaper SP Page Builderの2件は、既報のJoomla用コンテンツエディタプラグイン「JCE」（CVE-2026-48907、CVSS 10.0）とは異なる製品・CVEだが、Joomlaプラグインエコシステムにおいてアップロード制御不備に起因する最大深刻度の脆弱性が繰り返し発見・悪用される傾向が続いていることを示す事例といえる。

---

## 関連記事

- [Langflow AIアプリ開発プラットフォームのパストラバーサル脆弱性（CVE-2026-5027）が野放し状態で悪用中](../articles/2026-06-16-langflow-path-traversal-cve-2026-5027.md) - 同一プラットフォームLangflowにおける別のCVEでのKEV追加事例
