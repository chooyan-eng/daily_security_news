# Android新種バンキング型トロイ「StreamRat」、Meta・TikTok広告経由で拡散

- **日付**: 2026-09-06
- **出典**: [Malwarebytes](https://www.malwarebytes.com/blog/news/2026/09/streamrat-android-malware-spreads-through-meta-and-tiktok-ads), [GBHackers](https://gbhackers.com/streamrat-abuses-android/)
- **トピック**: [StreamRat Android広告経由バンキング型トロイ（2026年）](../topics/streamrat-android-banking-trojan-2026.md)
- **分類**: 新規

## 概要

Malwarebytesは、無料動画配信サービスを装ったMeta（Facebook/Instagram）およびTikTok上の広告を通じて拡散する新種Androidマルウェア「StreamRat」を報告した。感染端末を遠隔操作し、銀行アプリの操作乗っ取りや情報窃取が可能で、スペイン語圏のユーザーを主な標的に約57万人が広告に接触したとみられる。

## 詳細

StreamRatは、Android端末のアクセシビリティ機能、MediaProjection API、隠密VNC（HVNC：Hidden VNC）機能を悪用することで、被害者に気づかれることなく端末をほぼ完全に遠隔操作できる点が特徴のバンキング型トロイの木馬兼情報窃取マルウェアである。攻撃者はMetaやTikTokの正規広告プラットフォームに「無料ストリーミングサービス」を装った広告を出稿し、これをきっかけにユーザーを不正アプリのインストールへ誘導する。

確認されたMeta広告キャンペーンの一つは2026年6月11日から7月3日まで展開されており、同一のバナー素材がTikTok上でのマルウェア配布にも流用されていた。観測された被害者の多くはスペインに集中しており、スペイン語話者を標的とした地域特化型のソーシャルエンジニアリングが行われていたとみられる。

インストール後、StreamRatは画面表示内容の監視、アプリ内で入力された文字情報の取得、正規の銀行アプリなどを模した偽の画面（オーバーレイ）を表示して認証情報を窃取する機能に加え、攻撃者が端末をリアルタイムで遠隔操作できる機能を備える。アクセシビリティ機能とMediaProjection、HVNCを組み合わせる手口は近年のAndroidバンキングマルウェアで広く採用されている傾向であり、正規の大手広告プラットフォームが配布経路として悪用されている点は、広告審査をすり抜けるマルウェア配布キャンペーンへの警戒が引き続き必要であることを示している。
