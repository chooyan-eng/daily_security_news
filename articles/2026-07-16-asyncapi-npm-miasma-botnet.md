# AsyncAPI npmパッケージが改ざん、Miasmaボットネットローダーが多段階C2で拡散

- **日付**: 2026-07-16
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/compromised-asyncapi-npm-packages.html), [Wiz.io](https://www.wiz.io/blog/m-red-team-asyncapi-supply-chain-compromise-via-github-actions), [Rescana](https://www.rescana.com/post/active-exploitation-alert-asyncapi-npm-supply-chain-attack-delivers-multi-stage-miasma-botnet-via-compromised-github-act)
- **トピック**: [Red Hat npmサプライチェーン攻撃（Miasma）](../topics/redhat-npm-supply-chain-miasma.md)
- **分類**: 続報

## 概要

npmの@asyncapiネームスペースに属する4パッケージ（週間合計300万ダウンロード超）が改ざんされ、既知の多段階ボットネットローダー「Miasma」が配布されていたことが判明。2026年7月14日、GitHub Actionsのワークフロー設定不備を悪用し高権限PATを窃取したことが侵害の起点。

## 詳細

OX Security・SafeDep・Socket・StepSecurityなど複数のセキュリティ企業が報告したところによると、侵害を受けたのは@asyncapi/generator-helpers@1.1.1、@asyncapi/generator-components@0.7.1、@asyncapi/generator@3.3.1、@asyncapi/specs（v6.11.2およびv6.11.2-alpha.1）の4パッケージ。

攻撃者は2026年7月14日、AsyncAPI generatorリポジトリに対して37件のプルリクエストを送信した。そのほとんどは偽の寄付ページ追加という無害に見える変更だったが、その中に紛れ込ませた1件のPRが、誤設定されたGitHub Actionsワークフローを悪用して高権限のPersonal Access Token（PAT）を窃取するものだった。このトークンを用いてパッケージへの不正な変更が行われた。

汚染されたパッケージには、デコードすると同一の第二段階ダウンローダーに解決される難読化ソースファイルが仕込まれていた。従来型のnpmサプライチェーン攻撃で多用されるインストールフック（`preinstall`スクリプト等）とは異なり、今回のコードはNode.jsによってモジュールが読み込まれたタイミングで実行され、バックグラウンドの子プロセスを起動してIPFS経由でマルウェア本体をダウンロード・実行する。

配布されたマルウェアは744モジュールを内蔵するコマンドフレームワークで、HTTP・Nostrリレー・IPFS・BitTorrent DHT・libp2p GossipSub P2Pメッシュ・Ethereumスマートコントラクトという6系統の独立したC2通信チャネルを備える。認証情報窃取、AIツールの汚染、LAN内の横展開、npm/PyPI/Cargoレジストリへのワーム的自己拡散に加え、systemd・crontab・macOS launchd・Windowsレジストリへの永続化機構も持つ。

このマルウェアはWiz Researchが2026年6月に発見・命名した「Miasma」ボットネットと同一系統であることが確認されており、Red Hat関連npm名前空間を発端としたサプライチェーン攻撃キャンペーンが、7月に入ってもAsyncAPIという異なる主要パッケージ群を標的に継続・拡大していることを示す続報となる。
