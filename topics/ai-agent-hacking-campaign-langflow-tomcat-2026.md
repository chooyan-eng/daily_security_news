# AI自律型ハッキングキャンペーン「Hermes Agent」（2026年8月）

## 概要

中国語話者の脅威アクター（エイリアス: knaithe / KnYuan、珠海拠点）が、独自フレームワーク「Hermes Agent」を通じてAIモデル DeepSeek を自律的な攻撃オペレーターとして運用し、Langflow・n8n・Apache Tomcatなどインターネット公開のAI関連ツールを対象に脆弱性探索から侵入までを自動化したキャンペーン。Apache Tomcat CVE-2026-34486の悪用がCISA KEVに追加されたことで表面化した。攻撃指示はTelegramで行われていた。

**同一性の判断に役立つ情報：**
- 脅威アクター: knaithe / KnYuan（中国・珠海拠点、中国語話者）
- AIオーケストレーションフレームワーク: Hermes Agent（DeepSeekを自律オペレーターとして利用）
- 悪用CVE: CVE-2026-34486（Apache Tomcat、EncryptInterceptor暗号化不備）、CVE-2026-33017（Langflow、初期標的）、CVE-2026-9198（Langflow コードインジェクション、CISA KEV追加）
- 標的: インターネット露出のLangflow・n8n等、計7件の脆弱性
- 手動追撃: 少なくとも9台のApache Tomcatサーバーへのリバースシェル設置を試行
- 指揮系統: Telegram
- 調査元: Palo Alto Networks Unit 42

## タイムライン

- [2026-08-06 中国系脅威アクターがAIエージェント「Hermes Agent」で自律的侵入キャンペーンを実施、Apache Tomcat脆弱性(CVE-2026-34486)などを悪用](../articles/2026-08-06-ai-agent-hacking-campaign-langflow-tomcat-2026.md)
