# インフォスティーラー由来のAIサービス認証トークン窃取・不正転売事案（2026年）

## 概要

インフォスティーラー型マルウェア（LummaC2、Vidar、StealC等）で窃取されたセッショントークンが、Anthropic Claude、Google、Amazon等の主要AIサービスの認証を突破する目的で悪用されている問題。2026年8月2日にTelegram上で公開された感染ログ（約7GB、162か国・5,871台分）には未失効の認証トークンが多数含まれていた。窃取トークンはアンダーグラウンド市場で「Poison Claude」等の名称で転売され、正規契約者のアカウントで高額なAPI利用料が発生する被害につながっている。Anthropicが被害警告を発表。

**同一性の判断に役立つ情報：**
- 発端: 2026年8月2日にTelegramで公開された約7GBのインフォスティーラー感染ログ（162か国、5,871台の感染端末）
- 対象サービス: Anthropic Claude、Google、Microsoft、Amazon、Gamma、Notion、Character.ai、Cursor、Poe.com、Pika AI等
- 悪用マルウェア: LummaC2、Vidar、StealC
- 悪用手口: セッショントークンのリプレイによるMFA回避・アカウント乗っ取り
- アンダーグラウンド商材名: 「Poison Claude」（Opus 4.8/4.7/4.6、Sonnet 4.6等へのアクセス提供を謳う）
- 公表主体: Anthropic（Claudeユーザーへの注意喚起）

## タイムライン

- [2026-09-09 インフォスティーラーで窃取されたAIサービスの再利用可能トークン、MFAを回避しClaude等のアカウント乗っ取りに悪用](../articles/2026-09-09-infostealer-ai-token-theft-anthropic-claude.md)
