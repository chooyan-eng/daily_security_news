# iOSのサンドボックス回避「worse_query」が公開、Binanceが暗号資産ウォレット利用者に警告 ― 修正状況は情報が錯綜

- **日付**: 2026-11-14
- **出典**: [The Hacker News](https://thehackernews.com/2026/11/binance-warns-of-ios-sandbox-escape.html)
- **トピック**: [iOS サンドボックス回避「worse_query」（2026年11月）](../topics/ios-worse-query-sandbox-escape-2026.md)
- **分類**: 新規

## 概要

研究者が公開したiOSのコンテナサンドボックス回避「worse_query」により、悪意あるアプリが他アプリのファイルを読み取れる可能性があるとして、Binanceが11月10日にiPhone利用者へ警告を出した。Appleの修正状況は情報源により食い違っており、実際の悪用や資産窃取は報告されていない。

## 詳細

### 概要

- **名称**: worse_query（CVE番号は報道時点で確認できていない）
- **種別**: 脱獄ではなく、アプリ間のコンテナ分離を破るサンドボックス回避。悪意あるアプリが他アプリのコンテナ内ファイルへアクセスできるとされ、成立条件はApp Groupコンテナを持つことだけと報じられている
- **公開者**: forcequit（@forcequitOS）と 0xjohnny。Appleのアップデート公開前日の日曜日に公開
- **Binanceの警告（2026-11-10）**: iOS 26.7.1、27.0.1、27.2 を影響対象として挙げ、信頼できない入手元のアプリの削除と、iOS・アプリの更新を呼びかけ。Binance固有ではなくiOSレベルの問題と説明
- 公開PoCの対象範囲はBinanceの記載より広く、iOS 26.0〜26.7.2 および 27.2 とされる

### 修正状況（食い違いあり）

- 複数メディアと公開者側は、直後に出たiOS 26／27系のアップデートのリリースノートに修正の記載がなく、iOS 27.2.1 および 27.3 beta 1 でも未修正の「パッチ未提供のゼロデイ」だとしている
- 一方、SlowMistのCISOは「iOS 27.2.1でworse_queryは止まる」と述べたと報じられている
- 現時点の報道ではどちらが正しいか決着していない

### 被害状況

Binanceも研究者も、この脆弱性を使った実攻撃や暗号資産の窃取は報告していない。鍵が抽出された具体的なウォレットアプリも特定されていない。

### アプリ開発者向けの補足

- 本件が示すのは「アプリコンテナ内のファイルは他アプリから読めない」という前提への依存リスクである。シードフレーズ、秘密鍵、セッショントークン、リフレッシュトークンなどを平文ファイル、UserDefaults、SQLite、App Group共有コンテナに置いているアプリは、サンドボックスが破られた時点で全て露出する。
- 秘密情報はKeychain（適切なアクセス制御属性付き）に置き、可能ならSecure Enclave保護鍵でラップする。ファイルに置く場合もData Protectionクラスに頼り切らず、Keychain保管の鍵でアプリ層暗号化を行う。
- App Groupコンテナ（Widget／Extensionとの共有領域）には機微データを置かない、または最小限にする。
- 攻撃には悪意あるアプリの導入が前提となるため、利用者側はApp Store外（サイドロード、TestFlight招待、エンタープライズ証明書配布など）のアプリを避けることが現実的な緩和策となる。

### 参考

- [CyberInsider](https://cyberinsider.com/binance-ios-worse-query-sandbox-escape-crypto-wallet-secrets/)
- [9to5Mac](https://9to5mac.com/2026/11/11/binance-warns-iphone-crypto-holders-of-security-flaw-researchers-say-remains-unpatched)
- [AppleInsider](https://appleinsider.com/articles/26/11/11/unpatched-exploit-allows-malicious-ios-apps-to-steal-data)

> 注: 本セッションでは外部サイトの本文を直接取得できず、検索結果の要約に基づいて作成した。数値・事実関係は出典で再確認のこと。

---

## 関連記事

