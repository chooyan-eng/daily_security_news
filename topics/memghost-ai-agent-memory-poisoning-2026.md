# MemGhost AIエージェント記憶汚染攻撃（2026年）

## 概要

永続的なメモリ機能を持つAIパーソナルエージェント（Open-Claw、Claude Code SDK等）を標的とした新攻撃手法「MemGhost」。攻撃者が送信した1通のメールを読ませるだけで、エージェント自身のファイル書き込みツールを悪用して虚偽の情報を永続メモリに書き込ませ、以後のセッションで応答や行動を誘導する。ユーザーへの可視応答には記憶改ざんの痕跡が現れないステルス性が特徴。

**同一性の判断に役立つ情報：**
- 攻撃名: MemGhost
- 論文タイトル: "When Claws Remember but Do Not Tell: Stealthy Memory Injection in Persistent Personal Agents"
- 攻撃ベクター: 1通のメール（ワンショット、被害者との直接的なやり取り不要）
- 検証結果: Open-Claw + GPT-5.4 で87.5%成功、Claude Code SDK + Sonnet 4.6 で71.4%成功
- テストケース数: 56件
- 分類: メモリポイズニング / プロンプトインジェクションの派生（永続性を伴う点が新規）

## タイムライン

- [2026-07-13 新手法「MemGhost」、1通のメールでAIエージェントに永続的な偽の記憶を植え付け](../articles/2026-07-13-memghost-ai-agent-memory-poisoning.md)
