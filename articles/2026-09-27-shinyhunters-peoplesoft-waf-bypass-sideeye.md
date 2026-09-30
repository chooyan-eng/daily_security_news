# ShinyHunters、URLエンコードでWAFを回避しOracle PeopleSoft攻撃を再開

- **日付**: 2026-09-27
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-uses-waf-bypass-trick-in-oracle-peoplesoft-attacks/), [Hackread](https://hackread.com/shinyhunters-bypass-waf-rules-oracle-peoplesoft-attacks/)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 続報

## 概要

恐喝グループShinyHunters（Mandiant追跡名UNC6240）が、Oracle PeopleSoftの脆弱性CVE-2026-35273に対するWAF（Webアプリケーションファイアウォール）緩和策をURLエンコードのトリックで回避し、パッチ未適用サーバーへの攻撃を再開していることをGoogle Mandiant/GTIGが確認した。教育・技術・医療・政府機関が新たな標的となっている。

## 詳細

多くの組織はCVE-2026-35273のパッチ適用に加え、脆弱な`/PSEMHUB/`エンドポイントへのアクセスをWAFやリバースプロキシでブロックする緩和策を講じていた。しかしShinyHuntersは、パス文字列の一部をパーセントエンコード（URLエンコード）した上でリクエストを送信する手法を新たに用いている。多くのWAFやリバースプロキシはデコード前のリクエストパス文字列をそのままルール照合に使うため、エンコードされた`/PSEMHUB/`はブロックルールに一致しない。一方でOracle WebLogicはリクエストをデコードしてから処理するため、結果的に脆弱なエンドポイントへそのままルーティングされてしまう。

この手法により、WAFでパッチ未適用サーバーへのアクセスを遮断していたつもりの組織も再び攻撃対象となった。GoogleのMandiantおよびThreat Intelligence Group（GTIG）は、この新手口を用いた攻撃でWebシェルの設置や、ShinyHuntersが過去のキャンペーンでも使用してきたバックドア「SIDEEYE」の展開が確認されたと報告している。標的は教育機関、テクノロジー企業、医療機関、政府機関など多岐にわたる。

CVE-2026-35273は2026年5月27日〜6月9日にかけて大学を中心に100組織・300インスタンス超が侵害された未パッチゼロデイで、Oracleは6月10日にパッチを公開済みである。今回の事案は、パッチだけでなくWAFルールの回避を前提とした多層防御の再点検が必要であることを示しており、単純な文字列一致によるパスブロックの限界を浮き彫りにしている。管理者にはパッチ未適用サーバーの即時特定に加え、WAF側でのデコード後パス評価やOracle WebLogic側のログ監視強化が推奨されている。
