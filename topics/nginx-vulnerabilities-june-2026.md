# NGINX 複数脆弱性（2026年6月）

## 概要

F5が2026年6月17日に公開したNGINX Open Source・NGINX Plus・NGINX Gateway Fabricに関する複数の脆弱性アドバイザリ。主要な脆弱性CVE-2026-9256（ngx_http_rewrite_moduleのヒープバッファオーバーフロー）はASLR無効環境またはASLRバイパス可能な条件下でRCEを可能とする。NGINX Gateway Fabric 2.3.0〜2.6.3にはHigh深刻度の脆弱性が複数含まれ、バージョン2.6.4への更新が必要。

**同一性の判断に役立つ情報：**
- 公開日: 2026年6月17日
- 対象製品: NGINX Open Source、NGINX Plus、NGINX Gateway Fabric、NGINX Ingress Controller
- 主要CVE:
  - CVE-2026-9256（ngx_http_rewrite_module ヒープバッファオーバーフロー / Critical）
  - CVE-2026-8711（ngx_http_js_module / High）
  - CVE-2026-42945（ngx_http_rewrite_module / High）
  - CVE-2026-1642（NGINX Core / High）
  - CVE-2026-11311（Gateway Fabric / High）
  - CVE-2026-50107（Gateway Fabric / High）
- 修正バージョン: nginx 1.29.8+、Gateway Fabric 2.6.4

## タイムライン

- [2026-06-19 NGINX 複数の深刻な脆弱性（CVE-2026-9256等）- F5が2026年6月セキュリティアドバイザリを公開](../articles/2026-06-19-nginx-multiple-vulnerabilities-june-2026.md)
