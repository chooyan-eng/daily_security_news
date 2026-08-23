# Microsoft Defender BTR.sys 起動時修復ドライバ悪用手法（2026年8月）

## 概要

Check Point Researchが Black Hat USA 2026／DEF CON 34で公表した、Microsoft Defenderの正規署名済みカーネルドライバ「BTR.sys」（Boot Time Removal Tool）を悪用し、ソフトウェアの脆弱性を突かずにカーネルレベルの任意のファイル・レジストリ操作を実行できる手法。Windows 7〜Windows 11 25H2の各バージョンに影響するが、ドライバが設計通りに動作しているだけであるためCVEは採番されておらず、パッチも予定されていない。

**同一性の判断に役立つ情報：**
- 発表者: Jiří Vinopal氏（Check Point Research）
- 発表イベント: Black Hat USA 2026 / DEF CON 34（2026年8月20日発表・PoC公開）
- 対象コンポーネント: BTR.sys（Boot Time Removal Tool、Microsoft Defenderの起動時修復ドライバ）
- 対象OS: Windows 7〜Windows 11 25H2
- 悪用の性質: ドライバの正規機能悪用（ソフトウェアバグ非依存）、CVE番号なし・パッチ予定なし
- 悪用条件: `SeLoadDriverPrivilege`権限を持つ攻撃者による、ADS格納のRC4暗号化トランザクションリストの細工
- 公開PoCツール: BTR_CLI（オープンソース）
- 対策が困難な理由: BTR.sysはWindows必須コンポーネントであり、脆弱ドライバブロックリストやWDACでの単純ブロックがDefender自体の動作を阻害する

## タイムライン

- [2026-08-22 Check Point、Microsoft Defender純正ドライバ「BTR.sys」を悪用したセキュリティ製品無効化手法を公開](../articles/2026-08-22-checkpoint-btr-sys-defender-weaponization.md)
