# 金銭目的の脅威アクター「Toy Ghouls」、HiveMQ／Elementを悪用する新種Windowsバックドアを展開

- **日付**: 2026-09-06
- **出典**: [Securelist](https://securelist.com/toy-ghouls-new-hivemq-and-element-backdoors/121270/), [GBHackers](https://gbhackers.com/hivemq-powers-backdoor/)
- **トピック**: [Toy Ghouls HiveMQ／Element悪用Windowsバックドア（2026年）](../topics/toy-ghouls-windows-backdoors-2026.md)
- **分類**: 新規

## 概要

金銭目的の脅威アクター「Toy Ghouls」（別名Bearlyfy、Laboo.boo、Feral Wolf）が、2026年7月以降、既製の攻撃ツールから自作の独自Windowsバックドアへと手口を移行させたことがカスペルスキーの調査で判明した。MQTTブローカー「HiveMQ」やメッセージングアプリ「Element（Matrix）」の正規サービスをC2（コマンド＆コントロール）通信の隠れ蓑として悪用する点が特徴。

## 詳細

Toy Ghouls（同グループの一部活動はロシア国内の組織を標的とし、2025年から確認されている）は、これまで市販・既製の侵入ツールを主に利用していたが、2026年7月初旬、初めて自作の独自バックドアを実戦投入したことが確認された。今回確認された亜種は「mqtt-bird-agent 0.1.0」および「matrix-bird-agent 0.1.0」と呼ばれ、それぞれMQTTブローカーサービス「HiveMQ」およびオープンソースのMatrixプロトコル対応メッセージングアプリ「Element」を悪用し、C2通信を正規のクラウドサービストラフィックに紛れ込ませることで検知を回避する設計となっている。

技術的には、両バックドアともWinRMベースのツール群と連携し、対話的に実行することも、Windowsサービスとして永続化することも可能で、`cplsupport.exe`や`wtass.exe`といった正規ソフトウェアを装ったファイル名で配置される。HiveMQ版はChaCha20-Poly1305で設定情報を暗号化し、Element版は暗号化した設定データをレジストリの「SealedConfig」という場所に格納するなど、それぞれ異なる隠蔽・永続化手法を採用している。

Toy Ghoulsは同時期に、Windows・ESXi・Linuxの各環境を標的とする新種ランサムウェア「GenieLocker」の運用にも関与しているとされ、2026年3月以降、主にロシア連邦の製造業セクターを標的とした攻撃で使用が確認されている。正規のパブリッククラウドサービス（メッセージングブローカーやチャットサービス）をC2チャネルとして悪用する手口は、従来型のドメイン・IPベースの検知やブロックリストでは捕捉しづらく、企業のネットワーク監視においてアプリケーションレベルでの異常検知の重要性を示す事例である。
