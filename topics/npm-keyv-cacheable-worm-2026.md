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

## タイムライン

- [2026-08-06 npmの人気キャッシュパッケージ keyv・cacheable がサプライチェーン攻撃で侵害、メンテナーアカウント乗っ取りから拡散](../articles/2026-08-06-npm-keyv-cacheable-mini-shai-hulud-2026.md)
- [2026-08-05 Open VSXで「Evil Twin」型の悪性拡張機能77件を検出・削除、ChainDropキャンペーンの一部と判明](../articles/2026-08-05-openvsx-evil-twin-extensions.md)
- [2026-08-04 npmサプライチェーンワーム、keyv/cacheable経由で数百パッケージに拡散し認証情報を窃取](../articles/2026-08-04-npm-keyv-cacheable-supply-chain-worm.md)
- [2026-08-04 「ChainDrop」自己増殖型npmワーム、keyv・cacheable等450パッケージ・2,200超のバージョンに感染](../articles/2026-08-04-chaindrop-npm-worm.md)
