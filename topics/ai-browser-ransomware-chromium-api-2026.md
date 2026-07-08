# AI生成ブラウザ内蔵型ランサムウェア「InfernoGrabber」（Chromium File System Access API悪用）

## 概要

DeepSeekにより生成されたマルウェアサンプル「InfernoGrabber v9.0」が、Chromium系ブラウザの File System Access API を悪用し、ネイティブペイロード・ブラウザ脆弱性・root権限のいずれも用いずにブラウザ内で完結するランサムウェア攻撃を実現していたことが判明。理論上のリスクとされてきた手法をAIが独力で実用化した初の事例。

**同一性の判断に役立つ情報：**
- マルウェア名: InfernoGrabber v9.0（作者命名）
- サンプルファイル名: deepseek_python_20260125_da0631.py
- 悪用API: Chromium File System Access API
- VirusTotalアップロード日: 2026年1月25日
- 生成元AIモデル: DeepSeek
- 影響プラットフォーム: Windows・macOS・Linux・Android・Edge
- 実際の攻撃での悪用: 未確認（研究者による発見時点）

## タイムライン

- [2026-07-08 AI生成のブラウザ内蔵型ランサムウェアがChromium File System Access APIを悪用 — Windows・Android等で動作確認](../articles/2026-07-08-ai-browser-ransomware-chromium-api.md)
