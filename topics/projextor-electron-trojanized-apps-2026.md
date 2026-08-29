# Projextor トロイの木馬化Electronアプリキャンペーン（2026年）

## 概要

G DATAが確認した、Electronフレームワークを悪用しドキュメント変換・献立プランナーなどの偽装生産性アプリに悪性コードを隠すマルウェアクラスター「Projextor」。`contextIsolation: false`を明示的に設定し、レンダラーとNode.js環境の境界を無効化することで、任意のJavaScript実行やデスクトップキャプチャなどの監視機能を仕込む。

**同一性の判断に役立つ情報：**
- クラスター名: Projextor
- 悪用技術: Electronフレームワーク（`contextIsolation: false`の意図的設定）
- 偽装アプリ例: Kitchen Canvas、Food Formula、DocConvertWizard、PDF Grip 等
- 配布手法: 偽の配布サイト・フリーソフト風インストーラー
- 発見元: G DATA
- 公表時期: 2026年8月下旬

## タイムライン

- [2026-08-29 偽装生産性アプリ「Projextor」、Electronフレームワークを悪用しマルウェアを隠蔽](../articles/2026-08-29-projextor-electron-trojanized-apps.md)
