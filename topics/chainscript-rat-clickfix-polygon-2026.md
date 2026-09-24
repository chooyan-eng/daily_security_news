# 新種RAT「ChainScript」Polygonブロックチェーン悪用C2キャンペーン（2026年9月）

## 概要

ClickFix型の偽キャプチャ／偽エラーページを起点に、これまで報告のなかった新種RAT「ChainScript」を配布するキャンペーン。SpotifyやZoom Workplace、Microsoft Teamsなどの正規ソフトウェアに偽装したMSIインストーラーを通じて展開される。最大の特徴は、C2インフラの所在探索にPolygonブロックチェーン上のスマートコントラクトを利用する「EtherHiding」類似の技術を用いている点。

**同一性の判断に役立つ情報：**
- マルウェア名: ChainScript（ビルド名: ComponentTask33／UpdateDigital／HostShared／OrchidViolet66）
- 配布経路: ClickFix型ルアー→msiexec経由のMSIインストーラー（Spotify／Zoom Workplace／Microsoft Teams偽装）
- C2探索技術: Polygonブロックチェーン上のスマートコントラクトを利用した「EtherHiding」類似の手口
- 報告元: Blackpoint Adversary Pursuit Group
- 既存の「EtherHiding」系キャンペーン（BNBスマートチェーン悪用、Lumma Stealer配布）とは対象ブロックチェーン・配布マルウェアが異なる別系統

## タイムライン

- [2026-09-21 ClickFix型ルアーで新種RAT「ChainScript」を配布、C2探索にPolygonブロックチェーンを悪用](../articles/2026-09-21-chainscript-rat-clickfix-polygon.md)
