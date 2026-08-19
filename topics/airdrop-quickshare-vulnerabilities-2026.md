# AirDrop・Quick Share 近接ファイル共有プロトコル脆弱性（2026年）

## 概要

Apple AirDropとGoogle/Samsung Quick Shareの近接無線ファイル共有プロトコルに合計6件の脆弱性が発見された事案。3件はAirDropのバックグラウンドサービス「sharingd」をクラッシュさせるもの（AirPlay・Handoff・Universal Clipboard・Continuity Camera・NameDropも道連れで停止）、2件はQuick Shareのハンドシェイクをバイパスするもの。攻撃者は対象の10〜30メートル圏内にいるだけで攻撃可能で、世界で約50億台のデバイスが影響対象。

**同一性の判断に役立つ情報：**
- 対象プロトコル: Apple AirDrop（sharingdサービス）、Google/Samsung Quick Share
- 脆弱性件数: 6件（AirDrop 3件・Quick Share 2件）
- 攻撃距離: 約10〜30メートル
- 影響範囲: 約50億台のiPhone・Android端末
- 影響サービス: AirPlay、Handoff、Universal Clipboard、Continuity Camera、NameDrop（sharingd経由で連鎖停止）
- パッチ状況: Apple側1件パッチ済み・CVE未公開、残り2件協調開示中／Google側コード修正済み・CVE未確定
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

- [2026-07-06 AirDropとAndroid Quick Shareに6件の脆弱性 – 近接する攻撃者が数十億台のデバイスをクラッシュ・改ざん可能](../articles/2026-07-06-airdrop-quickshare-vulnerabilities.md)
- [2026-07-04 AirDropとQuick Shareに6件の脆弱性、50億台規模のデバイスに影響——近接した攻撃者が無許可でクラッシュを誘発](../articles/2026-07-04-airdrop-quickshare-vulnerabilities.md)
- [2026-06-30 AirDropとQuick Shareに複数の脆弱性、近接攻撃者がクラッシュやチェック回避を実行可能](../articles/2026-06-30-airdrop-quickshare-vulnerabilities.md)
