# 3万6000台超のPlex Media Serverが未パッチのまま公開状態、Shadowserverが継続監視

- **日付**: 2026-09-09
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/over-36-000-plex-servers-unpatched-against-recently-disclosed-flaws/), [The Hacker News](https://thehackernews.com/2026/09/plex-urges-immediate-updates-after.html)
- **トピック**: [Plex Media Server 未パッチ大量露出事案（2026年）](../topics/plex-media-server-unpatched-exposure-2026.md)
- **分類**: 新規

## 概要

メディアサーバーソフトウェア「Plex Media Server」において、既に修正済みの複数のセキュリティ脆弱性に対し、インターネットに公開されたままのサーバーが3万6000台以上存在することが、脅威インテリジェンス機関Shadowserverの継続的なスキャンにより判明した。

## 詳細

Plexは2026年5月19日、v1.43.3において複数の未開示セキュリティ脆弱性を修正した。しかしこれらの脆弱性には現時点でもCVE番号が割り当てられておらず（申請中とされる）、防御側が脆弱性管理システムで追跡・優先順位付けを行う上での可視性が制限されている状況にある。対象となるのはv1.43.2以前のPlex Media Serverで、あわせてPlex Desktopクライアントもv1.115.0（2026年8月13日リリース）未満のバージョンが影響を受ける。

Shadowserverは2026年9月4日以降、インターネットに露出した未パッチのPlex Media Serverインスタンスを日次でスキャン・報告する取り組みを開始しており、その結果3万6000台を超えるサーバーが依然として脆弱なバージョンのまま稼働していることが明らかになった。Plexは1週間前にもユーザーに対し即座のセキュリティ対応を呼びかけていたが、パッチ適用率は低調である。

Plex Media Serverの脆弱性を巡っては、過去にも深刻なインシデントとの関連が指摘されている。2022年に発生したパスワード管理サービスLastPassの侵害では、攻撃者が従業員の自宅PCに存在したPlex Media Serverの脆弱性（CVE-2020-5741、CVSS 7.2）を悪用してキーロガーマルウェアを仕込んだことが侵入の起点になったと報告されている。家庭用途で広く使われるメディアサーバーソフトウェアが、企業ネットワークへの侵入経路になり得ることを改めて示す事例として注目されている。

Plex利用者には、Media Serverをv1.43.3以降、Desktopクライアントをv1.115.0以降へ直ちにアップデートすること、および管理インターフェースを不必要にインターネットへ公開しないことが強く推奨される。
