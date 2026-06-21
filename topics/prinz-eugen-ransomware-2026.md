# Prinz Eugen ランサムウェア（2026年6月〜）

## 概要

2026年6月に Malwarebytes Threatdown が分析を公開した新興ランサムウェアグループ。Go 言語実装で ChaCha20-Poly1305 暗号 + Argon2id 鍵導出を採用し、最近更新されたファイルを優先して暗号化する独自ロジックを持つ。身代金要求書（ランサムノート）をファイルとして残さず、メール・ダークウェブポータル等のアウトオブバンド手段で被害者に連絡するため法的証拠の痕跡が少ない。RaaS モデルは採用しておらず、独立型の組織として運営されているとみられる。

**同一性の判断に役立つ情報：**
- グループ名: Prinz Eugen（PrinzEugen）
- 実装言語: Go
- 暗号: ChaCha20-Poly1305（Argon2id + SHA-256 + HKDF-SHA256 で鍵導出）
- 主要ペイロード: `servertool.exe`
- 初期アクセス手法: 盗んだ RDP 認証情報
- 特徴: ランサムノートなし・最近更新ファイル優先暗号化・RaaS 非採用
- 確認被害者数: 5件以上（Standard Bank 含む）
- 分析元: Malwarebytes Threatdown

## タイムライン

- [2026-06-21 Prinz Eugen — 身代金要求書を残さない新興ランサムウェア、最近更新ファイルを優先暗号化](../articles/2026-06-21-prinz-eugen-ransomware.md)
