# Laravel組み込みTokenGuardに認証バイパス（CVSS v4.0 9.2）、細工した非文字列の資格情報で任意ユーザーとしてログイン可能

- **日付**: 2026-10-24
- **出典**: [Daily Security Review](https://dailysecurityreview.com/?p=44792)
- **トピック**: [Laravel TokenGuard 認証バイパス（GHSA-f9x3-7vq9-cph6、2026年10月）](../topics/laravel-tokenguard-auth-bypass-2026.md)
- **分類**: 新規

## 概要

Laravelの組み込みTokenGuardに、未認証の攻撃者が既存ユーザーとして認証されうる重大な欠陥が見つかった。MySQL/MariaDB利用のアプリが対象で、アドバイザリ GHSA-f9x3-7vq9-cph6 は10月19日公開、CVSS v4.0で9.2。

## 詳細

### 脆弱性情報

| 項目 | 内容 |
|------|------|
| アドバイザリ | GHSA-f9x3-7vq9-cph6（2026-10-19公開） |
| 深刻度 | CVSS v4.0 9.2（Critical） |
| 条件 | MySQLまたはMariaDBを使うアプリ |
| 修正版 | 12.68.0、13.29.0（8月にリリース済みと報じられている） |
| 対象外 | Sanctum、Passportはアドバイザリの対象外 |

### 技術的補足

報道によれば、ログイン時のユーザー検索でフレームワークが、細工された文字列以外の資格情報を適切に扱わず、APIトークンを知らなくても既存ユーザーとして認証される。修正版は8月に出ているため、依存関係を更新済みのアプリは保護されている可能性が高い。`auth:api`等でtoken guardを直接使うアプリは、`composer.lock`のlaravel/frameworkのバージョンを確認し、未更新なら更新する。CVE番号は確認できなかった。

### 参考出典

- [Laravel TokenGuard auth bypass（lilting.ch）](https://lilting.ch/en/articles/laravel-tokenguard-auth-bypass)

---

## 関連記事


