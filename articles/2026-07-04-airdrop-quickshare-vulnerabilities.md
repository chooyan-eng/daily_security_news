# AirDropとQuick Shareに6件の脆弱性、50億台規模のデバイスに影響——近接した攻撃者が無許可でクラッシュを誘発

- **日付**: 2026-06-30
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/airdrop-and-quick-share-flaws-let.html)、[Help Net Security](https://www.helpnetsecurity.com/2026/06/30/apple-airdrop-google-samsung-quick-share-vulnerabilities/)、[arXiv論文](https://arxiv.org/html/2606.26967v1)
- **トピック**: [AirDrop・Quick Share 近接無線共有プロトコル脆弱性（2026年）](../topics/airdrop-quickshare-vulnerabilities-2026.md)
- **分類**: 新規

## 概要

CISPAヘルムホルツ情報セキュリティセンターの研究者が、AppleのAirDropとGoogle/SamsungのQuick Shareという近接無線ファイル共有プロトコルに、合計6件の脆弱性を発見した。無線圏内にいる攻撃者は、事前の接続やタップ操作なしに、対象デバイスの共有サービスをクラッシュさせたり、セキュアなハンドシェイクをバイパスしたりできる。Apple・Google・Samsungは順次修正を進めている。

## 詳細

### 脆弱性の内訳

研究者らはmacOS・iOS・Android・Windowsにまたがる6件の脆弱性を発見した。内訳はAirDrop側の3件のサービスクラッシュ（DoS）系脆弱性、Quick Share側の2件のプロトコル状態操作エクスプロイト、および1件のuse-after-free脆弱性（RCEにつながる可能性あり）。

**AirDrop側の脆弱性**：
- 1件目：単一のHTTP POSTリクエストで、AirDrop・AirPlay・Handoff・Universal Clipboard・Continuity Cameraを担うmacOS/iOSの`sharingd`サービスを即座にクラッシュさせられる。
- 2件目：深くネストしたXML property listを含む不正な形式のリクエストにより、パース処理中にスタックオーバーフローが発生する。
- 3件目：重複または矛盾するヘッダーを含む意図的に破損したWebリクエストを悪用するもの。

**Quick Share側の脆弱性**：
- SamsungのQuick Shareにおいて、セッションを保護するはずのハンドシェイクをバイパスできる2件の脆弱性。1つはUKEY2暗号化が完了する前に未認証デバイスが接続を開始できてしまうもの、もう1つは、セキュアセッション確立後であっても特定の制御メッセージが暗号化されずに通過してしまうもの。
- さらに、RCEにつながりうるuse-after-free脆弱性も確認された。

### 影響規模

Appleは`sharingd`を稼働中のアクティブデバイスが22億台以上あると報告しており、Googleも同様にQuick Shareがデフォルトの共有機構として動作するAndroidデバイスが30億台以上あるとしている。AirDropとQuick Shareを合わせると、影響を受けうるデバイスの規模は50億台に達するとされる。

### 攻撃の容易さ

攻撃者は無線圏内にいて、ノートPC一台があれば、事前の接続なしに「全員から受信」に設定されたMacやiPhoneの共有サービスをタップや確認プロンプトなしにクラッシュさせることができる。

### 対応状況

Apple・Google・Samsungはこの脆弱性群について修正を順次進めている段階。深刻度としては「重大ではあるが、直ちに壊滅的な脅威ではない」との評価も一部専門家からなされている。

---

## 関連記事

なし（新規トピック）
