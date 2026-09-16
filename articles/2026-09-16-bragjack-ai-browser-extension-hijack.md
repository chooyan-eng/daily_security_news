# 1つのブラウザ拡張機能でChrome・Comet・Edge・Opera Neon・Claudeの AIアシスタントを乗っ取り可能な「BragJack」型攻撃

- **日付**: 2026-09-16
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/one-extension-could-hijack-ai.html), [Dark Reading](https://www.darkreading.com/endpoint-security/bragjack-browser-agentic-ai)
- **トピック**: [BragJack：ブラウザ拡張機能によるAIアシスタント乗っ取り手法（2026年9月）](../topics/bragjack-ai-browser-extension-hijack-2026.md)
- **分類**: 新規

## 概要

セキュリティ企業Forever Securityは、通常の低権限ブラウザ拡張機能を1つ使うだけで、Chrome（Gemini Live）、Perplexity Comet、Microsoft Edge、Opera Neon、Claude for Chrome拡張機能という5製品に組み込まれたAIエージェント機能を乗っ取れる攻撃手法を実証した。ブラウザ内蔵のAIエージェントが、拡張機能から到達可能な高権限機能への新たな攻撃経路を生んでいる。

## 詳細

Forever Securityの研究者らは、Chromiumベースの複数ブラウザ・拡張機能に組み込まれたAIアシスタント機能について、悪意ある（あるいは侵害された）通常の低権限ブラウザ拡張機能から、本来ブラウザが厳格に隔離しているはずの高権限機能へ到達できることを示した。

製品ごとの影響は異なる。Perplexity Cometは完全にAI駆動のブラウザとして設計されているため影響が最も大きく、乗っ取られたエージェントはコンピュータ上の任意のファイル読み取り、閲覧履歴の取得、スクリーンショットの取得、さらにはユーザーになりすました操作までが可能になる。Chromeでは、ファイル読み取りに加えてカメラ・マイクを起動されるおそれがある。Edge、Opera Neon、Claude for Chrome拡張機能では、AIエージェントを攻撃者の意図通りに操作されるおそれがある。

共通する原因は、ブラウザ内にAIエージェントを組み込んだことで、ブラウザが本来維持している権限の分離（低権限の拡張機能と高権限のブラウザ機能との境界）に新たな抜け道が生じている点にある。

対応状況として、5手法のうちChromeとEdgeの2製品についてのみCVEが採番されており、Chromeはバージョン143.0.7499.192以降、Edgeはバージョン150.0.4078.48以降で修正済みである。Comet、Opera Neon、Claude for Chrome拡張機能についても、Forever Securityは各社から報奨金の支払いを受けたとしているが、修正の具体的な時期は公表されていない。2026年9月16日時点では、これらの手法が実環境の攻撃で使用された公開証拠はないとされている。

ブラウザにAIエージェント機能を統合する製品が急速に増える中、拡張機能のエコシステムを経由した新たな攻撃面が生まれつつあることを示す事例であり、同種のAI機能を持つ他ブラウザ・拡張機能についても同様の設計上のリスクが存在する可能性が指摘されている。

---
