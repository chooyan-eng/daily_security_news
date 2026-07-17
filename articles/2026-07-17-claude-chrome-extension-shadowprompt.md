# Claude for Chrome拡張機能に「ShadowPrompt」脆弱性 ― 悪意ある別拡張機能がクリックを偽装しGmail等を不正操作

- **日付**: 2026-07-17
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/claude-for-chrome-flaw-lets-other.html) / [Koi Security](https://www.koi.ai/blog/shadowprompt-how-any-website-could-have-hijacked-anthropic-claude-chrome-extension)
- **トピック**: [Claude for Chrome拡張機能 ShadowPrompt脆弱性（2026年）](../topics/claude-chrome-extension-shadowprompt-2026.md)
- **分類**: 新規

## 概要

Anthropicのブラウザ拡張機能「Claude for Chrome」に、他の悪意あるブラウザ拡張機能が承認クリックを偽造できる脆弱性が発見された。研究者らは「ShadowPrompt」と命名している。Claudeのクリックハンドラがブラウザの`event.isTrusted`プロパティを検証していないため、悪意ある拡張機能が合成クリックを生成し、Claudeに事前定義されたブラウザ操作（Gmail・Google Docs・Calendarの読み取りなど）を承認済みとして実行させることが可能。2026年5月の報告から8リリース後の最新版（v1.0.80、7月7日リリース）でも未修正のままとなっている。

## 詳細

### 脆弱性の技術詳細

Claude for Chrome拡張機能は、ユーザーが操作の承認ダイアログをクリックしたかどうかを、ブラウザ標準の`event.isTrusted`プロパティで検証していない。このため、Claude.aiにスクリプトを注入できる別の悪意あるブラウザ拡張機能が、実際のユーザー操作を伴わない合成クリックイベントを生成し、Claudeにこれを正規の承認クリックとして受理させることができる。研究者はこの一行の修正で防げると指摘している（クリックハンドラ冒頭に `if (!n.isTrusted) return;` を追加するのみ）。

### 影響範囲

デフォルト設定では、この攻撃によってClaudeの事前定義済みブラウザタスクの一部が承認ダイアログ提示前に自動トリガーされうる。さらに、拡張機能の「Act without asking（確認なしで実行）」モードが有効な場合、Claudeはこれらの操作をサイレントに実行してしまい、攻撃者はGmailメッセージ・Google Docsの内容・カレンダー情報などを窃取できる可能性がある。

### 発見と対応状況

問題はManifold Securityの研究者によって2026年5月にAnthropicへ報告された。しかし記事執筆時点の最新版（Claude for Chrome v1.0.80、2026年7月7日リリース）でも8回のリリースを経てなお再現可能な状態が続いている。

### 対策推奨

- Claude for Chromeの「Act without asking」モードを無効化し、常に承認ダイアログを確認する運用に切り替える
- ブラウザにインストールする拡張機能を最小限に絞り、出所不明な拡張機能の導入を避ける
- Anthropicによる修正パッチの公開状況を注視する

---

## 関連記事

なし（新規トピック）
