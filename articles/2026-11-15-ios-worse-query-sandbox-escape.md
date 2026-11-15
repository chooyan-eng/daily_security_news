# iOSのサンドボックス脱出PoC「worse_query」が公開、Binanceがウォレット秘密情報の窃取リスクを警告 Appleは修正を明言せず

- **日付**: 2026-11-15
- **出典**: [The Hacker News](https://thehackernews.com/2026/11/binance-warns-of-ios-sandbox-escape.html)
- **トピック**: [iOS サンドボックス脱出「worse_query」（2026年11月）](../topics/ios-worse-query-sandbox-escape-2026.md)
- **分類**: 新規

## 概要

研究者forcequitらがiOSのサンドボックス脱出PoC「worse_query」をGitHubで公開し、Binanceが11月10日、悪意あるアプリが他アプリのローカルファイル（シードフレーズ、秘密鍵、ログイン情報）を読み取れる恐れがあると警告した。iOS 27.2.1／26.7.3で修正されたかは確認されておらず、実攻撃は未確認。

## 詳細

The Hacker News、Security Affairs、CyberInsider、AppleInsider等の報道によれば、研究者forcequit（0xjohnnyと共同）がiOSのサンドボックス脱出エクスプロイト「worse_query」のPoCコードをGitHubで公開した。これを受けBinanceは11月10日にセキュリティ警告を発出し、端末にインストールされた悪意あるアプリがサンドボックスを越えて他アプリのコンテナ内ファイルを読み取り、暗号資産ウォレットのシードフレーズ、秘密鍵、ログイン情報が窃取され得るとした。

影響バージョンは、BinanceによるとiOS 26.7.1、27.0.1、27.2。研究者側の主張ではより広く、iOS 26.0〜26.7.2および27.2が対象とされる。Appleは11月9日にiOS 27.2.1と26.7.3をリリースしているが、リリースノートにworse_queryやサンドボックス関連の記載はなく、修正されたかは確認されていない（研究者は27.2.1および27.3 beta 1でも未修正と主張していると報じられている）。Appleからのコメントは報じられていない。現時点で実際の攻撃・被害は確認されておらず、Binanceも特定のウォレットアプリが影響を受けたとは述べていない。

Binanceの推奨は、信頼できない配布元のアプリを削除すること、iOSと全アプリを最新に更新すること、侵害が疑われる場合はクリーンな端末で作成した新しいウォレットへ資産を移し、全ログインセッションをリセットすること。なお同時期にiVerifyは、App Storeで配布されていた暗号資産モニタリングアプリ「FomoPeek」がiOSの脆弱性を悪用してサンドボックスを脱出し他アプリのデータへアクセスし得たと報告しており、審査通過済みアプリであっても安全とは限らないことが示されている。

モバイルアプリ開発者向けの補足: サンドボックスは唯一の防御線ではないという前提で、(1) 秘密鍵・シード・リフレッシュトークンなどはアプリコンテナ内のファイル（plist、SQLite、UserDefaults）ではなくKeychainに保存し、可能ならSecure Enclave保護鍵＋ `kSecAttrAccessibleWhenUnlockedThisDeviceOnly` と生体認証のアクセス制御を付ける、(2) コンテナ内に置かざるを得ないデータはKeychain保管の鍵でアプリ層暗号化する、(3) ログ・キャッシュ・WebViewストレージに機微情報を残さない、(4) サーバー側でトークンのデバイスバインディングや異常検知を行う、といった多層防御が有効。今回のPoCが読み取れるのは「ファイル」とされており、Keychain項目が同様に取得できるかは報道からは確認できない。

- 参考: [Security Affairs](https://securityaffairs.com/202788/hacking/ios-sandbox-escape-is-public-and-apple-hasnt-confirmed-a-fix.html) / [CyberInsider](https://cyberinsider.com/binance-ios-worse-query-sandbox-escape-crypto-wallet-secrets/) / [AppleInsider](https://appleinsider.com/articles/26/11/11/unpatched-exploit-allows-malicious-ios-apps-to-steal-data) / [Ostorlab](https://blog.ostorlab.co/worse-query-ios-sandbox-escape.html)

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

