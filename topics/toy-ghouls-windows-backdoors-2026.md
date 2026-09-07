# Toy Ghouls HiveMQ／Element悪用Windowsバックドア（2026年）

## 概要

金銭目的の脅威アクター「Toy Ghouls」（別名Bearlyfy、Laboo.boo、Feral Wolf）が2026年7月以降に投入した自作Windowsバックドアに関するトピック。MQTTブローカー「HiveMQ」やMatrixベースのメッセージングアプリ「Element」の正規サービスをC2通信の隠れ蓑として悪用する点が特徴。同グループはランサムウェア「GenieLocker」の運用にも関与。

**同一性の判断に役立つ情報：**
- 脅威アクター名: Toy Ghouls（別名Bearlyfy、Laboo.boo、Feral Wolf）
- 活動開始: 2025年から（主にロシア国内組織を標的）、自作バックドアの初投入は2026年7月
- マルウェア名: mqtt-bird-agent 0.1.0（HiveMQ悪用）、matrix-bird-agent 0.1.0（Element/Matrix悪用）
- 特徴: 正規クラウドサービス（HiveMQ／Element）をC2チャネルとして悪用、WinRMベースツールと連携、Windowsサービスとして永続化
- ファイル名例: cplsupport.exe、wtass.exe
- 暗号化方式: HiveMQ版はChaCha20-Poly1305、Element版はレジストリ「SealedConfig」に暗号化設定を格納
- 関連ランサムウェア: GenieLocker（2026年3月以降、ロシア製造業セクターを標的）
- 報告元: カスペルスキー（Securelist）

## タイムライン

- [2026-09-06 金銭目的の脅威アクター「Toy Ghouls」、HiveMQ／Elementを悪用する新種Windowsバックドアを展開](../articles/2026-09-06-toy-ghouls-windows-backdoors.md)
