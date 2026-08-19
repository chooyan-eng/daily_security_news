# TrueBooker WordPress プラグイン認可バイパス（2026年8月）

## 概要

WordPress の予約・スケジューリングプラグイン「TrueBooker – Appointment Booking and Scheduler System」（1.2.3以下、パスワードリセット関連は1.2.4未満）に認可バイパスの重大な脆弱性が発見された。フロントエンドのパスワードリセット機能がアカウント所有権を検証しないため、未認証の攻撃者が管理者を含む任意アカウントのパスワードを変更しサイトを乗っ取ることが可能。

**同一性の判断に役立つ情報：**
- プラグイン名: TrueBooker – Appointment Booking and Scheduler System
- CVE: CVE-2026-14364、CVE-2026-14365、CVE-2026-14545
- 対象バージョン: 1.2.3以下（一部1.2.4未満）
- 脆弱性種別: 認可バイパス／不適切な権限管理（CWE-269）
- 影響: 未認証での管理者パスワード変更・サイト乗っ取り
- 発見・公表: Patchstack

## タイムライン

- [2026-08-07 WordPress 予約プラグイン「TrueBooker」に重大な認可バイパス – 未認証で管理者パスワードを変更可能](../articles/2026-08-08-truebooker-wordpress-plugin-auth-bypass.md)
