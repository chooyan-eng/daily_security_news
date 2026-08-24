# ToxicPanda 2.0 Androidバンキングトロジャン（2026年）

## 概要

Zimperium zLabsが確認した、Androidバンキングマルウェア「ToxicPanda」の強化版。VPNサービス権限を悪用してGoogle Play／Play Protectとの通信を遮断する新機能を備え、標的とする金融関連アプリを349種類・16か国に拡大した。ユーザー補助機能悪用によるオーバーレイ型フィッシングやロック画面偽装によるPIN窃取も行う。同時期に報告されたGoldFactory系のオンデバイス詐欺型マルウェア「GoldDigger」とも関連キャンペーンとして言及される。

**同一性の判断に役立つ情報：**
- マルウェアファミリー: ToxicPanda（少なくとも2022年7月から活動）
- 今回のバージョン: 2.0（大幅強化版）
- 発見: Zimperium zLabs
- 新機能: VPNサービス権限悪用によるGoogle Play/Play Protect通信遮断
- 標的規模: 349の金融関連アプリ、16か国
- 追加コマンド数: 167種類の遠隔操作コマンド
- 配布経路: Amazon AWSホスト型ストレージバケット
- 関連マルウェア: GoldDigger（GoldFactory、on-device fraud）

## タイムライン

- [2026-08-23 Androidバンキングマルウェア「ToxicPanda 2.0」、VPN権限を悪用してGoogle Playを遮断](../articles/2026-08-23-toxicpanda-2-android-banking-trojan.md)
