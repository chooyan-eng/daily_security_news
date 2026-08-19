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
- 発見者: Arash Ale Ebrahim、Nils Ole Tippenhauer（CISPAヘルムホルツ情報セキュリティセンター）
- 対象プロトコル: Apple AirDrop、Google/Samsung Quick Share
- 脆弱性件数: 計6件（AirDrop側のXML property listパーサーのスタックオーバーフロー等、Quick Share側のセッションチェックバイパス・use-after-free等）
- 影響OS: macOS・iOS・watchOS・tvOS・visionOS、Windows（Quick Shareクライアント）
- 修正状況: Apple iOS/macOS 26.5.2（2026年6月29日リリース）で修正、Google Quick Share Windowsクライアントも修正済み

## タイムライン

- [2026-07-04 AirDropとQuick Shareに6件の脆弱性、50億台規模のデバイスに影響——近接した攻撃者が無許可でクラッシュを誘発](../articles/2026-07-04-airdrop-quickshare-vulnerabilities.md)
- [2026-06-30 AirDropとQuick Shareに複数の脆弱性、近接攻撃者がクラッシュやチェック回避を実行可能](../articles/2026-06-30-airdrop-quickshare-vulnerabilities.md)
