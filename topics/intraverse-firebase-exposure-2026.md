# Intraverse Firebase 設定不備による情報漏洩（2026年）

## 概要

Web3ギャンブルプラットフォーム「Intraverse」の本番用Firebase Realtime Databaseが認証設定なしで公開されており、約1,690万件のレコードが第三者から読み取り可能な状態になっていた事案。プレイヤーのウォレットアドレスと紐づく勝敗記録や、ゲーム運用ボットのウォレット・APIキー情報などが含まれていた。

**同一性の判断に役立つ情報：**
- 対象サービス: Intraverse（Web3ギャンブル／カジノプラットフォーム）
- 原因: Firebase Realtime Database の認証設定不備（無認証で公開状態）
- 流出件数: 16,898,017件（518MB超）
- 流出データ: カジノ勝敗記録（735,705件超、ウォレットアドレス紐付き）、ユーザー通知レコード（FCMトークン等、1,610万件超）、Soneium/ApeChain上のボット設定・ウォレットアドレス、DRPC APIキー
- 発見経緯: 自動Firebaseスキャンを行う脅威アクターが地下フォーラムで公表

## タイムライン

- [2026-08-18 Web3ギャンブルプラットフォーム Intraverse、Firebase Realtime Database の設定不備で1,690万件のレコードが公開状態に](../articles/2026-08-18-intraverse-firebase-exposure.md)
