# GitHub Agentic Workflows「GitLost」プロンプトインジェクション脆弱性（2026年7月）

## 概要

GitHub の自然言語ワークフロー自動化機能「Agentic Workflows」において、未認証の攻撃者が公開リポジトリの GitHub Issue に間接プロンプトを仕込むだけで、同一組織のプライベートリポジトリのデータを漏洩させられる脆弱性「GitLost」。Noma Security（Noma Labs）が発見・報告。GitHub 側のガードレールも単純な文言追加で回避可能だった。

**同一性の判断に役立つ情報：**
- 脆弱性名: GitLost
- 対象: GitHub Agentic Workflows
- 発見: Noma Security（Noma Labs）
- 攻撃手法: 公開リポジトリの GitHub Issue 経由の間接プロンプトインジェクション
- 前提条件: 認証・アクセス権限不要
- 公表日: 2026年7月7〜8日

## タイムライン

- [2026-07-08 「GitLost」— GitHub Agentic Workflowsのプロンプトインジェクション脆弱性でプライベートリポジトリが漏洩](../articles/2026-07-08-github-gitlost-agentic-workflows-prompt-injection.md)
