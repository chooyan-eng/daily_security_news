# Red Hat npmサプライチェーン攻撃（Miasma）

## 概要

2026年6月1日に発見されたnpmサプライチェーン攻撃。@redhat-cloud-servicesネームスペースの32件以上のパッケージにマルウェアが混入された（Wiz Researchが「Miasma」と命名）。侵害されたGitHubアカウントを通じてpreinstallスクリプトや`binding.gyp`を悪用したインストール時自動実行が仕掛けられ、CI/CDパイプラインのクレデンシャル窃取やクラウド環境への侵入が目的と推測。週間約8万ダウンロードのパッケージ群が対象。

**同一性の判断に役立つ情報：**
- 攻撃名: Miasma
- 発見組織: Wiz Research
- 対象: @redhat-cloud-services npmネームスペース（2026年6月）、AsyncAPI @asyncapi ネームスペース（2026年7月）
- 発見日: 2026-06-01（初回）
- 侵害パッケージ数: 32件以上（Red Hat）、4件・週間300万DL超（AsyncAPI）
- 7月の手口: リポジトリ`next`ブランチへの書き込みアクセスを奪取し、正規CI/CDパイプライン経由でMiasma系マルウェアを配信

## タイムライン

- [2026-07-14 AsyncAPIのnpmパッケージがCI/CDパイプライン経由で侵害、Miasma系マルウェアを配信](../articles/2026-07-15-asyncapi-npm-miasma-supply-chain.md)
- [2026-06-16 Shai-Hulud自己拡散型マルウェア、npm/PyPIで320件以上のパッケージを汚染：Miasmaとの関連が明確化](../articles/2026-06-16-shai-hulud-supply-chain-worm-320-packages.md)
- [2026-06-16 Red Hat npmパッケージを標的としたサプライチェーン攻撃「Miasma」、32件のパッケージが侵害](../articles/2026-06-16-redhat-npm-supply-chain-attack-miasma.md)
