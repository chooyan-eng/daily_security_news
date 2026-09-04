# StreamRat Android型トロイの木馬・Meta/TikTok広告悪用キャンペーン（2026年）

## 概要

無料動画配信アプリを装うMeta（Facebook/Instagram）およびTikTok広告を通じて配布される新種のAndroidバンキング型トロイの木馬「StreamRat」に関するキャンペーン。スペイン語圏ユーザー（主にスペイン）を標的とし、Accessibility ServiceやMediaProjection APIを悪用して端末を遠隔から完全に制御可能にする。

**同一性の判断に役立つ情報：**
- マルウェア名: StreamRat（Android型バンキング/RATトロイの木馬、MaaS＝Malware-as-a-Serviceとして提供）
- 配布経路: Meta広告・TikTok広告（無料動画配信サービスを偽装したバナー広告）
- 標的: スペイン語圏ユーザー（観測された被害者の大半はスペイン）
- 想定潜在被害者数: 約57万人（広告到達数ベース）
- 主要な悪用手口: Accessibility Service・MediaProjection API・HVNC（Hidden VNC）による画面監視・キーロギング・偽オーバーレイでの認証情報窃取・遠隔操作
- 観測期間例: Meta広告キャンペーンの一つは2026年6月11日〜7月3日に実施
- 発見: ThreatFabric、Malwarebytes等が分析・報告

## タイムライン

- [2026-09-04 Meta・TikTok広告経由で拡散するAndroidトロイの木馬「StreamRat」 Accessibility悪用で端末を完全掌握](../articles/2026-09-04-streamrat-android-trojan-meta-tiktok-ads.md)
