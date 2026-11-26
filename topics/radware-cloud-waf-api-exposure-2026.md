# Radware Cloud WAF 管理API露出・顧客認証情報流出（2026年11月）

## 概要

Radwareのクラウド型WAFサービスで、内部用の管理APIが認証なしでインターネットからアクセス可能な状態になっており、2026年11月19日に攻撃者がアクセス（約10時間後に検知）。顧客の連絡先情報と、一部顧客のログエクスポート用認証情報（AWS S3／Azure Blob Storage／SFTP）が露出した事案。

**同一性の判断に役立つ情報：**
- 対象: Radware Cloud WAF（AppSec: WAF／BOT 顧客）
- 発生: 2026-11-19（約10時間後に検知）
- 原因: 内部管理APIが未認証でインターネット公開
- 露出: 顧客連絡先、ログエクスポート用のS3/Azure Blob/SFTP認証情報（一部顧客）
- 影響なしとされるもの: WAF検査、証明書、アプリケーショントラフィック、クラウドDDoSデータ

## タイムライン

- [2026-11-26 Radware、Cloud WAFの内部管理APIが認証なしで公開状態に 顧客のログ出力先クラウド認証情報が露出](../articles/2026-11-26-radware-cloud-waf-management-api-exposed.md)
