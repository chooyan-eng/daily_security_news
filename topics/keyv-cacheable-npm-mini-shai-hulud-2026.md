# keyv・cacheable npm サプライチェーン攻撃「Mini Shai-Hulud」（2026年8月）

## 概要

2026年8月4日、npm の人気キャッシュライブラリ keyv・cacheable のメンテナー Jared Wray 氏の GitHub アカウントが乗っ取られ、10件のコアパッケージ（月間合計20億ダウンロード超）に自己拡散型の資格情報窃取マルウェアが混入された。preinstall フックが Bun ランタイムをダウンロードし、npm・GitHub・AWS・HashiCorp Vault の認証情報を収集した上で、到達可能な他のパッケージを改変して再公開する自己増殖型ワームで、Microsoft はこれを「ChainDrop」と命名し技術分析を公開。最終的に434パッケージ・1,381バージョン、Deliveroo・OneReach・Ornikar・Picsart・ServiceTitan・Qlik 等の企業リポジトリにまで被害が拡大した。Wiz は本ペイロードを「Mini Shai-Hulud」ファミリーに分類している。

**同一性の判断に役立つ情報：**
- 攻撃名: Mini Shai-Hulud（Wiz命名）／ ChainDrop（Microsoft命名、自己拡散メカニズムの分析名）
- 発端: keyv・cacheable メンテナー Jared Wray 氏の GitHub アカウント乗っ取り
- 発生日: 2026-08-04
- 侵害パッケージ数: 最終的に434パッケージ・1,381バージョン
- 影響ダウンロード数: 月間合計20億件超
- マルウェアの特徴: preinstall フック（setup.mjs）、Bun ランタイム悪用、npm公開トークンを使った自己増殖
- 波及した企業: Deliveroo・OneReach・Ornikar・Picsart・ServiceTitan・Qlik 等
- 関連する過去キャンペーン: Red Hat npm サプライチェーン攻撃「Miasma」、TeamPCP、@antv

## タイムライン

- [2026-08-05 Microsoft、自己拡散型 npm ワーム「ChainDrop」を分析 – 400超パッケージに感染拡大](../articles/2026-08-08-chaindrop-npm-worm-microsoft-analysis.md)
- [2026-08-04 keyv・cacheable 名前空間の npm パッケージが乗っ取り被害 – 月間20億ダウンロード規模の「Mini Shai-Hulud」型サプライチェーン攻撃](../articles/2026-08-08-keyv-cacheable-npm-mini-shai-hulud.md)
