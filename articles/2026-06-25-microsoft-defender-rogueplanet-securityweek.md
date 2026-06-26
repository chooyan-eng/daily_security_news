# Microsoft Defender RoguePlanet（CVE-2026-50656）— パッチ未提供の状態が継続、SecurityWeek が現状を報告

- **日付**: 2026-06-25
- **出典**: [SecurityWeek](https://www.securityweek.com/microsoft-working-on-patch-for-rogueplanet-zero-day/)
- **トピック**: [Microsoft Defender RoguePlanet ゼロデイ（CVE-2026-50656）](../topics/microsoft-defender-rogueplanet-2026.md)
- **分類**: 続報

## 概要

SecurityWeek は、Microsoft Defender の TOCTOU 競合状態脆弱性「RoguePlanet」（CVE-2026-50656）について、Microsoft が依然としてパッチを開発中であることを報告した。研究者「Nightmare Eclipse」が6月10日にゼロデイとして公開し、6月24日に PoC を公開してから2週間が経過したが、完全パッチ済みの Windows 10/11 においてSYSTEM権限奪取が可能な状態が続いている。

## 詳細

### 現状サマリー

**CVE**: CVE-2026-50656  
**別名**: RoguePlanet  
**CVSS**: 7.8（Important）  
**種別**: ローカル特権昇格（LPE）/ TOCTOU 競合状態  
**対象**: Windows Defender Malware Protection Engine  
**パッチ状況**: 未提供（Microsoft 開発中）  
**PoC 公開日**: 2026年6月24日

### Microsoft の対応状況

Microsoft は SecurityWeek の取材に対し、パッチの開発中であることを認め、顧客保護のため修正を急いでいると回答した。ただし具体的なリリース日程は示されておらず、アウトオブバンドのセキュリティ更新プログラムとして提供されるか、次回の Patch Tuesday（2026年7月）まで待つかは未確定。

Microsoft Security Response Center（MSRC）は CVE-2026-50656 を登録し、深刻度を「Important」と評価しているが、現時点では回避策（Workaround）の提供も行っていない。

### RoguePlanet のリスク評価

**攻撃シナリオ**:
1. 低権限ユーザー（または悪意あるコード）が Windows Defender の Malware Protection Engine における競合状態をトリガー
2. ファイルスキャン処理のタイミングを悪用してSYSTEM権限への昇格を達成
3. エンドポイントの完全制御を掌握

**実際の悪用リスク**:
- PoC が公開済みのため、攻撃者がパッチなしで悪用できる期間が延長中
- Windows Defender は Windows に標準搭載されており、影響を受けるシステム数は膨大
- ランサムウェア・APT グループが初期侵入後の特権昇格に悪用するリスクが高い

### 緩和策（パッチ適用まで）

- Windows Defender のリアルタイム保護を無効化することは逆効果（これにより保護が低下する）
- サードパーティの EDR ソリューションが存在する場合、Windows Defender を補完的に設定
- 最小権限の原則を徹底し、ローカル管理者権限を持つアカウントを最小化
- 異常なSYSTEM権限プロセスの生成を監視

### YellowKey/GreenPlasma/MiniPlasma との関係

同研究者「Nightmare Eclipse」は、同じ期間に YellowKey（CVE-2026-45585）・GreenPlasma（CVE-2026-45586）・MiniPlasma（CVE-2020-17103）も発見しており、こちらは6月10日 Patch Tuesday で既に修正されている。RoguePlanet のみが未修正状態であり、特に注意が必要。

---

## 関連記事

なし
