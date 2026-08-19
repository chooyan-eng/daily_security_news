# Claude for Chrome ClaudeBleed脆弱性（2026年）

## 概要

Anthropic製ブラウザ拡張機能「Claude for Chrome」に存在する、他の拡張機能によるユーザー操作偽装を許す脆弱性群（通称「ClaudeBleed」）。claude.aiドメイン上でスクリプトアクセス権限を持つ悪意ある拡張機能が、わずかなJavaScriptでクリックを偽装し、Claudeに9種類のハードコードされたプロンプトを不正実行させ、Gmail・Google Drive・GitHubなどのデータを窃取できる。「Act without asking」有効時は完全にサイレントで実行される。

**同一性の判断に役立つ情報：**
- 脆弱性名: ClaudeBleed
- CVSS: 9.6（Critical）
- 対象製品: Claude for Chrome（v1.0.80時点で未修正）
- 初回報告: 2026年5月
- 影響範囲: Gmail・Google Docs・Google Calendar・GitHub等の連携データ

## タイムライン

- [2026-07-16 Claude for Chrome拡張機能の脆弱性「ClaudeBleed」、悪意ある拡張機能によるGmail等窃取のおそれ](../articles/2026-07-16-claude-for-chrome-extension-vulnerability.md)
