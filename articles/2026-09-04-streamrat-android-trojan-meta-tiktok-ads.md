# Meta・TikTok広告経由で拡散するAndroidトロイの木馬「StreamRat」 Accessibility悪用で端末を完全掌握

- **日付**: 2026-09-04
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/meta-ads-push-streamrat-android-trojan.html), [Malwarebytes](https://www.malwarebytes.com/blog/news/2026/09/streamrat-android-malware-spreads-through-meta-and-tiktok-ads), [ThreatFabric](https://www.threatfabric.com/blogs/from-meta-ads-to-full-device-takeover-uncovering-streamrat)
- **トピック**: [StreamRat Android型トロイの木馬・Meta/TikTok広告悪用キャンペーン（2026年）](../topics/streamrat-android-trojan-2026.md)
- **分類**: 新規

## 概要

無料動画配信アプリを偽装したMeta（Facebook/Instagram）およびTikTokの広告を通じて配布される新種のAndroidトロイの木馬「StreamRat」が確認された。スペイン語圏ユーザーを主な標的とし、Accessibility ServiceやMediaProjection APIを悪用して端末を遠隔から完全に制御できる。想定到達数は約57万人に上る。

## 詳細

StreamRatは、Malware-as-a-Service（MaaS）として提供されるAndroid向けの銀行詐欺・遠隔操作型トロイの木馬（RAT）で、ThreatFabric、Malwarebytesなどのセキュリティ研究機関により分析・報告された。開発者がマルウェア本体と管理基盤（C2インフラ）を提供し、実際の拡散はサービス利用者（アフィリエイト）が担うという分業型の運用モデルを取っている。

配布経路として特徴的なのは、正規の広告プラットフォームであるMetaの広告ネットワーク（Facebook/Instagram）およびTikTokの広告枠が悪用されている点である。無料の動画配信（ストリーミング）サービスを謳うバナー広告がスペイン語圏ユーザー（主にスペイン在住者）に向けて配信され、確認されているキャンペーンの一つは2026年6月11日から7月3日まで実施されていた。広告をクリックしたユーザーはフィッシングサイトへ誘導され、Androidデバイスからのアクセスの場合にのみダウンロードが可能になる仕組みが実装されている。さらに、遷移元がInstagram経由か、Facebook経由か、TikTok経由か、あるいは通常のブラウザ経由かによって、インストール手順の案内内容が変化する作り込みがなされており、いずれの経路でも「提供元不明のアプリ」のインストール許可とAndroidのAccessibility Service（ユーザー補助機能）の有効化へと巧妙に誘導する。

インストール後、StreamRatはAccessibility ServiceとMediaProjection APIを悪用し、画面内容の監視、アプリへの入力内容のキャプチャ（キーロギング）、正規のアプリを模した偽の画面オーバーレイによる認証情報の窃取、UIツリー情報の収集、インターネット接続や画面表示のブロックといった多様な機能を実行する。特に注目される点は、HVNC（Hidden VNC）技術を用いて、被害者に気づかれることなく攻撃者が端末をリアルタイムで遠隔操作できる機能を備えていることで、通常のバンキングトロイの木馬が行う画面オーバーレイによる認証情報窃取にとどまらず、端末そのものへのほぼ完全なアクセス権を攻撃者に与える点で深刻度が高い。

本件は、正規の大手広告プラットフォームの審査をすり抜けて悪意あるアプリへの誘導広告が配信されていたという点、そしてAndroidのAccessibility Serviceという正規のユーザー補助機能が攻撃者に悪用され続けているという、モバイルマルウェアの定番化した攻撃パターンを踏襲している点で、ユーザー側の警戒に加え、広告プラットフォーム事業者側での審査体制強化や、Android OS側でのAccessibility Service許可プロセスの厳格化が引き続き課題となることを示している。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
