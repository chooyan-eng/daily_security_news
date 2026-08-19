# AI生成ブラウザ内完結型ランサムウェア（Chromium File System Access API悪用、2026年）

## 概要

Check Pointが、AIモデルDeepSeekに指示して生成させたマルウェアサンプルにより、ブラウザのChromium File System Access APIを悪用したブラウザ内完結型ランサムウェアの攻撃チェーンが実際に動作することを実証。ネイティブペイロードやブラウザ脆弱性の悪用なしに、Windows/macOS/Linux/Androidでファイル暗号化が可能。実際の攻撃キャンペーンでの悪用証拠は未確認。

**同一性の判断に役立つ情報：**
- 研究元: Check Point
- 悪用対象機能: Chromium File System Access API
- 生成AI: DeepSeek
- 攻撃手法: フィッシングでフォルダアクセス許可を取得 → 列挙・窃取・暗号化・脅迫文表示（ブラウザ内で完結）
- 動作確認環境: Windows, macOS, Linux, Android, Microsoft Edge
- 実悪用の有無: 未確認（実証・概念実証段階）

## タイムライン

- [2026-07-07 AI生成のブラウザ内完結型ランサムウェア、Chromium File System Access APIを悪用（Windows/Android等）](../articles/2026-07-07-ai-browser-ransomware-chromium-filesystem-api.md)
