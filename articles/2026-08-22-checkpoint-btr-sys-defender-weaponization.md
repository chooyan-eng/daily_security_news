# Check Point、Microsoft Defender純正ドライバ「BTR.sys」を悪用したセキュリティ製品無効化手法を公開

- **日付**: 2026-08-22
- **出典**: [Check Point Research](https://research.checkpoint.com/2026/btr-reforged-weaponizing-defenders-remediation-driver-as-a-kernel-operation-primitive/) / [The Hacker News](https://thehackernews.com/2026/08/microsoft-defenders-own-driver-can-be.html)
- **トピック**: [Microsoft Defender BTR.sys 起動時修復ドライバ悪用手法（2026年8月）](../topics/checkpoint-btr-sys-defender-weaponization-2026.md)
- **分類**: 新規

## 概要

Check Point Researchが、Microsoft Defenderの正規署名済みドライバ「BTR.sys」（Boot Time Removal Tool）を悪用し、ソフトウェアの脆弱性を突くことなくカーネルレベルのファイル・レジストリ操作を実行できる手法をBlack Hat USA 2026／DEF CON 34で発表した。CVEは採番されておらずパッチも予定されていない。

## 詳細

### BTR.sysとは

BTR.sysは、Windows 7からWindows 11 25H2までの各バージョンに組み込まれている、Microsoft Defenderの起動時修復（Boot Time Removal）を担う正規のカーネルモードドライバである。マルウェア感染時にOS起動前の段階でファイルシステムやレジストリを修復するために設計されており、Windowsの必須コンポーネントの一つとして扱われている。

### 悪用手法の仕組み

研究者Jiří Vinopal氏によると、BTR.sysは代替データストリーム（ADS）に格納されたRC4暗号化のトランザクションリストを起動時に復号し、Ring 0（カーネル権限）で処理を実行する。`SeLoadDriverPrivilege`を持つ攻撃者は、この暗号化トランザクションリストを細工することで、正規のドライバの動作を通じて任意のファイル削除・レジストリ改変などのRing 0操作を実行できる。ソフトウェアバグを突くものではなく、ドライバが「設計通りに」動作する過程を悪用する点が特徴である。

### 悪用がもたらす影響

この手法により、フルパッチ済みかつDefenderで保護された状態のWindows端末から、Defenderのスタック全体を起動段階で削除するデモンストレーションが公開された。ファイルシステムが利用可能になるがDefenderの保護機構自体はまだ起動していない、起動シーケンス中の「隙間」の時間帯を突く点がポイントとされる。

### 対策が困難な理由

BTR.sysはWindowsの必須コンポーネントであるため、Microsoftの脆弱ドライバブロックリストへの追加や、Windows Defender Application Control（WDAC）による単純なブロックは、Defender自体の動作を阻害してしまう。ドライバが本来の設計通りに機能しているだけであるため、修正すべき「脆弱性」が存在せず、CVE番号も付与されていない。

### 検知に向けた対応

Vinopal氏は、発表と同時に概念実証ツール「BTR_CLI」をオープンソースとして公開し、シグネチャベースではなく挙動ベースの検知手法に関するガイダンスも併せて提供した。防御側には、ドライバのシグネチャ検証だけに依存せず、起動シーケンス中のファイル・レジストリ操作の異常な挙動を監視する体制が求められる。

---

## 関連記事

- [Microsoft Defender ゼロデイ「ShieldBreak」（CVE-2026-69414）、パッチ未提供のままCISA指令の期限が迫る](../articles/2026-08-20-shieldbreak-cve-2026-69414-defender-zero-day.md) - Black Hat/DEF CON 2026前後で相次いで公表された、Microsoft Defenderの内部コンポーネントを悪用する別系統の手法
