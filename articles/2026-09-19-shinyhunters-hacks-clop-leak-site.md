# ShinyHunters、Clopランサムウェアのダークウェブリークサイトをハッキング

- **日付**: 2026-09-19
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-hacks-clop-leak-site-threatens-to-extort-ransomware-gang/), [DataBreaches.Net](https://databreaches.net/2026/09/19/shinyhunters-hacks-clop-leak-site-threatens-to-extort-ransomware-gang/)
- **トピック**: [ShinyHunters、Clopランサムウェアのリークサイト侵害事案（2026年9月）](../topics/shinyhunters-clop-leak-site-hack-2026.md)
- **分類**: 新規

## 概要

恐喝グループ「ShinyHunters」が、ランサムウェアグループ「Clop」のダークウェブ上のデータリークサイト（Tor隠しサービス）に侵入し、サイトを改ざんした上でサーバーデータやTor隠しサービスの秘密鍵を窃取したと主張している。ShinyHuntersはClopに対し72時間以内の対応を求め、逆に恐喝する構えを見せている。

## 詳細

BleepingComputerなどの報道によれば、攻撃は金曜夜（現地時間）に開始され、ShinyHuntersはClopのリークサイトで利用されているとみられるGrav CMSの未認証ファイルアップロード脆弱性を悪用し、小さなテキストファイルをサイトにアップロードして改ざんに成功したとされる。

改ざんされたページには「THIS SITE HAS BEEN PWN3D BY SHINYHUNTERES #Skids10p - Maybe don't try to threaten us next time.」というメッセージが掲示され、ShinyHunters自身のリークサイトへのリンクが含まれていた。

ShinyHuntersは、Clop側のソースコード、Grav CMSプラグイン、システムログに加え、Tor隠しサービスの秘密鍵を窃取したと主張している。この秘密鍵が有効であれば、ShinyHuntersがClopのサイトになりすますことも理論上可能になる。ShinyHuntersはClopに72時間の猶予を与え、対応がなければさらなる情報公開や恐喝に踏み切ると警告している。

今回の攻撃は、2025年のOracle E-Business Suiteを巡るデータ窃取キャンペーンに関連してClopメンバーがShinyHuntersを脅したとされる過去の対立への報復と位置づけられている。ランサムウェア・恐喝グループ同士の内部抗争が、双方の被害組織の情報管理体制にも影響を及ぼす可能性があり、今後Clop側の漏えいデータの真正性や範囲の検証が注目される。
