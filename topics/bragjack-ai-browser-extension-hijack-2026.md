# BragJack：ブラウザ拡張機能によるAIアシスタント乗っ取り手法（2026年9月）

## 概要

セキュリティ企業Forever Securityが実証した、通常の低権限ブラウザ拡張機能を使うだけでChromeのGemini Live、Perplexity Comet、Microsoft Edge、Opera Neon、Claude for Chrome拡張機能という5製品に組み込まれたAIエージェント機能を乗っ取れる攻撃手法。ブラウザ内蔵のAIエージェントが、拡張機能から到達可能な高権限機能への新たな攻撃経路を生んでいる。

**同一性の判断に役立つ情報：**
- 発見者: Forever Security
- 対象: Chrome（Gemini Live）、Perplexity Comet、Microsoft Edge、Opera Neon、Claude for Chrome拡張機能
- 手口: 低権限の通常ブラウザ拡張機能から、ブラウザ内蔵AIエージェントの高権限機能へアクセス
- 影響（製品別）: Cometはファイル読み取り・閲覧履歴取得・スクリーンショット・ユーザーになりすました操作まで可能な完全なエージェント乗っ取り。Chromeはファイル読み取りに加えカメラ・マイクの起動も可能。Edge・Opera Neon・Claude for ChromeはAIエージェントの不正操作
- CVE: Chrome・Edgeの2件のみCVE採番、Chrome 143.0.7499.192／Edge 150.0.4078.48で修正済み。Comet・Opera Neon・Claude for Chromeは各社が報奨金を支払ったが修正時期は非公表
- 悪用状況: 2026年9月16日時点で実環境での悪用の公表証拠なし
- 報道日: 2026年9月16日

## タイムライン

- [2026-09-16 1つのブラウザ拡張機能でChrome・Comet・Edge・Opera Neon・Claudeの AIアシスタントを乗っ取り可能な「BragJack」型攻撃](../articles/2026-09-16-bragjack-ai-browser-extension-hijack.md)
