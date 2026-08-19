# npm keyv/cacheable サプライチェーンワーム（2026年8月）

## 概要

2026年8月4日、週間ダウンロード数約1.27億件のnpmパッケージ「keyv」のメンテナーGitHubアカウントが侵害され、資格情報窃取型の自己増殖ワーム（Mini Shai-Hulud亜種）が配布された。preinstallスクリプトでBunランタイムと難読化スティーラーを実行し、npmトークン・GitHub CLIトークン・AWS認証情報・Vaultトークン・Kubernetes設定・暗号資産ウォレットを窃取する。窃取した公開トークンで自己増殖し、9組織・400以上のパッケージ（月間20億インストール超）に拡散した。

**同一性の判断に役立つ情報：**
- 起点パッケージ: keyv@6.0.0（cacheable名前空間にも波及）
- マルウェア系統: Mini Shai-Hulud 亜種（自己増殖npmワーム）
- 侵入経路: メンテナーGitHubアカウント侵害
- 標的: npm/GitHub/AWS/Vault/Kubernetes認証情報、暗号資産ウォレット
- 拡散規模: 9組織・400以上のパッケージ名（2026年8月4日時点）

## タイムライン

- [2026-08-04 npmサプライチェーンワーム、keyv/cacheable経由で数百パッケージに拡散し認証情報を窃取](../articles/2026-08-04-npm-keyv-cacheable-supply-chain-worm.md)
