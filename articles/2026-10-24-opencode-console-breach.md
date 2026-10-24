# AIコーディングツールOpenCodeのConsoleが侵害、連携したAIプロバイダのAPIキーが露出し不正課金

- **日付**: 2026-10-24
- **出典**: [BleepingComputer](https://bleepingcomputer.com/news/security/opencode-hack-exposes-api-keys-amid-ai-distillation-attacks)
- **トピック**: [OpenCode Console 侵害・連携AIプロバイダAPIキー露出（2026年10月）](../topics/opencode-console-breach-2026.md)
- **分類**: 新規

## 概要

OpenCodeは10月17日、ホスト型Consoleの旧システムへの不正アクセスにより、外部AIプロバイダを連携していたユーザー（全体の1.4%）のAPIキーが露出した可能性があると公表した。不正課金や一部GCPプロジェクトの停止が報告されている。

## 詳細

### 事案の経緯

- OpenCodeは2026年10月17日に侵害を公表。廃止作業中だった旧システムへの不正アクセスが原因とされ、影響はConsoleで外部AIプロバイダを連携していたユーザーの1.4%。対象者にはメールで通知された。
- 共同創業者のDax Raad氏は、オープンソース版アプリやCLIは影響を受けず、ローカルで設定したキーはOpenCodeに送られないと説明した。
- OpenCode側は「大規模なdistillation攻撃」と表現し、少なくとも48時間にわたり標的にされていたとした。
- AnthropicとGoogleは露出したと見られるキーを無効化し、OpenAIはOpenCodeと協力してアクセス復旧とクレジット返金を進めた。ユーザーからは一晩で1,700ドル超の不正課金の報告があった。

### 技術的補足

侵入経路、認証情報の保管方式（暗号化の有無等）、悪用範囲は独立には確認されていない。推奨対策は、各プロバイダのダッシュボードで該当キーを失効させ新しいキーを発行すること（OpenCode上でキーを削除しても、既に取得されたコピーは無効化されない）、10月16日以降の利用履歴の確認、利用上限・アラートの設定である。サードパーティAPIキーを預かるSaaS／Webアプリでは、保管時暗号化、スコープ制限、旧システム廃止時のデータ消去が教訓となる。

### 参考出典

- [OpenCode Breach Exposes AI API Keys（eSecurity Planet）](https://www.esecurityplanet.com/artificial-intelligence/news-opencode-breach-ai-api-keys/)
- [Hackers hit AI coding tool OpenCode（TechCrunch）](https://techcrunch.com/2026/10/19/hackers-hit-ai-coding-tool-opencode-running-up-charges-on-users-ai-accounts/)

---

## 関連記事


