# メール配信SaaS「Brevo」Cloudflare APIキー窃取サプライチェーン攻撃（2026年9月）

## 概要

メールマーケティングSaaS「Brevo」のソースコードにハードコードされていた全権限のCloudflare APIキーが窃取され、攻撃者は悪意あるCloudflare Workerを作成してCDNエッジ上でコンテンツを改ざんした。Brevo本体および顧客サイトに埋め込まれたフォーム・ウィジェット・SDKスクリプトにClickFix型の偽エラー画面とWordPressバックドアが注入され、10万件超のサイトに影響が及んだ。

**同一性の判断に役立つ情報：**
- 被害組織: Brevo（メールマーケティングSaaS、旧Sendinblue）
- 窃取された認証情報: ソースコードにハードコードされた全権限のCloudflare APIキー
- 悪用開始（不正利用開始）: 2026年8月下旬、顧客向けコンテンツへの注入開始: 2026年9月14日16:05〜20:13（UTC）
- 攻撃手法: 悪意あるCloudflare Workerによるエッジでのコンテンツ改ざん、ClickFix型偽検証画面、WordPressバックドア設置
- 影響範囲: brevo.com本体、sibforms.com、顧客サイトに埋め込まれたBrevoフォーム/Conversationsウィジェット/SDKローダー、10万件超のサイト

## タイムライン

- [2026-09-18 メール配信SaaS「Brevo」でCloudflare APIキー窃取、10万超サイトにClickFix型マルウェアを配信するサプライチェーン攻撃](../articles/2026-09-18-brevo-cloudflare-clickfix-supply-chain.md)
