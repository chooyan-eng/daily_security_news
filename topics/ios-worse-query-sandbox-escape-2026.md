# iOS サンドボックス回避「worse_query」（2026年11月）

## 概要

研究者 forcequit（@forcequitOS）と 0xjohnny が公開したiOSのコンテナサンドボックス回避「worse_query」。App Groupコンテナを持つ悪意あるアプリが他アプリのファイルにアクセスできるとされる。Binanceが2026-11-10に警告（iOS 26.7.1／27.0.1／27.2を影響対象として記載、PoCは26.0〜26.7.2および27.2）。iOS 27.2.1での修正有無は情報が食い違っている。実悪用・資産窃取の報告はなし。CVE番号は未確認。

## タイムライン

- [2026-11-14 iOSのサンドボックス回避「worse_query」が公開、Binanceが暗号資産ウォレット利用者に警告 ― 修正状況は情報が錯綜](../articles/2026-11-14-ios-worse-query-sandbox-escape.md)
