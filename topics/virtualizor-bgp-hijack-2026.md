# Virtualizor BGPハイジャックによる悪意ある更新配信事案（2026年）

## 概要

VPS管理パネル「Virtualizor」の更新配信元Softaculousが使用するIPアドレス帯に対するBGPハイジャック攻撃。Virtualizorの更新クライアントがパッケージの署名検証を行っていなかったため、経路乗っ取り＋正規TLS証明書の組み合わせのみでroot権限のコード実行が可能となり、一部ホスティング事業者のハイパーバイザーが侵害された。

**同一性の判断に役立つ情報：**
- 対象製品: Virtualizor（VPS管理パネル、更新・課金基盤はSoftaculous）
- 攻撃手法: BGPハイジャック（AS62390 NexonHostがHetznerブロック162.55.80.0/24をAS6204 Zet.net経由で広告）
- 攻撃期間: 2026年8月28日20:57 UTC 〜 8月30日6:10 UTC
- 根本原因: Virtualizor更新クライアントによるパッケージ署名検証の欠如
- 侵害内容: rootアカウントへの攻撃者公開鍵追加、Java 17経由ペイロード実行、systemd永続化、不正アカウント「proxyuser」作成
- 影響対象: Virtualizorで管理されるKVM/Xen/LXC/OpenVZ/Proxmox等のハイパーバイザー

## タイムライン

- [2026-09-02 BGPハイジャックでVirtualizor更新配信網が乗っ取られ、ホスティング事業者のハイパーバイザーがroot権限奪取](../articles/2026-09-02-virtualizor-bgp-hijack-malicious-update.md)
