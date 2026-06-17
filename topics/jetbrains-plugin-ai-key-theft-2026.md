# JetBrains Marketplace 悪意あるプラグインによる AI API キー窃取（2026年）

## 概要

JetBrains Marketplace で発見された15件の悪意あるプラグインキャンペーン。いずれも AI コーディングアシスタントを装い、ユーザーが設定に入力した OpenAI・Claude・DeepSeek などの AI プロバイダー API キーを攻撃者管理サーバに送信する。2025年10月から2026年6月まで継続的に新プラグインが追加され、合計70,000回以上インストールされた。Aikido Security が発見。

**同一性の判断に役立つ情報：**
- 悪意あるプラグイン数: 15件
- 合計インストール数: 70,000回以上
- 活動期間: 2025年10月〜2026年6月10日
- 窃取対象: AI プロバイダー API キー（OpenAI、Claude、DeepSeek 等）
- C2サーバ: 39.107.60[.]51（HTTP、平文）
- 発見者: Aikido Security

## タイムライン

- [2026-06-17 JetBrains Marketplaceの悪意あるプラグイン15件がAI APIキーを窃取（70,000インストール超）](../articles/2026-06-17-jetbrains-malicious-plugins-ai-api-keys.md)
