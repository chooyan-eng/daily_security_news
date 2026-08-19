# ブラウザ完結型ランサムウェア（File System Access API悪用、2026年）

## 概要

Check Point Researchが発見した、AI（DeepSeek）が生成したブラウザ完結型ランサムウェアの攻撃手法。ChromeのFile System Access API（`showDirectoryPicker()`）を悪用し、Windows・Android上でファイルの窃取・暗号化・恐喝を実行する。Androidでは写真フォルダ（DCIM）が標的となりうる。

**同一性の判断に役立つ情報：**
- 発見組織: Check Point Research
- 悪用API: Chrome File System Access API（`showDirectoryPicker()`）
- 生成元とされるAIモデル: DeepSeek
- 検体名: deepseek_python_20260125_da0631.py（VirusTotal）
- 対象プラットフォーム: Windows, Android（Chrome 132以降）

## タイムライン

- [2026-07-01 AI生成のブラウザ完結型ランサムウェア、ChromeのFile System Access APIをAndroidで悪用](../articles/2026-07-01-ai-browser-ransomware-chrome-fsa-android.md)
