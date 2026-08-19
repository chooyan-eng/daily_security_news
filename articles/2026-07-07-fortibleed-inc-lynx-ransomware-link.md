# FortiBleed続報：認証情報流出キャンペーンがINC・Lynxランサムウェア攻撃と関連

- **日付**: 2026-07-07
- **出典**: [SOCRadar](https://socradar.io/blog/fortibleed-inc-lynx-ransomware-link/), [The Hacker News](https://thehackernews.com/2026/07/fortibleed-credential-theft-linked-to.html), [BleepingComputer](https://www.bleepingcomputer.com/news/security/fortibleed-credential-theft-campaign-linked-to-lynx-ransomware/)
- **トピック**: [FortiBleed：Fortinet Firewall 大規模認証情報流出キャンペーン（2026年6月）](../topics/fortibleed-fortinet-credential-harvesting.md)
- **分類**: 続報

## 概要

SOCRadarが、Fortinet FortiGateを標的とした大規模認証情報流出キャンペーン「FortiBleed」が、INC RansomおよびLynxランサムウェアの攻撃基盤と直接関連していることを突き止めた。FortiBleedのインフラにアクセスできる関係者が、両ランサムウェア組織の交渉パネルにログインしていた痕跡が確認され、盗取した認証情報がランサムウェア攻撃の足がかりに使われていたことが裏付けられた。

## 詳細

SOCRadarは、6月に警告を発していたFortinet FortiGateファイアウォールを狙う大規模認証情報流出キャンペーン「FortiBleed」について、INC RansomおよびLynxランサムウェアオペレーションとの直接的な関連を新たに特定した。

分析によると、FortiBleedのインフラへアクセス権を持つオペレーターの一人が、INC RansomとLynxの両方の被害者交渉パネルにログインしていたことが確認された。さらに、INC Ransomが公表している被害者リストと、FortiBleedキャンペーンで収集されたデータとの間に重複が見られたことも、両者の関連を裏付ける証拠となっている。この関連付けにより、FortiBleedで窃取されたFortinet認証情報が、将来のネットワーク侵入・ランサムウェア展開の足がかりとして使われることを意図したものであった可能性が高いことが明らかになった。

技術的な手口としては、侵害されたFortiGateファイアウォール上で「FortiGate Sniffer」と呼ばれる独自のパケットスニッフィングツールが使用され、ネットワークトラフィックから直接VPN認証情報や他の認証データを傍受していたことが判明している。

キャンペーンの規模についても新たな情報が示された。SOCRadarは約11,250件のFortiGateポータルに対するスキャン活動を150カ国以上で追跡し、そのうち409件で管理者レベルのアクセスが確認され、354件で攻撃チェーンが完全に完了したことを突き止めた。この結果、少なくとも12件のランサムウェア展開がこのアクセス経路に起因すると報告されている。内部の追跡文書の分析からは、主要なオペレーター数名を中心に、専門要員とジュニアオペレーター・技術支援層からなる約20人規模の組織的な運用体制であったことも示唆されている。

本件は、単なる大規模認証情報収集キャンペーンとして始まったFortiBleedが、実際にはランサムウェアグループへの初期アクセス供給網として機能していたことを示すものであり、Fortinet製品を利用する組織に対しては、既に案内されている緩和策の適用状況の再確認と、侵害の兆候（想定外のVPNログイン、異常な管理者アクセスなど）の調査が改めて強く推奨される。
