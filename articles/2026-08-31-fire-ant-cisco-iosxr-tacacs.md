# 中国系「Fire Ant」、Cisco IOS XRルーターとTACACS認証サーバーをスパイ基盤に転用

- **日付**: 2026-08-31
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/china-linked-fire-ant-hijacks-cisco.html), [BleepingComputer](https://www.bleepingcomputer.com/news/security/chinese-fire-ant-hackers-turn-cisco-routers-into-spying-platforms/), [Security Affairs](https://securityaffairs.com/198183/apt/china-linked-fire-ant-hides-inside-trusted-infrastructure.html)
- **トピック**: [中国系「Fire Ant」Cisco IOS XR／TACACSサーバー侵害キャンペーン（2026年8月）](../topics/fire-ant-cisco-iosxr-tacacs-espionage-2026.md)
- **分類**: 新規

## 概要

中国系サイバースパイ集団「Fire Ant」が、従来のVMwareハイパーバイザー標的から活動範囲を拡大し、Cisco IOS XRルーターおよびTACACS認証サーバーを侵害していることが判明した。ルーターにマルウェアを埋め込みGREトンネルで通信を秘匿し、管理者のコマンド実行結果を改ざんして痕跡を隠蔽するなど、高度な手口が確認された。

## 詳細

セキュリティ企業Sygniaの調査によると、Fire Antは大規模ネットワークのルーティング・認証・管理に使われるCisco IOS XRルーター、TACACSサーバー、Linux管理ホストを標的とした侵害キャンペーンを展開している。発端は、あるCisco IOS XRルーター上で、動作中の設定やコミット履歴では説明のつかないGRE（Generic Routing Encapsulation）トンネルインターフェースが発見されたことだった。

このルーター向けマルウェアは、一般的なLinuxアプライアンス向けではなく、IOS XRの制御プレーン専用に構築されていた。あるコンポーネントは、システムライブラリを改変してログメッセージを監視し、特定の文字列を含むログのみを転送することで検知を回避。別のコンポーネントは、show系コマンドの実行結果に「| exclude」フィルタを自動付加するようコマンド実行経路を改ざんし、管理者から攻撃者の設定したトンネルを隠蔽していた。

TACACSサーバーに対しては、管理者ログインの認証を担うTACACS認証デーモンのプロセスに悪意あるライブラリを直接注入。稼働中のセッションを傍受し、やり取りされる認証情報をひそかに複製していたという。Sygniaは、今回の手口が中国系スパイ集団UNC3886に関する既存の報告と強く重なると評価しているが、断定的な帰属は避けている。仮想化基盤に続き、ネットワーク機器そのものが攻撃対象として狙われている点で、企業のネットワーク管理者にとって深刻な脅威となる。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
