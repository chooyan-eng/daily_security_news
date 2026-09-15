# 複数の中国系ハッカー集団、同一のChrome／Windowsゼロデイ連鎖エクスプロイトを共有し使用

- **日付**: 2026-09-14
- **出典**: [CyberScoop](https://cyberscoop.com/china-espionage-groups-exploit-chain-zero-days/), [Volexity](https://www.volexity.com/blog/2026/09/09/mind-the-patch-gap-multiple-chinese-threat-actors-chain-0-day-exploits-in-chrome-windows/), [GBHackers](https://gbhackers.com/china-linked-hackers-exploit-chrome-and-windows-zero-days/)
- **トピック**: [Chrome V8 ゼロデイ CVE-2026-87491（2026年9月）](../topics/chrome-v8-cve-2026-87491-zero-day-2026.md)
- **分類**: 続報

## 概要

Volexityは、少なくとも4つの中国関連スパイ活動グループが、Chromeおよび同系統ブラウザのV8エンジン脆弱性（CVE-2026-85046、CVE-2026-87491）とWindowsの権限昇格ゼロデイ（CVE-2026-85880）を連鎖させた、バイト単位で同一のエクスプロイトチェーンを共有して使用していると報告した。航空宇宙・製造業・政府機関・コンサルティング・金融業界などが標的とされている。

## 詳細

Volexityが自社のネットワーク監視基盤を通じて9月1日に検知した攻撃活動では、標的組織のWebサイトに仕込まれた反射型XSS脆弱性を悪用し、被害者を脅威アクター管理下のインフラへ誘導、多段階のエクスプロイトチェーンを展開する手口が確認された。攻撃チェーンはブラウザのサンドボックス内でコードを実行した後、サンドボックスを脱出し、Windowsのシステム権限を奪取するというものである。

観測された脅威アクターには、APT31／Violet Typhoon／TA412として知られるJungleBamboo、UTA0560のほか、UNK_LateNight、UNK_DoubleCheck、UNK_QuietRacketといった複数のクラスタが含まれる。ブラウザおよびWindowsのエクスプロイトコード自体はバイト単位で同一だった一方、侵入後に展開されるペイロードはグループごとに異なっていたといい、複数の攻撃者間でエクスプロイト開発基盤や供給元を共有している可能性が指摘されている。

CVE-2026-85046とCVE-2026-87491はいずれもGoogleが2026年9月に修正済みのChrome V8エンジンの実悪用済みゼロデイであり、既報のChromeゼロデイ一連の脆弱性が、公開後間もない時期から国家関連の攻撃者によって実際の標的型攻撃に転用されていたことを裏付ける事例となる。パッチ適用に加え、Windows側のCVE-2026-85880についても修正状況の確認が推奨される。

---

## 関連記事

- [Google、Chromeで2026年7件目となる実悪用中のV8ゼロデイCVE-2026-87491を修正](../articles/2026-09-09-chrome-v8-zeroday-cve-2026-87491.md) - 悪用されたV8ゼロデイの初報
