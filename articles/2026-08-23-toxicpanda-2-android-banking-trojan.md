# Androidバンキングマルウェア「ToxicPanda 2.0」、VPN権限を悪用してGoogle Playを遮断

- **日付**: 2026-08-23
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/toxicpanda-android-malware-uses-vpn-permissions-to-block-google-play/) / [Security Affairs](https://securityaffairs.com/197681/breaking-news/toxicpanda-2-0-gets-a-major-upgrade.html) / [The Hacker News](https://thehackernews.com/2026/08/toxicpanda-20-and-golddigger-expand.html)
- **トピック**: [ToxicPanda 2.0 Androidバンキングトロジャン（2026年）](../topics/toxicpanda-2-android-banking-trojan-2026.md)
- **分類**: 新規

## 概要

Zimperium zLabsが、Androidバンキングマルウェア「ToxicPanda」の大幅強化版「2.0」を確認した。標的とする金融関連アプリを349種類・16か国にまで拡大したほか、新たにAndroidのVPNサービス権限を悪用してGoogle PlayおよびPlay Protectとの通信を遮断する機能を追加し、セキュリティ検査や正規の保護動作を妨害する。

## 詳細

### VPN権限を用いたGoogle Play遮断の手口

ToxicPanda 2.0は、正規アプリのインストール画面を装った偽の画面を通じてユーザーからVPNサービスの権限を取得する。取得した権限を用いてデバイス上にローカルのVPNインターフェースを作成し、そこを経由する通信を制御下に置く。この仕組みにより、Google PlayおよびGoogle Play Servicesとの通信を遮断し、アプリの検証・更新・Play Protectとの通信・その他ユーザー保護を目的とした動作を妨害できるようになった。マルウェアはこの権限を使ってGoogle Play Protectの検知を裏でブロックしつつ、実際の悪性コードをアプリのファイル内に隠して密かにインストールする。

### 標的の拡大と新機能

今回の更新でToxicPandaは167種類の遠隔操作コマンドを新たに追加し、対象とする金融機関・暗号資産関連アプリを349種類・16か国にまで拡大した。Androidのユーザー補助機能（Accessibility Services）を悪用して画面要素の読み取り・タッチ操作の自動化・フィッシングオーバーレイの表示を行うほか、Androidのロック画面を偽装してPIN・パターン・パスワードを窃取する機能も備える。マルウェアの配布にはAmazon AWSがホストするストレージバケットが使われており、攻撃者がクラウドインフラを悪用して配布網を構築していることが示されている。

### GoldDiggerとの並行キャンペーン

同時期にThe Hacker Newsは、GoldFactory（中国語話者とされる脅威アクター）系統のオンデバイス詐欺型マルウェア「GoldDigger」もAndroidバンキング攻撃を拡大させていると報じた。GoldDiggerは2023年10月にGroup-IBが最初に報告したマルウェアで、被害者の正規バンキングセッションを遠隔操作するオンデバイス詐欺（on-device fraud）を実行する。ToxicPandaとGoldDiggerはいずれも、従来の認証情報窃取に加えて被害者のデバイス上で直接不正送金を完結させる手口を用いており、多要素認証を回避しやすい点が共通の脅威として指摘されている。

### 活動時期と背景

ToxicPandaは少なくとも2022年7月から活動が確認されているマルウェアファミリーであり、今回の2.0への強化は既存の検知・防御手法を回避するための継続的な進化と位置づけられる。ADB（Android Debug Bridge）を悪用したシェルレベルのアクセス取得も報告されており、感染端末に対する制御の深度が増している。

### リスクと対策

VPN権限の悪用は、通常はセキュリティ強化を目的として許可されることが多いため、ユーザーが警戒しにくい攻撃経路となる。提供元不明のアプリのインストールを避け、インストール時に要求される権限（特にVPNやユーザー補助機能）の妥当性を確認すること、Google Play Protectの動作状況を定期的に確認することが引き続き推奨される。
