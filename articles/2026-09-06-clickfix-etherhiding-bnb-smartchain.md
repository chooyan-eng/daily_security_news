# 侵害サイト5,400件超がBNBスマートチェーン悪用のClickFixマルウェアを配信

- **日付**: 2026-09-06
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/over-5-400-hacked-sites-serve-clickfix-payloads-stored-on-the-blockchain/), [crypto.news](https://crypto.news/microsoft-flags-clickfix-malware-using-bnb-chain-to-fetch-attack-instructions/)
- **トピック**: [ClickFix「EtherHiding」BNBスマートチェーン悪用キャンペーン（2026年）](../topics/clickfix-etherhiding-bnb-smartchain-2026.md)
- **分類**: 新規

## 概要

Microsoftなどの調査により、WordPressやPrestaShop等で構築された中小企業サイト5,400件以上が侵害され、偽のCAPTCHA画面（ClickFix手口）を通じて情報窃取型マルウェアを配信していることが判明した。攻撃者はBNBスマートチェーン上のスマートコントラクトに次段ペイロードの取得先情報を格納する「EtherHiding」という手法を用いており、従来型のテイクダウンやシンクホールでは対処が困難とされる。

## 詳細

本キャンペーンは、侵害されたWebサイトに偽のCloudflare風CAPTCHA認証画面を表示し、訪問者に対しWindowsの「ファイル名を指定して実行」ダイアログを開かせ、クリップボードの内容を貼り付けて実行するよう誘導する典型的なClickFix（ClearFakeとも関連）の手口を踏襲する。訪問者がこの手順に従うと、攻撃者が用意したコマンドが実行され、最終的に情報窃取マルウェア「Lumma Stealer」などが感染端末に展開される。

技術的に注目されるのは、各侵害サイトに埋め込まれたBase64エンコードのJavaScriptが、BNBスマートチェーン（BSC）のRPCゲートウェイに問い合わせを行い、スマートコントラクトに格納された攻撃指示・次段ペイロード情報を取得する「EtherHiding」という手法である。ブロックチェーン上のコントラクトはデプロイしたウォレットの秘密鍵を持つ者しか内容を書き換えられないため、セキュリティ企業による従来型のテイクダウンや不正サーバーの停止措置が効かず、悪性インフラの排除が極めて困難になっている。

Microsoft Threat Intelligenceは、この手法がClearFakeキャンペーンと関連する侵害サイト群で使われていることを確認しており、EtherHiding自体は過去にも別のマルウェア配布に利用された前例がある技術だが、今回はClickFix型の偽CAPTCHA攻撃と組み合わせることで大規模化した点が特徴である。Lumma Stealerはブラウザに保存されたパスワード、暗号資産ウォレットの認証情報、セッションクッキーなど機微情報を窃取する能力を持つ。Webサイト運営者にはCMSおよびプラグインの最新化、管理画面への多要素認証導入が、一般利用者には検索結果やサイト上で表示される「認証」を求めるコマンド実行指示に一切従わないことが推奨される。
