# npm Trusted Publishingの検証不備「SlugFest」、1,500超のパッケージが乗っ取りリスクに

- **日付**: 2026-10-13
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/10/13/slugfest-npm-trusted-publishing-flaw/)
- **トピック**: [npm Trusted Publishing「SlugFest」検証不備（1,500超パッケージ、2026年10月）](../topics/npm-slugfest-trusted-publishing-2026.md)
- **分類**: 関連

## 概要

Bloom Securityの研究により、npmのTrusted Publishingが信頼する発行元をリポジトリの可変な名前で検証していたため、放棄されたGitHubリポジトリ名を再取得した攻撃者が1,500超のパッケージの新版を公開できるおそれが判明した。10月2日に修正が適用された。実被害は未確認。

## 詳細

根本原因: npmがTrusted Publishingの発行元をリポジトリの人間可読な『owner/repo』名で検証しており、不変の数値IDを使っていなかった。元の所有者がリポジトリを放棄・改名・削除し、第三者が同名を取得すると、パッケージの公開権限を引き継げる状態だった。

影響: Bloom Securityは1,500超の潜在的な脆弱パッケージ（合計1,000万超のダウンロード）を特定。管理下のテストで既存パッケージの新版公開に成功したが、実環境での悪用は観測していないとする。

修正: 報道によれば10月2日に、未検証のTrusted Publishing設定に48時間の有効期限を設ける対策が導入された。一次情報（npm／GitHubのアドバイザリ）は検索では確認できておらず、修正内容は二次報道に基づく。メンテナーは既存の信頼関係の見直しが望ましい。

関連: AIコーディングエージェントが自動でパッケージを導入する流れの中で、こうした上流の乗っ取りが増幅されうる点も指摘されている。既存のnpmワーム型サプライチェーン攻撃とは手口が異なるが、同じnpmエコシステムの発行権限を狙う点で関連する。

---

## 関連記事

- [npmサプライチェーンワーム、keyv/cacheable経由で数百パッケージに拡散し認証情報を窃取](../articles/2026-08-04-npm-keyv-cacheable-supply-chain-worm.md) - npm発行権限を悪用するサプライチェーン攻撃として関連
- [Mastra AIフレームワーク npm 144パッケージがサプライチェーン攻撃で侵害：週間140万DLに影響](../articles/2026-06-17-mastra-npm-supply-chain-attack.md) - 同じnpmエコシステムの攻撃事例
