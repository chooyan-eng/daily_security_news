# TeamPCPサプライチェーン攻撃（Trivy/Bitwarden/Checkmarx）（2026年）

## 概要

2026年2月末〜4月にかけて「TeamPCP」と呼ばれる脅威アクターが実施した多段階サプライチェーン攻撃。Aqua Securityのコンテナセキュリティスキャンツール Trivy の GitHub サービスアカウントへの不完全なクレデンシャルローテーションを突破口に、Trivy Action（76タグ）を侵害。そこで取得した認証情報を踏み台にセキュリティ分析ツール Checkmarx、パスワードマネージャー Bitwarden CLI、AIゲートウェイ LiteLLM、通信SDK Telnyx Python SDK、IaCスキャナー KICS を連鎖的に侵害した。最終的にCheckmarxの非公開GitHubデータ96GBがLAPSUS$の恐喝ポータルに公開され、OpenAI・Vercel等への二次侵害も確認された。

**同一性の判断に役立つ情報：**
- 脅威アクター名: TeamPCP
- 攻撃期間: 2026年2月末〜4月（約2ヶ月）
- 侵害ツール: Trivy, Trivy Action, Bitwarden CLI (@bitwarden/cli), Checkmarx, LiteLLM, Telnyx Python SDK, KICS
- 侵害手法: 不完全なクレデンシャルローテーション悪用 → フォースプッシュ → 悪意あるnpmパッケージ公開
- 窃取対象: GitHub/npmトークン・SSH鍵・.envファイル・クラウドシークレット・CI/CDシークレット
- 二次被害: OpenAI・Vercel等の大手企業への侵害
- Checkmarx: LAPSUS$ポータルに96GBの非公開データが公開（2026年4月28日）

## タイムライン

- [2026-06-22 TeamPCPによるサプライチェーン攻撃：Trivy・Bitwarden CLI・Checkmarxを2ヶ月間侵害](../articles/2026-06-22-teampcp-trivy-bitwarden-checkmarx.md)
