# claude.ai「共有チャット」機能悪用によるClickFix型マルウェア配布（2026年）

## 概要

攻撃者がAI開発ツール検索者向けGoogle広告のハイジャックからclaude.aiの「Artifacts」「共有チャット（claude.ai/share）」機能の悪用へと手口を発展させ、正規かつ信頼されたclaude.aiドメイン上にClickFix型（コピー＆ペーストでコマンドを実行させる）の不正手順を掲載し、マルウェアを配布したキャンペーン。Trend Microが発見・報告し、Anthropicは該当アカウントの停止と共有チャットの無効化で対応した。

**同一性の判断に役立つ情報：**
- 悪用されたプラットフォーム: Anthropic Claude.ai（Artifacts機能、claude.ai/share共有リンク機能）
- 発見・報告: Trend Micro
- 攻撃手法: マルバタイジング（Google広告ハイジャック）→claude.aiの信頼ドメイン上でのClickFix型コマンド実行誘導
- 被害規模: 広告経由の被害者2,000人超
- ペイロード: Mac向け情報窃取マルウェア（インフォスティーラー）
- Anthropicの対応: 該当アカウント停止、悪用された共有チャットの無効化、追加の悪用対策を実装中

## タイムライン

- [2026-09-12 攻撃者、claude.aiの「共有チャット」機能を悪用しClickFix型マルウェア配布の踏み台に](../articles/2026-09-12-claude-ai-shared-chat-clickfix-malware.md)
