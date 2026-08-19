# BdThemes WordPress サプライチェーン攻撃 — 汚染JSONフィードで不正管理者アカウントを自動作成

- **日付**: 2026-08-11
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/bdthemes-supply-chain-attack-poisons.html)
- **トピック**: [BdThemes WordPress サプライチェーン攻撃（2026年8月）](../topics/bdthemes-wordpress-supply-chain-2026.md)
- **分類**: 新規

## 概要

WordPress向け人気プラグインベンダー BdThemes の上流インフラが侵害され、管理画面へ配信されるJSONフィードが改ざんされた。プラグインのコード自体は変更せず、管理者のブラウザセッションを悪用して不正管理者アカウントとWebシェルを自動作成する手口が確認された。Wordfenceが2026年8月7日に攻撃を検知した。

## 詳細

### 攻撃手法

攻撃者はBdThemesのプラグインファイルを直接改変するのではなく、同社の上流インフラを侵害し、管理者ダッシュボードに宣伝バナーを表示するために使われるリモートJSONフィード（Biggopライブラリの Biggopti コンポーネントが取得）を改ざんした。このJSON応答解析コードには2026年3月に混入したコーディング上の欠陥があり、クロスサイトスクリプティング（XSS）が可能な状態になっていた。

改ざんされたJSONフィードに埋め込まれた悪意あるJavaScriptは、ログイン中の正規管理者の認証済みセッションを悪用して不正な管理者アカウントを作成する。さらに追加のペイロード（w2.js）が偽装プラグインをインストールし、Webシェル（emer-run.php）による永続化を確立する。

### 影響範囲

BdThemesはElement Pack、Prime Slider、Ultimate Post Kit、Pixel Gallery、Ultimate Store Kitなどのプレミアムプラグインを提供しており、無料版の主力プラグインElement Packだけでも10万件以上のアクティブインストールがある。影響を受けたプラグインはWordPress.orgのリポジトリから調査目的で一時削除された。

### 関連するサプライチェーン攻撃

本攻撃で使用されたC2サーバーは、Advanced Responsive Video Embedder（CVE-2026-18072）やOptinMonsterを標的とした過去のソフトウェアサプライチェーン攻撃との関連が指摘されている。

## 関連記事

なし（新規トピック）
