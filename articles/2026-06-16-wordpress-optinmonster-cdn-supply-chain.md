# WordPress大手プラグイン（OptinMonster/PushEngage）のCDNサプライチェーン攻撃、120万サイトに影響

- **日付**: 2026-06-16
- **出典**: [Patchstack](https://patchstack.com/articles/supply-chain-attack-on-optinmonster-trustpulse-and-pushengage-tampered-cdn-scripts-auto-creating-rogue-admins/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/optinmonster-wordpress-plugin-hacked-in-cdn-supply-chain-attack/), [Sansec](https://sansec.io/research/optinmonster-supply-chain-attack)
- **トピック**: [WordPress Awesome Motive CDNサプライチェーン攻撃（2026年6月）](../topics/wordpress-awesome-motive-cdn-attack-2026.md)
- **分類**: 新規

## 概要

WordPress向け人気プラグイン「OptinMonster」「TrustPulse」「PushEngage」を開発するAwesome Motiveのサービスが提供するCDNホスト型JavaScriptファイルが改ざんされた。悪意あるコードは管理者がログイン中のサイトにロードされると自動的に不正な管理者アカウントを作成し、秘匿バックドアプラグインをインストールする。1,200万以上のWordPressサイトへの影響が懸念されるが、直接被害を確認できたのは少なくとも100万以上のサイトとされる。

## 詳細

### 攻撃の発端：UpdraftPlusの脆弱性が悪用される

攻撃者はまずAwesome Motiveのマーケティングサイトに侵入するため、WordPressプラグイン「UpdraftPlus」の既知の脆弱性を悪用した。侵入後、サーバー上に保管されていたCDN APIキーを窃取。このキーを使ってOptinMonster・TrustPulse・PushEngageのSDKファイルとして配信されているCDNコンテンツを書き換えた。

### 悪意あるコードの仕組み

セキュリティ企業Sansecが2026年6月13日に検出した改ざんコードは以下のように動作する：

1. 改ざんされたJavaScriptがWordPressサイトに読み込まれる
2. ブラウザが管理者のログインセッション（Cookieなど）を検出する
3. 管理者のセッションを利用して、WordPress REST APIを通じて新規の管理者アカウントを無音で作成する
4. 攻撃者制御下の管理者アカウントが秘匿バックドアプラグインをインストールする
5. バックドアは通常のプラグインリストに表示されないよう隠蔽される

攻撃は完全にクライアントサイドで実行されるため、サーバーのログに残りにくく、管理者が何も気づかない間に乗っ取りが完了する。

### タイムライン

- **2026年6月12日**: 最初の悪意あるコードが配信される（Sansec記録）
- **2026年6月13日**: SansecがCDN改ざんを検出・報告
- **2026年6月13〜14日**: OptinMonster・TrustPulseのCDNリソースから悪意あるコードが除去される
- **2026年6月14日**: 一部のPushEngage CDNノードが引き続き悪意あるペイロードを配信（14日中に除去）

### 影響範囲

- **OptinMonster**: 120万以上のWordPressサイトが利用
- **TrustPulse**: 同じく数百万サイトが利用
- **PushEngage**: WordPressサイト向け人気プッシュ通知プラグイン
- 3製品はすべてAwesome Motiveが開発・保守

### Awesome Motiveの対応

攻撃検出後、Awesome Motiveは以下の対応を実施した：
- 影響を受けるファイルを正常版に差し戻す
- CDNキャッシュを完全パージ
- 侵害されたキーおよび関連する認証情報をローテーション
- マーケティングサイトを新しいインフラに移行

### WordPressサイト管理者へのアクション

侵害された可能性があるサイトは以下を確認すべき：
1. 不審な管理者アカウントの有無を確認・削除
2. 非表示または不明なプラグインの有無を確認
3. 期間中（6月12〜14日）にサイト管理者がログインした場合はパスワードリセットとセッション無効化

### CDNサプライチェーンリスクの教訓

本事案はCDNホスト型スクリプトの完全性検証（Subresource Integrity = SRI属性）の重要性を改めて示した。Awesome Motiveのプラグインは読み込む外部スクリプトにSRI属性を付与していなかったため、CDN側での改ざんを検知できなかった。
