# ClickFix型ルアーで新種RAT「ChainScript」を配布、C2探索にPolygonブロックチェーンを悪用

- **日付**: 2026-09-21
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/clickfix-lures-deploy-chainscript-rat.html)
- **トピック**: [新種RAT「ChainScript」Polygonブロックチェーン悪用C2キャンペーン（2026年9月）](../topics/chainscript-rat-clickfix-polygon-2026.md)
- **分類**: 新規

## 概要

Blackpoint Adversary Pursuit Groupが、ClickFix型の偽キャプチャ画面を起点に、これまで報告のなかった新種RAT「ChainScript」を配布するキャンペーンを報告した。ChainScriptはSpotifyやZoom Workplace、Microsoft Teamsなどの正規ソフトウェアに偽装し、C2インフラの所在探索にPolygonブロックチェーン上のスマートコントラクトを利用する「EtherHiding」類似の技術を採用している点が特徴。

## 詳細

Blackpoint Adversary Pursuit Groupの調査によれば、攻撃者はClickFix型の偽キャプチャ／偽エラーページを通じて被害者にコマンドを実行させ、Windowsインストーラー（msiexec.exe経由）をダウンロード・実行させる。確認されたインストーラーの一つ「ComponentTask33-4d14e6ac.msi」はSpotifyに偽装しており、実行されるとNode.jsランタイムを展開したうえで、隠蔽されたPowerShellおよびVBScriptの複数段階を経て、JavaScript製のRATエージェント「ChainScript」を起動する。

ChainScriptはこれまで「ComponentTask33」「UpdateDigital」「HostShared」「OrchidViolet66」といった複数のビルド名で確認されており、Spotifyに加えZoom WorkplaceやMicrosoft Teamsのインストーラーを装う亜種も見つかっている。

技術的に注目されるのは、C2インフラの探索手法として、Polygon（旧Matic）ブロックチェーン上のスマートコントラクトを参照し、稼働中のWebSocket通信先を動的に特定する「EtherHiding」類似の手口を用いている点である。ブロックチェーンの改ざん耐性・検閲耐性を悪用することで、テイクダウンによるC2インフラの無力化を困難にする狙いがあるとみられる。

ChainScript自体はフル機能を備えたRATであり、対話的なCMD／PowerShell実行、ファイル操作、スクリーンショット取得、追加ペイロードの展開、デスクトップアプリおよびブラウザ拡張機能の双方を対象とした暗号資産ウォレットの探索、リモートでのJavaScript実行など、幅広い遠隔操作機能を備えている。

**同一性の判断に役立つ情報：**
- マルウェア名: ChainScript（ビルド名: ComponentTask33／UpdateDigital／HostShared／OrchidViolet66）
- 配布経路: ClickFix型ルアー→msiexec経由のMSIインストーラー（Spotify／Zoom Workplace／Microsoft Teams偽装）
- C2探索技術: Polygonブロックチェーン上のスマートコントラクトを利用した「EtherHiding」類似の手口
- 報告元: Blackpoint Adversary Pursuit Group

---

## 関連記事

- [ClickFix「EtherHiding」BNBスマートチェーン悪用キャンペーン（2026年）](../topics/clickfix-etherhiding-bnb-smartchain-2026.md) - 同じ「EtherHiding」技術（ブロックチェーン上のスマートコントラクトをC2探索に利用）を採用しているが、対象ブロックチェーン（BNBスマートチェーン→Polygon）・配布マルウェア（Lumma Stealer→ChainScript）が異なる別系統のキャンペーン
