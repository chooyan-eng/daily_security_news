# Pass-ta-key攻撃 Google同期パスキー ハイジャック（2026年8月）

## 概要

Palo Alto Networks Unit 42が公表した、Windows上のChrome＋GoogleパスワードマネージャーによるTPM保護済み同期パスキーを、端末感染済みマルウェアが生体認証を経ずに窃取・悪用できる3手法「Pass-ta-key」「Silver Pass-ta-key」「Golden Pass-ta-key」の総称。最も深刻なGolden Pass-ta-keyは、Chrome再登録時にメモリ上に一時出現するマスターシークレットを抽出し、同期済み・将来同期される全パスキーを継続的に復号可能にする。

**同一性の判断に役立つ情報：**
- 攻撃名: Pass-ta-key / Silver Pass-ta-key / Golden Pass-ta-key
- 対象: Google Password Manager（Chrome、Windows、TPM搭載機）の同期パスキー
- 前提条件: 端末上でマルウェアが既に実行中であること（暗号技術自体は無傷）
- 最深刻な手法: Golden Pass-ta-key（再登録時のメモリ上マスターシークレット窃取、継続的復号が可能）
- 調査元: Palo Alto Networks Unit 42
- Google対応: 事前通知済み、一部緩和策を展開

## タイムライン

- [2026-08-06 「Pass-ta-key」攻撃、指紋認証なしでGoogle同期パスキーをマルウェアが乗っ取り可能に](../articles/2026-08-06-google-passkey-pass-ta-key-attack-2026.md)
