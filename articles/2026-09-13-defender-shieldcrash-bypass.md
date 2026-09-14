# Microsoft Defenderゼロデイ「ShieldCrash」公開、ShieldBreak修正のバイパスでSYSTEM権限窃取

- **日付**: 2026-09-13
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/new-microsoft-defender-shieldcrash-zero-day-grants-system-access/), [SecurityWeek](https://www.securityweek.com/new-shieldcrash-zero-day-exploit-targets-microsoft-defender/), [GBHackers](https://gbhackers.com/windows-defender-shieldcrash-0-day/)
- **トピック**: [Microsoft Defender ShieldBreak ゼロデイ（CVE-2026-69414、2026年8月）](../topics/shieldbreak-defender-cve-2026-69414.md)
- **分類**: 続報

## 概要

研究者「Nightmare Eclipse」（別名Chaotic Eclipse）が、8月に公開したMicrosoft Defenderの権限昇格ゼロデイ「ShieldBreak」（CVE-2026-69414）に対するMicrosoftの修正をさらにバイパスする新たなPoC「ShieldCrash」を公開した。完全にパッチ適用済みのWindows 10／11／Serverでも、SYSTEM権限での任意ファイル読み取りが可能になるという。

## 詳細

ShieldCrashは、Microsoftが直近のセキュリティ更新でShieldBreak（CVE-2026-69414）を修正したと発表した直後に公開されたPoCエクスプロイトである。研究者Nightmare Eclipseによれば、Microsoftはこれまでに指摘されていた複数の悪用経路を塞いだものの、特定の条件下で同一の攻撃が依然として成立する抜け道を見落としているという。ShieldCrash自体はファイルへの書き込み権限までは付与しないが、SYSTEM権限での任意ファイル読み取り（arbitrary file read as SYSTEM）を引き起こすことが可能で、認証情報や機密設定ファイルの窃取につながり得る。

ShieldBreakはさらに、2026年6月に開示され7月に修正された別のDefenderの欠陥「RoguePlanet」に対する修正バイパスとして登場した経緯があり、ShieldCrashはその系譜に連なる3代目の修正バイパスとなる。Nightmare Eclipseは、これらのゼロデイ公開をMicrosoftのバグバウンティ制度および脆弱性開示対応方針への抗議の一環として続けていると説明している。

Microsoft Defenderは大多数のWindows環境で標準搭載されているセキュリティ製品であり、その内部コンポーネント自体が権限昇格の踏み台として繰り返し悪用される状況は、エンドポイント保護の前提を揺るがす問題として注視されている。本稿執筆時点でMicrosoftはShieldCrashに対する正式な修正状況を公表していない。

---
