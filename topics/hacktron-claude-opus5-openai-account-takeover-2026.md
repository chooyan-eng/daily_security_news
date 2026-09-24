# Hacktron研究者、Claude Opus 5でOpenAI社内システムへの侵入に成功（脆弱性連鎖悪用、2026年9月）

## 概要

セキュリティ企業Hacktron AIの研究者3名（Harsh Jaiswal氏、Mohan Pedhapati氏、Rahul Maini氏）が、AnthropicのAIモデル「Claude Opus 5」を用いて、OpenAIの公開ヘルプフォーラムの脆弱性（悪意ある画像アップロードによるフォーラムサーバー上でのコード実行）とOpenAI独自のログイン機構の脆弱性を連鎖させ、OpenAI社員のChatGPT・Codexアカウントを乗っ取り、社内コードリポジトリへの到達を実証した事案。発見から実証まで72時間未満、OpenAIは約14時間で修正し研究者へ6,500ドルの報奨金を支払った。旧モデルOpus 4.8では攻撃チェーンの構築に失敗していた点が特筆される。

**同一性の判断に役立つ情報：**
- 実施企業: Hacktron AI（研究者: Harsh Jaiswal、Mohan Pedhapati、Rahul Maini）
- 使用AIモデル: Anthropic Claude Opus 5（旧モデルOpus 4.8では失敗）
- 対象: OpenAI（ヘルプフォーラム＋ログイン機構の脆弱性連鎖）
- 攻撃手法: 悪意ある画像アップロードによるフォーラムサーバーRCE→ログイン機構の弱点悪用→アカウント乗っ取り
- 到達範囲: ChatGPT・Codex・GitHub・Slack・メール等の連携サービス、社内コードリポジトリ
- 実施期間: 発見から実証まで72時間未満
- OpenAI対応: 約14時間で修正、報奨金6,500ドル支払い
- 実害: ソースコード閲覧・マージ・顧客データアクセスなし

## タイムライン

- [2026-09-20 セキュリティ研究者、Claude Opus 5を使いOpenAI社員アカウントを72時間未満で乗っ取り](../articles/2026-09-20-hacktron-claude-opus5-openai-account-takeover-2026.md)
