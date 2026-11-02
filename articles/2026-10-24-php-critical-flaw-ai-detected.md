# AIが発見したPHPの重大脆弱性、PHP Foundationが緊急修正を公開（ウェブサイト全体の約7割に影響の可能性）

- **日付**: 2026-10-24
- **出典**: [ABC News](https://www.abc.net.au/news/2026-10-22/data-breach-warning-after-ai-uncovers-critical-php-flaw/107295516)
- **トピック**: [PHP の重大脆弱性（AI支援で発見、2026年10月）](../topics/php-critical-flaw-ai-detected-2026.md)
- **分類**: 新規

## 概要

AIエージェントの支援で発見されたPHPの重大な脆弱性に対し、PHP Foundationが修正版を公開し、即時アップデートを呼びかけた。PHPは全ウェブサイトの約7割で使われるとされ、一部サイトは対応のため停止した。

## 詳細

### 報道されている内容

- OpenAIは、自社モデルが脆弱性発見に寄与し、Wiz・Cloudflareなどを含むメンテナ・研究者・セキュリティ事業者の連合で、公開前に修正を準備したと説明している。修正作業とリリースはPHPのメンテナが主導した。
- PHP Foundationは、利用者に即時アップデートを強く推奨した。FBIは、即時の更新が難しい場合は完全な緩和までシステムをオフラインにするよう助言したと報じられている。
- 悪用状況は情報源により異なる。CISAは公表時点で悪用を観測していないとした一方、ABC Newsの報道ではAWSが10月17日頃から悪用試行の兆候を確認したとされる。PHP Foundationは、潜在的なエクスプロイトが2024年には理論上指摘されていたと述べたという。
- 対応のため一部のウェブサイトが一時停止した（AP配信記事）。

### 技術的補足と留意点

本記事作成時点で確認できた報道には、CVE番号、影響バージョン、脆弱性の種別（RCE等）、修正バージョンの具体的記載を見つけられなかった。そのため、これらはPHP公式のセキュリティアドバイザリで確認する必要がある。WebアプリではPHPランタイムを自前で管理している場合（VPS、コンテナ、レガシーなLAMP環境）は自分で更新が必要で、共有ホスティングやマネージドPaaSは事業者側の対応を確認する。更新後はランタイムのバージョン確認、WAFログでの不審リクエストの確認を行うことが望ましい。

### 参考出典

- [Some websites go dark as operators address an AI-detected flaw（news4jax／AP）](https://www.news4jax.com/business/2026/10/21/some-websites-go-dark-as-operators-address-an-ai-detected-flaw-in-a-web-programming-language/)
- [Urgent security fix issued for code vital to estimated 70% of all websites（ABC7）](https://abc7news.com/story/urgent-security-fix-issued-code-vital-estimated-70-websites/19965216/)

---

## 関連記事


