# StreamRat Androidバンキング型トロイの木馬・広告配信キャンペーン（2026年）

## 概要

無料動画配信サービスを装ったMeta（Facebook・Instagram）・TikTok広告を通じて拡散するAndroidバンキング型マルウェア「StreamRat」。Accessibility ServiceとMediaProjection APIを悪用し、VNCによる遠隔操作、キーロギング、偽ログイン画面によるクレデンシャル窃取など、感染端末をほぼ完全に制御できる。スペイン語圏ユーザーが主な標的。

**同一性の判断に役立つ情報：**
- マルウェア名: StreamRat
- 拡散経路: Meta（Facebook/Instagram）・TikTok広告、無料ストリーミングアプリを装ったランディングページ
- 主な標的地域: スペイン（スペイン語圏ユーザー）
- 悪用機能: Android Accessibility Service、MediaProjection API
- 攻撃能力: VNC遠隔操作、Hidden Screen、UIツリー収集、キーロギング、オーバーレイによるクレデンシャル窃取
- 観測されたキャンペーン期間: 2026年6月11日〜7月3日（Meta）、同時期にTikTokでも同一バナー使用
- 広告リーチ: 単一Metaキャンペーンで約57万人

## タイムライン

- [2026-09-05 Meta・TikTok広告経由で拡散するAndroidバンキング型トロイの木馬「StreamRat」](../articles/2026-09-05-streamrat-android-trojan-meta-tiktok-ads.md)
- [2026-09-04 Meta・TikTok広告経由で拡散するAndroidトロイの木馬「StreamRat」 Accessibility悪用で端末を完全掌握](../articles/2026-09-04-streamrat-android-trojan-meta-tiktok-ads.md)
