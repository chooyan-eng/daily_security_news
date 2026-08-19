# ShinyHunters、Brinks Home・RingCentral・EYをリークサイトに追加 — SaaSサプライチェーン侵害が続く

- **日付**: 2026-07-28
- **出典**: [BreachNews](https://breachnews.com/breaches/shinyhunters-adds-ey-ringcentral-and-brinks-home-to-data-leak-site/), [cybersecuritynews.com](https://cybersecuritynews.com/ey-data-breach-claim-shinyhunters/), [gbhackers.com](https://gbhackers.com/shinyhunters-claims-ey-data-breach/)
- **分類**: 関連

## 概要

脅威アクター集団「ShinyHunters」が、スマートホームセキュリティ企業Brinks Home、クラウド通信サービスRingCentral、会計・コンサルティング大手EYの3社を新たにデータリークサイトに掲載した。同グループはサードパーティのサポート・エコシステムを経由して認証情報を取得したと主張しており、盗んだデータの公開を予告する「最終警告」を出している。

## 詳細

ShinyHuntersは2026年7月28日までに、Brinks Home（米テキサス州のスマートホームセキュリティ企業）、RingCentral、EY（アーンスト・アンド・ヤング）の3社をデータ漏洩リークサイトへ相次いで追加した。同グループはEYのデータ侵害を主張し、盗んだとされる顧客の税務データを含む情報を公開すると脅迫している。Brinks Homeについては「最終警告」表示とともに交渉期限を設定し、交渉が成立しなければデータを公開すると通告した。記事執筆時点でBrinks Homeは公式な声明を出していない。

ShinyHuntersは、これらの侵害についてサードパーティのサポート・エコシステム（外部ベンダーやカスタマーサポート委託先など）の侵害を通じて認証情報を取得したと主張している。具体的な侵入経路の技術詳細は現時点で十分に明らかにされていないが、同グループは2025年8月以降、SalesloftやDrift、Gainsightなど複数のSaaS連携基盤を狙ったOAuthトークン窃取キャンペーンを継続的に展開しており、今回の一連の被害もその延長線上にある可能性が高い。

ShinyHuntersはこれまでにもOracle PeopleSoftのゼロデイ脆弱性（CVE-2026-35273）を悪用した大学等100社以上への侵入キャンペーンなど、多様な手口でグローバル企業・組織を標的にしてきた実績を持つ。今回のBrinks Home・RingCentral・EYの事案は攻撃ベクトルが異なるとみられるものの、同一の脅威アクターによる継続的な攻勢の一環として注視が必要である。

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 同一脅威アクター（ShinyHunters）による、別ベクトルのSaaS/エンタープライズ侵害キャンペーン
