# OpenCode Consoleが侵害、保存されたAIプロバイダAPIキーが流出の恐れ

- **日付**: 2026-10-27
- **出典**: [The Hacker News](https://thehackernews.com/2026/10/opencode-console-breach-may-have.html) / [Cyera](https://www.cyera.com/research/opencode-breach-what-happened-and-how-to-rotate-exposed-ai-api-keys)
- **トピック**: [OpenCode Console侵害・AI APIキー流出の恐れ（2026年10月）](../topics/opencode-console-breach-2026.md)
- **分類**: 新規

## 概要

AIコーディングツールOpenCodeのWebコンソールで、10月16日夜に侵入者が旧システムへ到達し、ユーザーが保存したOpenAI・Anthropic・GoogleなどのAPIキーが流出した可能性がある。OpenCodeは10月17日に公表し、外部プロバイダを連携したConsoleユーザーの約1.4%が対象とした。

## 詳細

- **原因**: 旧（廃止予定とされる）システムへの侵入とされるが、侵入経路・滞在期間は未公表。
- **影響**: プロバイダ側（OpenAI等）の侵害ではなく、OpenCode側基盤からのキー露出。一部ユーザーが身に覚えのないAI利用料金の請求を報告している。報道にはOpenCodeが未確認の数値も含まれる。
- **対応**: 各プロバイダのダッシュボードでキーを失効・再発行し、利用履歴を確認、新キーには利用上限を設定する。
- **教訓**: Webアプリが第三者APIキーを保管する場合、旧システムの棚卸し・暗号化・最小権限が不可欠。

---

## 関連記事

