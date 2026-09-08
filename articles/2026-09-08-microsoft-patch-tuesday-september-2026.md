# Microsoft、2026年9月のPatch Tuesdayで過去最多974件の脆弱性を修正、実悪用中のゼロデイ2件を含む

- **日付**: 2026-09-08
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-september-2026-patch-tuesday-fixes-966-flaws-2-zero-days/), [SecurityWeek](https://www.securityweek.com/microsoft-patches-record-974-vulnerabilities-including-two-exploited-zero-days/), [Cyber Security News](https://cybersecuritynews.com/microsoft-patch-tuesday-update-september-2026/)
- **トピック**: [Microsoft Patch Tuesday 2026年9月](../topics/microsoft-patch-tuesday-september-2026.md)
- **分類**: 新規

## 概要

Microsoftは2026年9月のPatch Tuesdayで、Windows・Office・SQL Server・Exchange・SharePoint・Azure等にまたがる過去最多となる974件の脆弱性を修正した。うち113件が最高深刻度の「Critical」、2件は既に実際の攻撃で悪用が確認されているゼロデイ（CVE-2026-85880、CVE-2026-81963）で、24時間以内の緊急パッチ適用が推奨されている。

## 詳細

今回のPatch Tuesdayは、これまでで最大規模のセキュリティ更新となった。修正された974件のうち113件がCriticalに分類され、内訳はリモートコード実行（RCE）が81件、権限昇格が20件、情報漏洩が2件、セキュリティ機能バイパスが1件となっている。対象製品はWindows本体にとどまらず、Microsoft Office、SQL Server、Exchange Server、SharePoint、Azure、開発者向けツール群など広範囲に及ぶため、組織はエンドポイント・サーバー・エンタープライズアプリケーション環境を横断した修正作業の調整が必要になる。

特に注意が必要なのは、既に実際の攻撃で悪用が確認されている2件の権限昇格ゼロデイである。

**CVE-2026-85880（Windows ALPC）**: Windows Advanced Local Procedure Call（ALPC）コンポーネントに存在するヒープベースのバッファオーバーフローおよび未初期化リソース使用の脆弱性。悪用に成功すると、ローカルの攻撃者がSYSTEM権限を取得できる。

**CVE-2026-81963（Windows Update Stack）**: Windows Update関連コンポーネントに存在する、ファイルアクセス前のリンク解決不備（link following）の脆弱性。こちらもローカル攻撃者による権限昇格をSYSTEM権限まで許す。

両脆弱性はいずれもローカル権限昇格であり、リモートから単独で悪用されるものではないが、フィッシングやマルウェア感染などで初期アクセスを得た攻撃者が、侵害後の水平展開・永続化のために組み合わせて使用するケースが多い。CISAのKnown Exploited Vulnerabilities（KEV）カタログへの追加も見込まれており、連邦政府機関には早期の修正適用義務が課される可能性が高い。

Microsoftは、影響範囲の広さと実悪用中のゼロデイが含まれることを踏まえ、Windows Update経由の自動適用に加え、サーバー環境やレガシーシステムを含む全対象製品への計画的なパッチ適用を強く推奨している。同社は過去にもPatch Tuesdayで大規模な修正をリリースしてきたが、今回の974件という件数は月次リリースとして過去最多であり、脆弱性の発見・報告ペースが引き続き高水準にあることを示している。
