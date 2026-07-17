# Claude for Chrome拡張機能 ShadowPrompt脆弱性（2026年）

## 概要

Anthropicの「Claude for Chrome」拡張機能における、クリックハンドラが`event.isTrusted`を検証しないことに起因する脆弱性「ShadowPrompt」。悪意ある別のブラウザ拡張機能がClaude.aiに合成クリックを注入することで、Claudeの事前定義ブラウザ操作（Gmail・Google Docs・Calendarの読み取り等）を不正に承認済みとして実行させられる。「Act without asking」モード有効時はサイレント実行される。2026年5月にManifold Securityが報告済みだが、7月7日リリースのv1.0.80時点でも未修正。

**同一性の判断に役立つ情報：**
- 脆弱性名: ShadowPrompt
- 対象製品: Anthropic「Claude for Chrome」ブラウザ拡張機能
- 根本原因: クリックハンドラが`event.isTrusted`を検証していない
- 発見者: Manifold Security（2026年5月報告）
- 未修正確認バージョン: v1.0.80（2026年7月7日リリース）
- 影響: Gmail・Google Docs・Calendarデータの不正読み取り

## タイムライン

- [2026-07-17 Claude for Chrome拡張機能に「ShadowPrompt」脆弱性 ― 悪意ある別拡張機能がクリックを偽装しGmail等を不正操作](../articles/2026-07-17-claude-chrome-extension-shadowprompt.md)
