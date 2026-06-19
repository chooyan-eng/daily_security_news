# NGINX 複数の深刻な脆弱性（CVE-2026-9256等）- F5が2026年6月セキュリティアドバイザリを公開

- **日付**: 2026-06-19
- **出典**: [F5 / my.f5.com](https://my.f5.com/manage/s/article/K000161377)
- **トピック**: [NGINX 複数脆弱性（2026年6月）](../topics/nginx-vulnerabilities-june-2026.md)
- **分類**: 新規

## 概要

F5が2026年6月17日にNGINX Open Source・NGINX Plus・NGINX Gateway Fabricに関する複数の脆弱性アドバイザリを公開した。主要な脆弱性CVE-2026-9256はASLR無効環境またはASLRバイパス可能な条件下でRCE（リモートコード実行）を可能とするヒープバッファオーバーフロー。NGINX Gateway FabricについてはHigh深刻度の脆弱性が複数含まれ、バージョン2.6.4への更新が必要。

## 詳細

### 公開された主な脆弱性

**CVE-2026-9256（ngx_http_rewrite_module）**
- **深刻度**: Critical
- **影響**: NGINX Plus、NGINX Open Source
- **概要**: `ngx_http_rewrite_module`のヒープバッファオーバーフロー。NGINXワーカープロセスの再起動を引き起こす。
- **RCE条件**: ASLR（アドレス空間配置のランダム化）が無効の環境、またはASLRをバイパスできる場合にRCE（リモートコード実行）が可能
- **対策**: 最新のNGINX Plusまたはnginx 1.29.8+に更新

**CVE-2026-8711（ngx_http_js_module）**
- **深刻度**: High
- **影響**: NGINX JavaScript（NJS）モジュール使用時
- **概要**: `ngx_http_js_module`の脆弱性

**CVE-2026-42945（ngx_http_rewrite_module）**
- **深刻度**: High
- **影響**: NGINX Plus、NGINX Open Source
- **概要**: `ngx_http_rewrite_module`の別の脆弱性

**CVE-2026-1642（NGINX Core）**
- **深刻度**: High
- **影響**: NGINX Plus、NGINX Open Source
- **概要**: NGINX Core の脆弱性

### NGINX Gateway Fabric の脆弱性

NGINX Gateway FabricはKubernetesのIngress管理に使用されるコンポーネントで、以下の脆弱性が含まれる：

| CVE | 深刻度 | 影響バージョン | 修正バージョン |
|-----|--------|--------------|--------------|
| CVE-2026-11311 | High | 2.3.0〜2.6.3 | 2.6.4 |
| CVE-2026-50107 | High | 2.3.0〜2.6.3 | 2.6.4 |

### HTTP/2 Bombとの関係

今回のアドバイザリには、別途CVE-2026-49975（HTTP/2 Bomb）として報告されているDoS脆弱性に対応するnginx 1.29.8への更新も含まれている。これにより、nginx 1.29.8以上への更新は複数の脆弱性への対策として重要である。

### 影響範囲

NGINX（エンジンエックス）はインターネット上で最も広く使用されているWebサーバーの一つで、WordPressを含む多くのWebアプリケーションのバックエンドとして機能している。また、Kubernetesクラスター上のIngress Controllerとして広く採用されているNGINX Ingress ControllerもNGINX Gateway Fabricの一部であり、クラウドネイティブ環境への影響も大きい。

### 推奨される対応

1. **すぐに更新**: NGINX Open Source → 1.29.8以上、NGINX Plus → 最新版
2. **Gateway Fabric使用者**: バージョン2.6.4に更新
3. **一時的な緩和策**: `rewrite`ディレクティブの使用を最小限に制限（CVE-2026-9256の回避）
4. **監視強化**: NGINXワーカープロセスの予期しない再起動（CVE-2026-9256の悪用兆候）を監視

---

## 関連記事

- [HTTP/2 Bomb（CVE-2026-49975）- 一台のPCでnginx・Apache・Envoyをダウン可能なDoS脆弱性](../articles/2026-06-19-http2-bomb-cve-2026-49975.md) - nginx 1.29.8で同時に修正されるDoS脆弱性
