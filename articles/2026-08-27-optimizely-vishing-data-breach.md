# アドテク大手Optimizely、ビッシング攻撃によるデータ侵害を公表 ― ShinyHuntersの関与か

- **日付**: 2026-08-27
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/ad-tech-firm-optimizely-confirms-data-breach-after-vishing-attack/), [SecurityWeek](https://www.securityweek.com/ad-tech-company-optimizely-confirms-cyberattack/), [TechRadar](https://www.techradar.com/pro/security/top-ad-tech-firm-optimizely-hit-by-data-breach-around-10-000-companies-possibly-affected)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 続報

## 概要

米アドテク大手Optimizelyが、ボイスフィッシング（ビッシング）攻撃を受けてシステムの一部が侵害され、顧客の基本的なビジネス連絡先情報が窃取されたと公表した。侵害の背後にはShinyHuntersが関与しているとみられている。Optimizelyの顧客にはH&M、PayPal、Zoom、トヨタ等1万社超が含まれ、二次的なフィッシング悪用への注意が呼びかけられている。

## 詳細

ニューヨークを拠点とするアドテク企業Optimizelyは、顧客宛の通知書簡において、脅威アクターが従業員になりすましたIT部門を装ってログイン情報や多要素認証（MFA）コードをだまし取る手口で一部システムへ接続したことを明らかにした。脅威アクターからは2月11日にシステムへのアクセスを保持しているとの接触があったとされている。

Optimizelyによれば、攻撃者は同社の一部システムに侵入したものの、権限昇格やソフトウェアのインストール、バックドアの設置には至らなかったとしている。窃取が確認された情報は「基本的な事業連絡先情報」にとどまり、機密性の高い顧客データや個人情報へのアクセスを示す証拠は確認されていないと説明している。

本件の脅威アクターはShinyHuntersであるとみられている。ShinyHuntersはビッシングやOAuth連携の悪用を通じてSaaS環境を狙う手口で知られており、2026年に入ってから複数企業（Carhartt、Sharecare、Questel、Lumenis、BOK Financial、ReliaQuestなど）への攻撃を主張・実行してきた一連のSaaS恐喝キャンペーンの延長線上にある事案と位置づけられる。

Optimizelyの顧客基盤は1万社を超え、H&M、PayPal、Zoom、トヨタ、ボーダフォン、シェル、Salesforce、ナイキといった著名ブランドが名を連ねる。同社は顧客に対し、今回窃取されたデータを用いた電話・メール・SMS等によるパスワードやMFAコードの詐取を狙った二次フィッシングに警戒するよう呼びかけている。

企業のIT部門を装った電話・チャットによるソーシャルエンジニアリング（ビッシング）は、技術的な脆弱性を突く攻撃よりも検知が難しく、SaaS事業者を経由して多数の顧客企業に間接的な影響が及ぶサプライチェーン性を持つ点でも警戒が必要である。

---

## 関連記事

- [ShinyHunters、セキュリティ企業ReliaQuestへのビッシング攻撃を主張も同社は「被害は限定的」と反論](../articles/2026-08-26-shinyhunters-reliaquest-social-engineering.md) - 同一脅威アクターによる同種のビッシング経由SaaS侵害キャンペーン
