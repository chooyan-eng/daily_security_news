# Meta・TikTok広告経由で拡散するAndroidバンキング型トロイの木馬「StreamRat」

- **日付**: 2026-09-05
- **出典**: [Malwarebytes](https://www.malwarebytes.com/blog/news/2026/09/streamrat-android-malware-spreads-through-meta-and-tiktok-ads)
- **トピック**: [StreamRat Androidバンキング型トロイの木馬・広告配信キャンペーン（2026年）](../topics/streamrat-android-trojan-2026.md)
- **分類**: 新規

## 概要

無料動画配信サービスを装ったMeta（Facebook・Instagram）・TikTok広告を通じて拡散するAndroidマルウェア「StreamRat」が確認された。スペイン語圏ユーザーを主な標的とし、あるMetaキャンペーンだけで約57万人に広告が表示された。Accessibility ServiceとMediaProjectionを悪用し、感染端末をほぼ完全に遠隔操作できる。

## 詳細

StreamRatの拡散は、無料ストリーミングサービスを謳う広告からユーザーを誘導するランディングページから始まる。当該サイトはアクセスしてきた端末がAndroidかどうかを判定し、Android以外からのアクセスにはダウンロードをさせず、Android端末に対してのみアプリのダウンロードを提示する仕組みになっている。観測されたMetaでの広告キャンペーンは2026年6月11日から7月3日まで実施され、同様のバナーがTikTokでも使用されていた。

インストールされたStreamRatは、AndroidのAccessibility ServiceとMediaProjection APIを悪用し、VNCによる遠隔操作とHidden Screen（画面を隠した状態での操作）、UIツリー情報の収集、キーロギング、正規アプリを装った偽のログイン画面によるクレデンシャル窃取、インターネット接続や画面表示のブロックなど、感染端末に対するほぼ完全な制御を攻撃者に与える機能を備えている。

被害者の多くはスペインに所在するとみられ、判明しているのは広告の表示回数（リーチ）であり、実際のダウンロード数や感染台数までは明らかになっていない。もっとも、有料広告を用いることで短期間に極めて多数のユーザーへマルウェアへの接触機会を作り出せる点が、本キャンペーンの脅威度を高めている。ユーザーは、正規のアプリストア以外からのAPKダウンロードを避け、広告経由で提示されるアプリのインストールには特に注意する必要がある。
