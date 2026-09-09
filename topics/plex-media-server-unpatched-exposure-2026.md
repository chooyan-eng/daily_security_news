# Plex Media Server 未パッチ大量露出事案（2026年）

## 概要

メディアサーバーソフトウェア「Plex Media Server」において、2026年5月19日リリースのv1.43.3で修正済みの複数の未開示脆弱性（CVE番号は申請中で未割当）に対し、インターネットに公開されたまま未パッチで稼働しているサーバーが3万6000台超存在することを、Shadowserverが2026年9月4日以降の継続スキャンで確認。過去にはPlex Media Serverの脆弱性がLastPass侵害（2022年）の侵入起点になった前例がある。

**同一性の判断に役立つ情報：**
- 対象製品: Plex Media Server（v1.43.2以前が影響対象）／Plex Desktopクライアント（v1.115.0未満）
- 修正版: Plex Media Server v1.43.3（2026年5月19日リリース）、Plex Desktop v1.115.0（2026年8月13日リリース）
- CVE状況: 未割当（申請中）
- 露出台数: 3万6000台超（Shadowserverが2026年9月4日以降スキャン）
- 過去の関連事案: LastPass侵害（2022年、CVE-2020-5741悪用が侵入起点）

## タイムライン

- [2026-09-09 3万6000台超のPlex Media Serverが未パッチのまま公開状態、Shadowserverが継続監視](../articles/2026-09-09-plex-media-server-unpatched-exposure.md)
