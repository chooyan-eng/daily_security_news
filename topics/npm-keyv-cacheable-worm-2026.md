# npm keyv/cacheable サプライチェーンワーム（2026年8月）

## 概要

2026年8月4日、週間ダウンロード数約1.27億件のnpmパッケージ「keyv」のメンテナーGitHubアカウントが侵害され、資格情報窃取型の自己増殖ワーム（Mini Shai-Hulud亜種）が配布された。preinstallスクリプトでBunランタイムと難読化スティーラーを実行し、npmトークン・GitHub CLIトークン・AWS認証情報・Vaultトークン・Kubernetes設定・暗号資産ウォレットを窃取する。窃取した公開トークンで自己増殖し、9組織・400以上のパッケージ（月間20億インストール超）に拡散した。

**同一性の判断に役立つ情報：**
- 起点パッケージ: keyv@6.0.0（cacheable名前空間にも波及）
- マルウェア系統: Mini Shai-Hulud 亜種（自己増殖npmワーム）
- 侵入経路: メンテナーGitHubアカウント侵害
- 標的: npm/GitHub/AWS/Vault/Kubernetes認証情報、暗号資産ウォレット
- 拡散規模: 9組織・400以上のパッケージ名（2026年8月4日時点）
- キャンペーン名: ChainDrop（別名 keyv-shai-hulud、Mini Shai-Hulud亜種を使用）
- 起点: npmメンテナーのGitHubアカウント侵害
- 影響パッケージ: keyv、cacheable等 約450種類、悪性バージョン約2,244件
- 手口: npm preinstallフック → Bun難読化ペイロード → 認証情報窃取 → 自己拡散、Ethereumスマートコントラクト経由のC2デッドドロップ
- 関連キャンペーン: Open VSX「Evil Twin」拡張機能77件（2026年7月26日〜8月1日アップロード、8月3日削除）
- 悪用開始: 2026年8月4日UTC10:53頃
- 侵害日: 2026年8月4日
- 侵害対象: npmメンテナー Jared Wray（jaredwray）のGitHubアカウント
- 直接侵害パッケージ: keyv, cacheable-request, cache-manager, @cacheable/utils, flat-cache, file-entry-cache, cacheable, @cacheable/memory, @cacheable/node-cache（計9パッケージ、月間20億+DL）
- マルウェア: preinstallフック経由の難読化ローダー→クレデンシャルスティーラー（npm/GitHub/AWS/HashiCorp Vault認証情報窃取）
- 攻撃者ファミリー帰属（Wiz）: Mini Shai-Hulud（TeamPCP・@antvキャンペーンとの類似性を指摘、同一犯行と断定はせず）
- 影響規模: 約400〜2,200件超のパッケージ・成果物
- 攻撃名: Mini Shai-Hulud（Wiz命名）／ ChainDrop（Microsoft命名、自己拡散メカニズムの分析名）
- 発端: keyv・cacheable メンテナー Jared Wray 氏の GitHub アカウント乗っ取り
- 発生日: 2026-08-04
- 侵害パッケージ数: 最終的に434パッケージ・1,381バージョン
- 影響ダウンロード数: 月間合計20億件超
- マルウェアの特徴: preinstall フック（setup.mjs）、Bun ランタイム悪用、npm公開トークンを使った自己増殖
- 波及した企業: Deliveroo・OneReach・Ornikar・Picsart・ServiceTitan・Qlik 等
- 関連する過去キャンペーン: Red Hat npm サプライチェーン攻撃「Miasma」、TeamPCP、@antv
- 攻撃発生日: 2026年8月4日
- 起点: keyvメンテナーのGitHubアカウント侵害
- ワーム名: CHAINDROP（Shai-Hulud系統、Mini Shai-Huludの後継）
- 影響パッケージ: keyv, cacheable, flat-cache, file-entry-cache, cacheable-request, cache-manager 等（1,300バージョン超）
- 影響規模: 月間合計約20億ダウンロード
- 手口: preinstallフック → Bunランタイムダウンロード → 728KB難読化情報窃取プログラム実行
- マルウェア名: ChainDrop（自己増殖型npmワーム）
- 感染起点: 「keyv」パッケージ（2026年8月4日公開の悪意あるバージョン）
- 拡散手法: preinstallフックでnpm/GitHub/AWS等の認証トークンを窃取 → 連鎖的にパッケージを汚染
- 関連パッケージ: keyv, file-entry-cache, cache-manager, jaredwray/cacheable, jaredwray/ecto 等
- 被害規模: 1,300以上のパッケージ、月間ダウンロード合計20億件超、2,000以上のアーティファクトを追跡（Socket, Microsoft）
- 特徴: インストール実行せずともautostartフック経由で発動する可能性、インシデント対応時に発動する持続化機構
- マルウェア名: Shai-Hulud（ワーム、認証情報窃取＋自己増殖）
- 侵害起点: keyvメンテナのGitHubアカウント侵害
- 影響パッケージ: keyv、cacheable、flat-cache、file-entry-cache等、汚染バージョン1,300超
- 発覚日: 2026年8月4日
- 手口: 悪意あるプリインストールフック（setup.mjs）→Bunランタイム経由の第2段階ペイロード→クラウド/CI認証情報窃取→他パッケージへの再感染
- 規模: 影響パッケージの月間インストール数合計20億件超

## タイムライン

- [2026-08-11 npmサプライチェーン攻撃「Shai-Hulud」ワーム — keyv/cacheable等1,300超のパッケージバージョンが汚染](../articles/2026-08-11-npm-shai-hulud-keyv-cacheable.md)
- [2026-08-10 自己増殖型npmワーム「ChainDrop」が1,300以上のパッケージに感染、月間20億ダウンロード規模に拡大](../articles/2026-08-10-chaindrop-npm-supply-chain.md)
- [2026-08-06 npmの人気キャッシュパッケージ keyv・cacheable がサプライチェーン攻撃で侵害、メンテナーアカウント乗っ取りから拡散](../articles/2026-08-06-npm-keyv-cacheable-mini-shai-hulud-2026.md)
- [2026-08-05 Microsoft、自己拡散型 npm ワーム「ChainDrop」を分析 – 400超パッケージに感染拡大](../articles/2026-08-08-chaindrop-npm-worm-microsoft-analysis.md)
- [2026-08-05 Open VSXで「Evil Twin」型の悪性拡張機能77件を検出・削除、ChainDropキャンペーンの一部と判明](../articles/2026-08-05-openvsx-evil-twin-extensions.md)
- [2026-08-04 npmの人気キャッシュライブラリkeyv/cacheableが乗っ取り被害、自己増殖ワーム「CHAINDROP」が1300超のパッケージに拡散](../articles/2026-08-09-keyv-cacheable-npm-chaindrop-worm.md)
- [2026-08-04 keyv・cacheable 名前空間の npm パッケージが乗っ取り被害 – 月間20億ダウンロード規模の「Mini Shai-Hulud」型サプライチェーン攻撃](../articles/2026-08-08-keyv-cacheable-npm-mini-shai-hulud.md)
- [2026-08-04 npmサプライチェーンワーム、keyv/cacheable経由で数百パッケージに拡散し認証情報を窃取](../articles/2026-08-04-npm-keyv-cacheable-supply-chain-worm.md)
- [2026-08-04 「ChainDrop」自己増殖型npmワーム、keyv・cacheable等450パッケージ・2,200超のバージョンに感染](../articles/2026-08-04-chaindrop-npm-worm.md)
