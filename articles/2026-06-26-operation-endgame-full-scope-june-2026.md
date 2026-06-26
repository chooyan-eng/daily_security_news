# Operation Endgame 続報：326台サーバー・142ドメイン押収、€41M 暗号資産凍結の全容判明

- **日付**: 2026-06-26
- **出典**: [Eurojust](https://www.eurojust.europa.eu/news/operation-endgame-continues-international-coalition-takes-malware-offline)
- **トピック**: [Operation Endgame：StealC・Amadey・SocGholish マルウェアインフラ解体（2026年6月）](../topics/operation-endgame-stealc-amadey-2026.md)
- **分類**: 続報

## 概要

Eurojust が 2026年6月25日、Operation Endgame フェーズ2の全容を公表した。2026年6月15〜19日の集中作戦でサーバー326台・ドメイン142件を無力化し、2700万件の盗難済み認証情報セットを回収、約4100万ユーロ（約47百万ドル）相当の暗号資産を凍結した。対象はStealC・Amadey・SocGholish の3マルウェアファミリーで、国際9ヶ国が参加した。

## 詳細

**作戦規模**

- 無力化サーバー数：326台
- 無力化ドメイン数：142件
- 回収した盗難認証情報：2700万件超
- 凍結暗号資産：約4100万ユーロ（約47百万米ドル）
- 参加国：カナダ・デンマーク・ドイツ・ベルギー・フランス・オランダ・英国・米国（9ヶ国）
- 民間協力企業：Microsoft・Proofpoint・IBM X-Force・Infoblox・Bitdefender 他

**標的マルウェアファミリーの概要**

**SocGholish（FakeUpdates）**：偽ブラウザアップデートを経由した初期アクセスブローカーマルウェア。侵害済み Web サイトに注入される偽アップデートスクリプトで、ユーザーが「アップデート」を実行することで感染。

**Amadey**：フィッシングキャンペーン経由で拡散する多機能マルウェア。追加マルウェアの投下・機密データの窃取が可能で、Qilin・Interlock・Rhysida・Akira・8Base・Black Basta などのランサムウェアグループへの初期アクセス提供ルートとして機能していた。

**StealC**：2023年1月以降活動中の Malware-as-a-Service（MaaS）インフォスティーラー。犯罪者が制御パネルへのアクセスを購入し、マルウェアサンプルをビルドして被害者を感染させ、盗難データを回収するビジネスモデルで運営されていた。

**Operation Endgame の位置付け**

本作戦は 2022年から Eurojust が司法当局間の情報共有と行動調整を支援してきた長期プロジェクトの継続。Europol が作戦調整・リアルタイム情報共有・分析・技術支援・帰属調査を担当した。

**ランサムウェアエコシステムへの影響**

Amadey は主要なランサムウェアグループ（Qilin・Interlock・Rhysida・Akira・8Base・Black Basta）への「初期アクセスブローカー」サービスを提供していたため、今回のインフラ解体はこれらランサムウェアキャンペーンへのアクセス経路を大幅に削減した可能性がある。
