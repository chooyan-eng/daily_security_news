# JetBrains Marketplaceの悪意あるプラグイン15件がAI APIキーを窃取（70,000インストール超）

- **日付**: 2026-06-17
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/malicious-jetbrains-marketplace-plugins-steal-ai-api-keys-from-developers/) / [The Hacker News](https://thehackernews.com/2026/06/malicious-jetbrains-plugins-steal-ai.html) / [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/fifteen-jetbrains-marketplace/)
- **トピック**: [JetBrains Marketplace 悪意あるプラグインによる AI API キー窃取（2026年）](../topics/jetbrains-plugin-ai-key-theft-2026.md)
- **分類**: 新規

## 概要

Aikido Security が JetBrains Marketplace で少なくとも15件の悪意あるプラグインを発見した。いずれも AI コーディングアシスタントを装い、ユーザーが設定に入力した AI プロバイダーの API キーを攻撃者管理サーバに送信する。70,000回以上インストールされており、2025年10月から2026年6月まで継続的に新プラグインが追加された。

## 詳細

### キャンペーンの概要

| 項目 | 詳細 |
|------|------|
| 発見者 | Aikido Security（BleepingComputer が独立検証） |
| 悪意あるプラグイン数 | 15件 |
| 合計インストール数 | 70,000回以上 |
| 活動期間 | 2025年10月〜2026年6月10日 |
| 窃取対象 | OpenAI、Claude、DeepSeek 等の AI プロバイダー API キー |

### プラグインの動作

各プラグインは AI コーディングアシスタントとして動作し、以下の機能を正常に提供する：
- チャット機能
- コミットメッセージ生成
- コードレビュー
- バグ検出
- ユニットテスト生成

しかし、ユーザーがプラグイン設定画面で API キーを入力して「Apply」をクリックした瞬間に、入力した認証情報が攻撃者管理のサーバ（39.107.60[.]51）に HTTP 経由で平文送信される。

### 技術的詳細

- **窃取タイミング**: 設定の「Apply」クリック時に即時送信
- **送信先**: ハードコードされたサーバ IP `39.107.60[.]51`（HTTP、平文）
- **対象 API キー**: OpenAI、Anthropic Claude、DeepSeek 等の主要 AI プロバイダー
- **コード共通性**: 15件すべてが類似コードを共有し、同一攻撃者グループと推定

### 主要プラグイン

最も多くインストールされた2件：
- **CodeGPT AI Assistant**: 25,000回以上のダウンロード
- **DeepSeek AI Assist**: 25,000回以上のダウンロード

（ダウンロード数が水増しされている可能性あり）

### 被害シナリオ

窃取した AI API キーを使用することで攻撃者は：
1. 被害者の API クレジットを不正消費
2. 被害者の組織名・ユーザー情報に紐づいた LLM リクエストを送信
3. 有料 API の課金を発生させる
4. キーが高い権限を持つ場合、組織の AI 利用履歴にアクセス

### 推奨対応

- 上記15件の JetBrains プラグインを即時アンインストール
- 影響を受けた全ての AI プロバイダー API キーを直ちにローテーション（無効化・新規発行）
- JetBrains Marketplace での AI 関連プラグインインストール時はベンダー公式のみを選択
- プラグインのネットワーク通信を監視し、不審な外部 IP への接続を検出

---

## 関連記事

- [Mastra AIフレームワーク npm 144パッケージがサプライチェーン攻撃で侵害](../articles/2026-06-17-mastra-npm-supply-chain-attack.md) - 同時期に発生した開発者を標的とした認証情報窃取攻撃
