# CryptoBandits Windows クリプト・クリッパーキャンペーン（2026年）

## 概要

2026年2月から活動している Windows ベースの暗号通貨クリッパーマルウェアキャンペーン「CryptoBandits」。Microsoft Threat Intelligence が 2026年6月17日に詳細を公開。USB LNK ワームで拡散し、Tor ネットワークで C2 通信を隠蔽する。クリップボードの暗号通貨アドレス置き換えにとどまらず、スクリーンショット窃取や RCE 機能も持つバックドアへと進化している。

**同一性の判断に役立つ情報：**
- キャンペーン名: CryptoBandits
- 発見者: Microsoft Threat Intelligence
- 活動開始: 2026年2月以降
- 主要配布手法: USB ドライブ経由の Windows LNK（ショートカット）ワーム
- マルウェア機能: クリップボードアドレス置換・BIP39 シードフレーズ窃取・スクリーンショット窃取・RCE バックドア
- C2 通信: Tor 隠しサービス（.onion）経由
- 主な標的: 個人暗号通貨ユーザー、開発者

## タイムライン

- [2026-06-20 CryptoBandits：USB経由で拡散するWindowsクリプト・クリッパーマルウェアキャンペーン](../articles/2026-06-20-cryptobandits-windows-crypto-clipper.md)
