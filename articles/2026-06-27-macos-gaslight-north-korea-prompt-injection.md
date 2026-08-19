# macOS.Gaslight：北朝鮮関連RustバックドアがプロンプトインジェクションでAIマルウェア解析を無効化

- **日付**: 2026-06-27
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/new-macos-malware-embeds-fake-errors-to-confuse-ai-analysis-tools/), [The Hacker News](https://thehackernews.com/2026/06/new-gaslight-macos-malware-uses-prompt.html), [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/macos-gaslight-rust-backdoor/)
- **トピック**: [macOS.Gaslight：北朝鮮関連マルウェアによるAIマルウェア解析回避（2026年6月）](../topics/macos-gaslight-north-korea-2026.md)
- **分類**: 新規

## 概要

2026年6月初旬にApple XProtectのシグネチャ更新で発見されたmacOSマルウェア「Gaslight」（macOS.Gaslight）は、北朝鮮関連サイバーアクターに帰属するRust製バックドアで、LLMを用いたマルウェア解析ツールをプロンプトインジェクションで欺くという前例のない回避技術を実装している。AIセキュリティスタックへの初の本格的攻撃として注目される。

## 詳細

### 発見の経緯

SentinelOneの研究者Phil Stokesが、Apple XProtectのシグネチャ更新をきっかけに分析した結果、このマルウェアがAI解析ツールを標的とした新しい回避技術を搭載していることを発見した。

### AIエスケープ技術（プロンプトインジェクション）

Gaslightの最大の特徴は、実行ファイル内部に38件の偽システムエラーメッセージを埋め込んでいる点である。これらのメッセージはLLMベースのマルウェアトリアージエージェントに対して読み込まれることを意図しており、「トークン期限切れ」「ディスク容量不足」「メモリ不足エラー」といった虚偽の警告を生成して、AI解析エージェントに解析の中断・打ち切りを誘導する。

従来のマルウェアが仮想サンドボックスの検出に注力していたのとは根本的に異なり、Gaslightは自動トリアージエージェントの「認識」そのものを攻撃する。

### 機能・C2チャンネル

Gaslightは持続的インプラントかつ高機能インフォスティーラーとして動作し、以下の特徴を持つ：
- **C2通信**: Telegram Bot API を利用（独自C2サーバーを持たないことで追跡を困難にする）
- **機能**: インタラクティブシェルによるコマンド実行と結果受信
- **実装言語**: Rust（クロスプラットフォーム対応・静的解析の難易度向上）

### 帰属と意義

SentinelOneは北朝鮮関連サイバーアクターへの帰属を報告している。本マルウェアは「AIによるセキュリティ防衛」の増加に対応して攻撃者側が適応を始めた最初の本格的な事例として業界内での警戒感を高めている。

### 防衛側への影響

- AI解析ツールのみに頼ったマルウェアトリアージには盲点がある
- 人間の解析者によるAI出力の検証が不可欠
- macOSセキュリティツールのXProtect・MRTを最新に保つ
- Telegram Bot API トラフィックの監視・制限を検討する

---

## 関連記事
