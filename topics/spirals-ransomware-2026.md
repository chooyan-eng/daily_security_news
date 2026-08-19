# Spirals ランサムウェア（2026年）

## 概要

インターネットに公開された IIS Web サーバーの侵害を起点に、初期侵入から情報窃取・暗号化完了まで24時間未満で完了させる新型ランサムウェア「Spirals」。ASP.NET Web シェル設置、UAC バイパス、WMI 横展開、revsocks/Chisel/Cloudflare トンネルによる冗長 C2 経路確立を経て、Rust 製ランサムウェア（断続的暗号化、AES-128 + ECDH P-256）で暗号化する。二重恐喝型で、身代金メモは `RECOVERY_SECTION.log`。

**同一性の判断に役立つ情報：**
- ランサムウェア名: Spirals
- 実装言語: Rust
- 暗号化方式: AES-128（ECDH P-256 で保護）、5MB超のファイルは断続的暗号化
- 身代金メモ: `RECOVERY_SECTION.log`
- 侵入経路: インターネット公開 IIS Web サーバー + ASP.NET Web シェル
- 初動事例: 南アジアの IT サービス企業（2026年6月16日侵入開始）

## タイムライン

- [2026-07-19 新型ランサムウェア「Spirals」、公開 IIS Web サーバー侵害から24時間以内に暗号化を完了](../articles/2026-07-19-spirals-ransomware-iis-webshell.md)
