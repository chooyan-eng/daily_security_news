# Operation Endgame フェーズ2：StealC・Amadey・SocGholish マルウェアネットワーク解体

- **日付**: 2026-06-24
- **出典**: [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/operation-endgame-stealc-amadey/)
- **トピック**: [Operation Endgame StealC・Amadey 解体（2026年6月）](../topics/operation-endgame-stealc-amadey-2026.md)
- **分類**: 新規

## 概要

欧州刑事警察機構（Europol）主導の大規模マルウェア対策作戦「Operation Endgame」のフェーズ2として、情報窃取マルウェア StealC・Amadey・SocGholish の運用インフラが2026年6月24日に解体された。326台のサーバーと142のドメインが押収され、2400万件超の盗難認証情報が回収、約4100万ユーロの暗号資産が凍結された。

## 詳細

### 作戦の概要

Operation Endgame は2024年に開始したサイバー犯罪インフラ解体作戦の継続フェーズで、今回は特にランサムウェア攻撃・金融詐欺・重要インフラ攻撃の「アセンブリライン」となっているマルウェアファミリーの破壊を目的として実施された。

2026年6月24日に発表された今回の成果：
- **押収**: 326台の刑事サーバー・142ドメイン
- **回収**: 2400万件超の盗難ログイン認証情報
- **凍結**: 約4100万ユーロ（約4650万ドル）の暗号資産
- **標的マルウェア**: StealC・Amadey・SocGholish

### 標的マルウェアの詳細

**StealC**  
Chrome・Firefox・Edge を含むブラウザの保存パスワード、クッキー、クレジットカード情報、暗号資産ウォレットを窃取するインフォスティーラー。2023年に登場し、MaaS（Malware-as-a-Service）形式で提供されている。2026年5月だけで約14万台の感染端末に関与した。

**Amadey**  
2018年から活動するドロッパー兼ボットネット。感染端末にさらなるマルウェア（ランサムウェア・クリプトマイナー・RAT等）を追加でインストールする「ローダー」として機能する。Amadey 経由で配信されたマルウェアはランサムウェア攻撃の初期侵入経路として頻繁に使用される。

**SocGholish**（別名：FakeUpdates）  
正規サイトを改ざんし、ブラウザアップデートに偽装した JavaScript ドロッパーをユーザーに実行させる手口で知られる。Amadey やその他のマルウェアのデリバリーに使用される。

### 法執行・民間連携

**参加機関**：オランダ国家ハイテク犯罪ユニット（THTC）主導のもと、カナダ・デンマーク・ドイツ・英国・米国の各法執行機関が参加。Europol・Eurojust が国際調整を担当。

**民間パートナー**：Microsoft、Proofpoint、IBM X-Force、Infoblox、Bitdefender、The Shadowserver Foundation、Have I Been Pwned、Spamhaus ほか。

### ランサムウェアへの影響

Amadey は Qilin・Interlock・Rhysida・Akira・8Base・Black Basta など主要ランサムウェアグループへのアクセス経路として利用されており、今回の解体がこれらグループの初期アクセス能力に影響を与える可能性がある。ただし、サービス提供者が逮捕されていないケースでは、代替インフラへの移行も懸念される。

### 被害者支援

Europol は盗難認証情報のデータベースを Have I Been Pwned と連携して提供し、自分のアカウントが侵害されたかどうかを確認できる仕組みを整備している。

---

## 関連記事

なし（新規トピック）
