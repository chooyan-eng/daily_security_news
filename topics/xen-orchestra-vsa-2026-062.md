# Xen Orchestra 認証バイパス VSA-2026-062 の悪用（2026年11月）

## 概要

Vatesのアドバイザリ VSA-2026-062（CVE未採番）。Xen Orchestra / XOA の認証Cookie処理の不備により、細工したCookieで未認証の攻撃者がAdmin権限を取得でき、XCP-ngノードのroot乗っ取りに至る。実悪用を確認。修正版は Xen Orchestra 6.9.1 / 6.10.0、xo-server 5.211.2 / 5.213.1。IoCとして「pivot2」という名前のVM等が公開されている。

## タイムライン

- [2026-11-10 Xen Orchestraの重大な認証バイパス（VSA-2026-062）が実悪用、XCP-ngホスト乗っ取りの恐れ](../articles/2026-11-10-xen-orchestra-auth-bypass-exploited.md)
