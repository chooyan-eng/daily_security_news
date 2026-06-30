# AirDrop・Quick Share 近接共有プロトコル脆弱性（2026年）

## 概要

CISPAヘルムホルツ情報セキュリティセンターの研究者が、Apple AirDropとGoogle/Samsung Quick Shareの近接無線ファイル共有プロトコルに計6件の脆弱性を発見。無線到達範囲内の攻撃者が事前接続なしにMac・iPhoneの共有サービスをクラッシュさせたり、Quick Shareのセッションチェックを回避したりできる。推定50億台規模のデバイスに影響。

**同一性の判断に役立つ情報：**
- 発見者: Arash Ale Ebrahim、Nils Ole Tippenhauer（CISPAヘルムホルツ情報セキュリティセンター）
- 対象プロトコル: Apple AirDrop、Google/Samsung Quick Share
- 脆弱性件数: 計6件（AirDrop側のXML property listパーサーのスタックオーバーフロー等、Quick Share側のセッションチェックバイパス・use-after-free等）
- 影響OS: macOS・iOS・watchOS・tvOS・visionOS、Windows（Quick Shareクライアント）
- 修正状況: Apple iOS/macOS 26.5.2（2026年6月29日リリース）で修正、Google Quick Share Windowsクライアントも修正済み

## タイムライン

- [2026-06-30 AirDropとQuick Shareに複数の脆弱性、近接攻撃者がクラッシュやチェック回避を実行可能](../articles/2026-06-30-airdrop-quickshare-vulnerabilities.md)
