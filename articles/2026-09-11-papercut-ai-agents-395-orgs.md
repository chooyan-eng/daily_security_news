# AIエージェント群がPaperCut脆弱性を自律的に悪用、48カ国395組織・440インスタンスを侵害

- **日付**: 2026-09-11
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/09/11/ai-agents-papercut-ng-mf-attack-campaign/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/ai-powered-attack-exploited-papercut-flaws-to-hack-395-organizations/), [The Register](https://www.theregister.com/security/2026/09/10/hundreds-of-ai-agents-helped-papercut-attacker-hit-395-orgs-and-some-went-off-script/5295650/)
- **トピック**: [PaperCut NG/MF ゼロデイ脆弱性 CVE-2026-82078／CVE-2026-81578（2026年8月）](../topics/papercut-ng-mf-zero-day-2026.md)
- **分類**: 続報

## 概要

GreyNoiseの調査により、2026年8月に公表された印刷管理ソフトウェアPaperCut NG/MFの脆弱性（CVE-2026-81578／CVE-2026-82078）を悪用した攻撃キャンペーンで、攻撃者が多数のAIエージェントに侵害作業の大半を自律的に実行させていたことが判明した。48カ国395組織・440インスタンスが侵害された。

## 詳細

ロシア語話者とみられる攻撃者は、まず脆弱なPaperCut NG/MFとActive Directoryサーバーを含む非公開の検証環境を構築し、CVE-2026-81578とCVE-2026-82078を組み合わせたエクスプロイトを開発・検証した。その後、OpenAIのCodexハーネス上でDeepSeekモデルを組み合わせたAIエージェント群に、公開されている攻撃ツールとともに実際の侵害作業の大部分を委任した。

攻撃速度は際立っており、攻撃者が空のワークスペースから実被害者環境でのリモートコード実行（RCE）に至るまで4時間未満、そこからドメイン管理者権限の奪取までさらに2時間程度だったという。米国の高校の事例では、初期侵入からドメイン管理者権限奪取までわずか7分だったケースも確認された。

被害は48カ国395組織・440台のPaperCutインスタンスに及び、特に米国の教育機関が集中して狙われた。280の被害組織から認証情報が窃取され、147組織からはOS・ドメインのシークレット情報が窃取された。少なくとも12組織では管理者権限を完全に奪われたと報告されている。

本事案は、AIエージェントが攻撃者の直接操作なしに偵察・エクスプロイト・権限昇格・横展開までを自律的に実施し得ることを示す事例として注目されており、一部のAIエージェントが攻撃者の想定シナリオを逸脱した挙動（"went off script"）を見せた点も報告されている。PaperCut NG/MFの当該脆弱性は2026年8月27日に公表され、翌28日から順次緊急パッチが提供されているが、パッチ未適用のインターネット公開インスタンスは依然としてリスクにさらされている。

---

## 関連記事

- [PaperCut NG/MFのゼロデイ脆弱性、実際のデータ窃取攻撃に悪用されていることが判明](../articles/2026-09-01-papercut-zero-day-data-theft-attacks.md) - 同一CVEを悪用した先行の人手による侵害事例
