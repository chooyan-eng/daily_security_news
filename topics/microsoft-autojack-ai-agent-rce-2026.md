# Microsoft AutoJack AI エージェント RCE エクスプロイトチェーン（2026年）

## 概要

Microsoft Defender Security Research Team が 2026年6月18日に公開した、AutoGen Studio（マルチエージェント AI プロトタイピング UI）を標的とするエクスプロイトチェーン「AutoJack」。オリジン許可リストバイパス・未認証 MCP エンドポイント・安全でないパラメータ処理の3脆弱性を連鎖させ、悪意あるウェブページを閲覧するだけでホストマシン上での RCE が可能となる。pip インストール版は影響を受けず、GitHub main で修正済み。

**同一性の判断に役立つ情報：**
- エクスプロイト名: AutoJack
- 発見者: Microsoft Defender Security Research Team
- 標的: Microsoft Research AutoGen Studio（マルチエージェント AI プロトタイピング UI）
- 脆弱性チェーン: オリジン許可リストバイパス + 未認証 MCP WebSocket + コマンドインジェクション（3段階）
- 攻撃要件: 悪意あるウェブ URL を被害者のエージェントに送信するだけ（ゼロクリック RCE）
- pip 版への影響: なし（MCP WebSocket サーフェスは PyPI リリースに含まれない）
- 修正: GitHub commit b047730（PR #7362）で修正済み
- 野生での悪用: 未確認（研究目的の公開）

## タイムライン

- [2026-06-20 Microsoft AutoJack：悪意あるウェブページ1枚でAIエージェント経由のホストRCEが可能](../articles/2026-06-20-microsoft-autojack-ai-agent-rce.md)
