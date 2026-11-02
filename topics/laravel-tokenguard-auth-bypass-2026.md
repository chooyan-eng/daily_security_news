# Laravel TokenGuard 認証バイパス（GHSA-f9x3-7vq9-cph6、2026年10月）

## 概要

Laravel組み込みTokenGuardの認証バイパス（GHSA-f9x3-7vq9-cph6、CVSS v4.0 9.2）。MySQL/MariaDB環境で未認証攻撃者が既存ユーザーとして認証可能。修正版: 12.68.0／13.29.0。Sanctum・Passportは対象外。

## タイムライン

- [2026-10-24 Laravel組み込みTokenGuardに認証バイパス（CVSS v4.0 9.2）](../articles/2026-10-24-laravel-tokenguard-auth-bypass.md)
