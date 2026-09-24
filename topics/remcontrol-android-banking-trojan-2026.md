# RemControl Androidバンキング型トロイ（AI構築C2基盤、2026年）

## 概要

Group-IBが2026年9月23日に報告した、欧州・中東・カナダの銀行を標的とする新種Androidバンキング型トロイ。IPTVアプリ「TVTap」を偽装した偽Google Playページ経由で配布されるMaaS（Malware-as-a-Service）基盤で、C2パネルやフィッシングページの構築・運用に生成AIが利用された痕跡（AIアシスタントの応答文がそのまま埋め込まれる等）が確認されている点が特徴。ボットネットタグ「UNKK」は既知マルウェア「Medusa」の「UNKN」と類似し、開発者間の関連が疑われる。

**同一性の判断に役立つ情報：**
- マルウェア名: RemControl（Androidバンキング型トロイ、MaaS形態）
- 配布手口: 偽IPTVアプリ「TVTap」偽装のGoogle Play風ページ、マルバタイジング
- 標的地域: 主にイタリア・フランス（欧州・中東・カナダの銀行）
- 特徴: C2/フィッシング基盤構築に生成AIを利用した痕跡
- ボットネットタグ: UNKK（類似マルウェアMedusaのUNKNと1文字違い）
- 初観測: サンプル2026年7月、インフラ稼働2026年5月頃
- 報告元: Group-IB（2026年9月23日）
- 追加機能: 画面リアルタイムストリーミング、キーロガー、画面ロックPIN/パターン再構成用情報収集、アンインストール妨害（設定画面から強制排除）
- 侵入時の回避策: インストール時にVPNサービス起動許可を要求しGoogle Playのネットワーク通信を遮断、Play Protectのスキャンを無効化した上でアクセシビリティ権限を要求

## タイムライン

- [2026-09-24 RemControl詳細判明、30行以上の銀行を標的にAI生成フィッシングオーバーレイでPIN窃取](../articles/2026-09-24-remcontrol-android-banking-trojan-details.md)
- [2026-09-23 AIが構築したC2基盤で稼働する新種Androidバンキング型トロイ「RemControl」を確認](../articles/2026-09-23-remcontrol-android-banking-trojan.md)
