# F5 NGINX クリティカル脆弱性（CVE-2026-42530/42055）（2026年6月）

## 概要

F5 が2026年6月17日にアウトオブバンドパッチをリリースした NGINX の複数のクリティカル脆弱性。CVE-2026-42530（Use-After-Free）と CVE-2026-42055（ヒープバッファオーバーフロー）が最も深刻で、CVSS 9.2。HTTP モジュールに影響し、非認証の遠隔攻撃者による DoS またはリモートコード実行（RCE）が可能。NGINX Open Source、NGINX Plus、NGINX Gateway Fabric、NGINX Ingress Controller が影響を受ける。NGINX Open Source の修正版（1.31.2 / 1.30.3）が公開済み。

**同一性の判断に役立つ情報：**
- CVE-2026-42530: Use-After-Free（CVSS 9.2、HTTP モジュール）
- CVE-2026-42055: ヒープバッファオーバーフロー（CVSS 9.2、HTTP モジュール）
- CVE-2026-11311: NGINX Gateway Fabric 設定インジェクション（High）
- CVE-2026-50107: NGINX Gateway Fabric 設定インジェクション（High）
- 影響製品: NGINX Open Source、NGINX Plus、NGINX Gateway Fabric、NGINX Ingress Controller
- 修正版: NGINX 1.31.2（メインライン）、1.30.3（安定）
- アドバイザリ公開: 2026-06-17

## タイムライン

- [2026-06-18 F5、NGINX の複数クリティカル脆弱性（CVE-2026-42530/42055）に緊急アウトオブバンドパッチ](../articles/2026-06-18-f5-nginx-critical-cve-2026-42530.md)
