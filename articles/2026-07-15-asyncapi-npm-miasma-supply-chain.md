# AsyncAPIのnpmパッケージがCI/CDパイプライン経由で侵害、Miasma系マルウェアを配信

- **日付**: 2026-07-14
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/-asyncapi-npm-packages-infected-with-credential-stealing-malware/), [SecurityAffairs](https://securityaffairs.com/195395/security/asyncapi-npm-supply-chain-attack-malware-injected-into-packages-with-2-million-weekly-downloads.html), [StepSecurity](https://www.stepsecurity.io/blog/compromised-next-branch-pushes-malicious-asyncapi-generator-generator-helpers-and-generator-components-to-npm)
- **トピック**: [Red Hat npmサプライチェーン攻撃（Miasma）](../topics/redhat-npm-supply-chain-miasma.md)
- **分類**: 続報

## 概要

2026年7月14日、AsyncAPIプロジェクトの2つのGitHubリポジトリが侵害され、週間300万ダウンロード超のnpmパッケージ（@asyncapi/generator等）に認証情報窃取マルウェアが混入していたことが判明した。攻撃者はnpmトークンを盗むのではなく、リポジトリの`next`ブランチへのプッシュ権限を奪取し、正規のCI/CDパイプラインを悪用して悪意あるパッケージを公開させた。配信されたマルウェアは6月のRed Hat npm攻撃で確認された「Miasma」系列とされる。

## 詳細

### 攻撃の手口

侵害されたのは@asyncapi/generator@3.3.1、@asyncapi/generator-helpers@1.1.1、@asyncapi/generator-components@0.7.1を含む計4つのパッケージ。2026年7月14日07:10 UTCにnpmへ公開された。特徴的なのは、パッケージがプロジェクト自身の正規GitHub Actionsリリースワークフローを通じて公開されており、有効なnpm OIDC provenance attestationsを保持していた点である。攻撃者はnpm発行用トークンを窃取したのではなく、リポジトリの`next`ブランチへの書き込みアクセスを獲得し、本物のCI/CDパイプラインに公開作業を代行させていた。

### マルウェアの挙動

混入されたドロッパーは難読化されており、インストール時ではなくライブラリが実際に読み込まれたタイミングで発火する設計になっている。この挙動特性から、6月に発覚したRed Hat npmサプライチェーン攻撃「Miasma」で使われたものと同系統のマルウェアと分析されている。

### 対応状況

悪意あるバージョンはすべてnpmレジストリから公開停止（unpublish）された。今回の侵害パッケージ群は合計週間300万ダウンロード超と大規模であり、依存関係にこれらのパッケージを含むプロジェクトは影響範囲の確認とロックファイルの精査が推奨される。

### 関連するJscrambler攻撃

同時期にJscramblerのnpmパッケージも別の攻撃者によって侵害されていたことが判明している。7月11日に開始されたこの攻撃では、盗まれたnpm発行用クレデンシャルを使ってpreinstallフックを仕込んだ改変版パッケージが公開され、非推奨化されるまでに1,479回ダウンロードされた。

### Miasmaキャンペーンとの関連性

既存トピック「Red Hat npmサプライチェーン攻撃（Miasma）」は2026年6月1日に発見された@redhat-cloud-servicesネームスペースへの攻撃を起点とする。今回のAsyncAPI攻撃は対象ネームスペースこそ異なるものの、配信されるマルウェアが同じ「Miasma」系列であることから、npmエコシステムを狙うMiasmaオペレーターの活動が継続・拡大していることを示している。

---

## 関連記事

なし
