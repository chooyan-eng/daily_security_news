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

## タイムライン

- [2026-07-06 AirDropとAndroid Quick Shareに6件の脆弱性 – 近接する攻撃者が数十億台のデバイスをクラッシュ・改ざん可能](../articles/2026-07-06-airdrop-quickshare-vulnerabilities.md)
