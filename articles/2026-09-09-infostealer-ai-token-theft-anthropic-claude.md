# インフォスティーラーで窃取されたAIサービスの再利用可能トークン、MFAを回避しClaude等のアカウント乗っ取りに悪用

- **日付**: 2026-09-09
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/infostealer-logs-expose-replayable-ai.html), [Dark Reading](https://www.darkreading.com/cyberattacks-data-breaches/anthropic-users-infostealer-attacks-session-thefts)
- **トピック**: [インフォスティーラー由来のAIサービス認証トークン窃取・不正転売事案（2026年）](../topics/infostealer-ai-token-theft-anthropic-2026.md)
- **分類**: 新規

## 概要

Anthropicは、インフォスティーラー型マルウェアによって窃取されたセッショントークンを悪用し、攻撃者がClaudeアカウントを乗っ取ってAI利用枠を不正消費する攻撃が発生していると警告した。2026年8月にTelegram上で公開された感染ログには、Google・Anthropic・Amazon等の主要AIサービスの未失効認証トークンが多数含まれていたことが判明している。

## 詳細

発端は2026年8月2日、Telegramチャンネル上で公開された約7GBのインフォスティーラー感染ログである。このダンプには162か国、5,871台の感染端末から窃取されたデータが含まれており、その中にはGoogle、Microsoft、Anthropic、Amazon、Gamma、Notion、Character.ai、Cursor、Poe.com、Pika AIなど、主要なAI・クラウドサービスの未失効認証トークンが多数存在していた。

LummaC2、Vidar、StealCといった代表的なインフォスティーラーファミリーがブラウザのCookieやセッショントークンを窃取し、攻撃者はこれを使ってアカウントを乗っ取っている。パスワードと異なり、セッショントークンを窃取・再利用（リプレイ）された場合、多要素認証（MFA）をはじめとする通常の認証防御を経由せずにアカウントへアクセスできてしまう点が深刻である。ログイン試行の異常としてアラートが発報されにくいため、被害の発覚が遅れる傾向もある。

窃取されたトークンはアンダーグラウンド市場で商品化されており、Claude・Cursor・ChatGPT・Geminiなどへのアクセス権を割引価格で提供し、24時間365日のサポートや返金保証まで謳う業者が確認されている。中でも「Poison Claude」と称するサービスは、AnthropicのOpus 4.8・4.7・4.6やSonnet 4.6といった上位モデルへのアクセスを提供すると宣伝しており、正規契約者のアカウントで発生した高額なAPI利用料が、乗っ取り被害者に転嫁される形となっている。

Anthropicはユーザーに対し、デバイスのマルウェア感染対策の徹底、異常なセッションの定期的な確認、疑わしいセッションの強制ログアウトなどの対策を呼びかけている。生成AIサービスの利用が拡大する中、認証トークンそのものが高値で取引される新たな窃取対象になっている実態が浮き彫りとなった。
