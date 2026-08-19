# 「Agentjacking」——SentryのMCP連携経由でClaude Code・Cursor・CodexなどAIコーディングエージェントを乗っ取る新手法

- **日付**: 2026-06-30
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/agentjacking-attack-tricks-ai-coding.html)、[VentureBeat](https://venturebeat.com/security/the-attack-that-hijacked-claude-code-came-through-sentry-datadog-pagerduty-and-jira-have-the-same-exposure)、[The New Stack](https://thenewstack.io/agentjacking-sentry-mcp-attack/)
- **トピック**: [Claude Code RCE・APIキー窃取脆弱性（CVE-2025-59536/CVE-2026-21852）](../topics/claude-code-rce-cve-2025-59536.md)
- **分類**: 関連

## 概要

セキュリティ企業Tenet Securityは、エラー監視ツールSentryのMCP連携を悪用しAIコーディングエージェント（Claude Code・Cursor・Codex等）に不正コードを実行させる新攻撃「Agentjacking」を報告した。公開されているSentryのDSN（認証不要で取得可能な公開鍵情報）さえあれば偽のエラーイベントを注入でき、85%の成功率で乗っ取りが確認されたという。

## 詳細

### 攻撃の仕組み

攻撃者は、公開されているSentryのDSN（Data Source Name）を悪用し、偽のエラーイベントをSentryに注入する。開発者が使用するAIコーディングエージェントは、MCP（Model Context Protocol）経由でSentryのエラー情報を「信頼できるシステム出力」として取り込む設計になっているため、この偽イベントを読み込んだ際、攻撃者が仕込んだ指示にエージェントが従い、開発者のマシン上で任意コードが実行されてしまう。

### 認証不要という深刻さ

本攻撃の特徴は、いかなる認証も必要としない点にある。公開されているDSN情報さえ入手できれば攻撃可能であり、Tenet Securityは公開Sentry認証情報を保持する組織を2,388件確認したと報告している。検証環境ではAWSのシークレットアクセスキーが窃取される事例や、他の連携エージェントへの侵害拡大も確認された。

### 影響範囲の広さ

同様の構造的問題は、Sentryに限らずDatadog・PagerDuty・Jiraなど、AIエージェントがMCP経由でテレメトリ/エラー情報を「信頼できる入力」として取り込む他のDevOpsツールにも共通するとされる。

### 既存のAIエージェント関連脆弱性との関連性

本リポジトリでは、Anthropic Claude Codeのプロジェクトファイル経由のRCE脆弱性（CVE-2025-59536/CVE-2026-21852）や、Microsoft AutoGen Studioを標的とするエクスプロイトチェーン「AutoJack」など、AIコーディングエージェント・マルチエージェントツールを標的とした脆弱性を継続的に追跡している。Agentjackingは、これらとは異なる攻撃経路（アプリケーション自体の脆弱性ではなく、MCP経由で取り込む外部テレメトリの信頼性の欠如）を突くものであり、直接の続報ではないが、「AIエージェントが外部入力を無条件に信頼することに起因するセキュリティリスク」という共通の脅威カテゴリに属する。2026年に入りAIエージェント・MCP関連のセキュリティリスクへの関心が急速に高まっている。

---

## 関連記事

- [Claude Codeのプロジェクトファイル経由でRCEとAPIキー窃取が可能な脆弱性（CVE-2025-59536/CVE-2026-21852）](../articles/2026-06-22-claude-code-rce-api-exfiltration.md) - 同じくAIコーディングエージェント（Claude Code）を標的とした脆弱性だが、攻撃経路は異なる
- [Microsoft AutoJack：悪意あるウェブページ1枚でAIエージェント経由のホストRCEが可能](../articles/2026-06-20-microsoft-autojack-ai-agent-rce.md) - AIエージェント連携基盤（MCP）を悪用する点で共通する攻撃パターン
