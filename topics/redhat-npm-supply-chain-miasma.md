# Red Hat npmサプライチェーン攻撃（Miasma）

## 概要

2026年6月1日に発見されたnpmサプライチェーン攻撃。@redhat-cloud-servicesネームスペースの32件以上のパッケージにマルウェアが混入された（Wiz Researchが「Miasma」と命名）。侵害されたGitHubアカウントを通じてpreinstallスクリプトや`binding.gyp`を悪用したインストール時自動実行が仕掛けられ、CI/CDパイプラインのクレデンシャル窃取やクラウド環境への侵入が目的と推測。週間約8万ダウンロードのパッケージ群が対象。2026年7月には@asyncapiネームスペースのパッケージ（週間300万ダウンロード超）でも同一のMiasmaローダーが確認され、GitHub Actionsのワークフロー悪用によるPAT窃取という新たな侵入手口を伴って攻撃範囲が拡大している。

**同一性の判断に役立つ情報：**
- 攻撃名: Miasma
- 発見組織: Wiz Research
- 対象: @redhat-cloud-services npmネームスペース（発見時）、@asyncapi npmネームスペース（2026年7月に拡大確認）
- 発見日: 2026-06-01
- 侵害パッケージ数: 32件以上（Red Hat関連）、4件（AsyncAPI、2026年7月）
- マルウェアの特徴: 744モジュールのコマンドフレームワーク、HTTP/Nostr/IPFS/BitTorrent DHT/libp2p GossipSub/Ethereumスマートコントラクトの6系統C2、systemd/crontab/launchd/レジストリへの永続化

## タイムライン

- [2026-07-16 AsyncAPI npmパッケージが改ざん、Miasmaボットネットローダーが多段階C2で拡散](../articles/2026-07-16-asyncapi-npm-miasma-botnet.md)
- [2026-06-16 Shai-Hulud自己拡散型マルウェア、npm/PyPIで320件以上のパッケージを汚染：Miasmaとの関連が明確化](../articles/2026-06-16-shai-hulud-supply-chain-worm-320-packages.md)
- [2026-06-16 Red Hat npmパッケージを標的としたサプライチェーン攻撃「Miasma」、32件のパッケージが侵害](../articles/2026-06-16-redhat-npm-supply-chain-attack-miasma.md)
