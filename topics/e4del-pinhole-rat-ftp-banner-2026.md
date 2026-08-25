# E4del／PINHOLE RAT – FTPバナー悪用C2キャンペーン（2026年）

## 概要

FTPサーバーの接続バナー（Welcomeメッセージ）をコマンド＆コントロール（C2）のデッドドロップ・リゾルバーとして悪用し、未確認の2種類のRAT「E4del」と「PINHOLE」を配布する攻撃キャンペーン。2026年7月上旬から観測されている。フィッシング経由のZIPアーカイブ・LNKファイルを起点とし、E4delはDiscordアプリを装うNode.jsベースRAT、PINHOLEはPinterestのピンやSurveyMonkeyのアンケートをC2設定取得元とする多段階型RATである。

**同一性の判断に役立つ情報：**
- マルウェア名: E4del（Discord偽装Node.js製RAT）、PINHOLE（多段階型RAT、14種コマンド対応）
- 手法: FTPバナー文字列をC2コマンドのデッドドロップ・リゾルバーとして悪用
- 観測開始: 2026年7月上旬
- 感染経路: フィッシング→ZIPアーカイブ→LNKファイル実行
- PINHOLEの特徴: C2設定取得元にPinterest・SurveyMonkey等の正規サービスを利用しテイクダウン耐性を確保

## タイムライン

- [2026-08-25 新型RAT「E4del」「PINHOLE」、FTPバナーをC2コマンドのデッドドロップに悪用](../articles/2026-08-25-e4del-pinhole-rat-ftp-banner.md)
