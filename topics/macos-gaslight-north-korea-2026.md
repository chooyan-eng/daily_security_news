# macOS.Gaslight：北朝鮮関連マルウェアによるAIマルウェア解析回避（2026年6月）

## 概要

2026年6月初旬にApple XProtectで検出されたmacOSマルウェア「Gaslight」（macOS.Gaslight）は、北朝鮮関連サイバーアクターに帰属するRust製バックドア。LLMベースのマルウェア解析ツールに対してプロンプトインジェクション（実行バイナリ内に38件の偽システムエラーメッセージを埋め込む）を行い、AI解析エージェントに解析の中断・打ち切りを誘導する。

**同一性の判断に役立つ情報：**
- マルウェア名: macOS.Gaslight
- 帰属: 北朝鮮関連サイバーアクター（SentinelOne Phil Stokes による帰属）
- 実装言語: Rust
- C2: Telegram Bot API
- 特異技術: LLMマルウェア解析ツールへのプロンプトインジェクション（38件の偽システムエラー埋め込み）
- 機能: 持続的インプラント + インフォスティーラー + インタラクティブシェル
- 発見経緯: Apple XProtectシグネチャ更新後、SentinelOneが分析

## タイムライン

- [2026-06-27 macOS.Gaslight：北朝鮮関連RustバックドアがプロンプトインジェクションでAIマルウェア解析を無効化](../articles/2026-06-27-macos-gaslight-north-korea-prompt-injection.md)
