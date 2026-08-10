# Google Password Manager パスキー乗っ取り「Pass-ta-key」攻撃（2026年）

## 概要

Palo Alto Networks傘下のUnit 42が発表した、Windows端末上で動作するマルウェアがChrome/Google Password Managerの同期パスキーを乗っ取る3つの攻撃手法「Pass-ta-key」「Silver Pass-ta-key」「Golden Pass-ta-key」に関する研究。いずれも端末が既にマルウェアに侵害されていることを前提とするポスト侵害型の攻撃で、TPM搭載Windows環境が対象。2026年8月7日時点で実際の悪用の公開証拠はない。

**同一性の判断に役立つ情報：**
- 研究元: Unit 42（Palo Alto Networks）
- 攻撃手法名: Pass-ta-key / Silver Pass-ta-key / Golden Pass-ta-key
- 対象: Chrome上のGoogle Password Manager同期パスキー、Windows + TPM環境
- 前提条件: 端末上でマルウェアが一般ユーザー権限で既に実行されていること
- 攻撃内容: 認証アサーションの窃取／攻撃者制御の検証キー登録／Security Domain Secret（32バイト）の抽出によるパスキー完全窃取
- 悪用状況: 2026年8月7日時点で実際の悪用の公開証拠なし（研究・PoC段階）

## タイムライン

- [2026-08-10 Unit 42、Windows上のマルウェアがGoogle同期パスキーを乗っ取る「Pass-ta-key」攻撃を報告](../articles/2026-08-10-google-passkey-pass-ta-key-attack.md)
