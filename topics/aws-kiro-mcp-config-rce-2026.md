# AWS Kiro エージェント型IDE 設定書き換えRCE（2026年）

## 概要

AWSのエージェント型コーディングIDE「Kiro」において、外部Webページ経由の間接プロンプトインジェクションを起点にKiroの設定ファイル（`~/.kiro/settings/mcp.json`）を書き換えさせ、開発者権限で任意コード実行に至る脆弱性群。発見はIntezer/Kodem Security（mcp.json経由、Kiro v0.11.130で修正）と、Cymulate（`.vscode/tasks.json`経由、CVE-2026-10591、CVSS3.1で8.8）の2系統。いずれも「外部コンテンツ起点の設定ファイル自動書き換え・自動再読み込み実行」という共通パターンを持つ。

**同一性の判断に役立つ情報：**
- 対象製品: AWS Kiro（エージェント型コーディングIDE）
- CVE: CVE-2026-10591（CVSS 3.1: 8.8 / CVSS 4.0: 8.6、Cymulate発見、`.vscode/tasks.json`系統）
- 関連する別系統の脆弱性（正式CVE番号なし）: Intezer/Kodem Security発見、`~/.kiro/settings/mcp.json`書き換え系統、v0.11.130で修正
- 攻撃起点: 細工されたWebページ内の隠しテキストによる間接プロンプトインジェクション
- 影響: 承認ステップを経ない開発者権限でのリモートコード実行

## タイムライン

- [2026-07-24 AWS Kiro：細工されたWebページからの間接プロンプトインジェクションでRCEに至る脆弱性](../articles/2026-07-24-aws-kiro-cve-2026-10591-mcp-config-rce.md)
