# Pass-ta-key：Googleパスワードマネージャー パスキー攻撃（2026年8月）

## 概要

Palo Alto Networks Unit 42が実証した、既にマルウェア感染したWindows端末からGoogleパスワードマネージャーの同期パスキーを乗っ取る3種類の攻撃手法「Pass-ta-key」「Silver Pass-ta-key」「Golden Pass-ta-key」。パスキー自体の暗号方式ではなく、クラウド同期・デバイス信頼・復旧フローの実装上の弱点を突く。

**同一性の判断に役立つ情報：**
- 研究主体: Palo Alto Networks Unit 42
- 攻撃名: Pass-ta-key（初期）、Silver Pass-ta-key、Golden Pass-ta-key（最深刻）
- 対象: Windows（TPM搭載）上のChrome「Googleパスワードマネージャー」同期パスキー機能
- 前提条件: 端末が既にマルウェア感染していること（パスキー暗号理論そのものは破られていない）
- 最大の影響: Security Domain Secret（SDS、32バイト）の抽出による同期パスキー全体の秘密鍵復元
- 公開日: 2026年8月3日（研究発表）

## タイムライン

- [2026-08-04 「Pass-ta-key」攻撃、Googleパスワードマネージャーの同期パスキーをマルウェア経由で乗っ取り可能とUnit 42が実証](../articles/2026-08-04-pass-ta-key-google-password-manager.md)
