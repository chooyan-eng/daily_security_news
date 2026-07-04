# AirDrop・Quick Share 近接無線共有プロトコル脆弱性（2026年）

## 概要

CISPAヘルムホルツ情報セキュリティセンターの研究者が発見した、AppleのAirDropおよびGoogle/SamsungのQuick Shareにおける6件の脆弱性群。macOS・iOS・Android・Windowsにまたがり、AirDrop側3件のサービスクラッシュ（DoS）系脆弱性、Quick Share側2件のハンドシェイクバイパス、1件のuse-after-free（RCEにつながる可能性）から成る。無線圏内の攻撃者が事前接続やタップ操作なしに攻撃可能。影響を受けるデバイス規模は合計50億台規模とされる。

**同一性の判断に役立つ情報：**
- 発見者: CISPAヘルムホルツ情報セキュリティセンター研究者
- 対象プロトコル: Apple AirDrop（macOS/iOS）、Google/Samsung Quick Share（Android/Windows）
- 脆弱性件数: 6件（AirDrop側3件のDoS、Quick Share側2件のハンドシェイクバイパス、1件のuse-after-free）
- 影響台数: AirDrop（sharingd稼働）22億台以上、Quick Share 30億台以上
- 公表日: 2026年6月30日
- 攻撃条件: 無線圏内・事前接続不要・タップ/プロンプトなし
- 研究論文: 「Protocol Prying: Systematic Vulnerability Research in the Apple AirDrop and Android Quick Share Proximity Transfer Protocols」（arXiv）

## タイムライン

- [2026-07-04 AirDropとQuick Shareに6件の脆弱性、50億台規模のデバイスに影響——近接した攻撃者が無許可でクラッシュを誘発](../articles/2026-07-04-airdrop-quickshare-vulnerabilities.md)
