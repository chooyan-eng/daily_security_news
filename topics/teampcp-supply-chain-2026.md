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
- LiteLLM経由の窃取マルウェア: SANDCLOCK Stealer（PyPI版 1.82.7/1.82.8 に混入）
- LiteLLM侵害規模: 153GBの認証情報アーカイブ（433,909ファイル）、118,829件のCI/CDランナーダンプ、2,488法人ドメインに波及（Hudson Rock調べ、2026年8月時点）
- 影響が確認された/推測される組織例: AWS・Cisco・Samsung・Salesforce・Nvidia・ServiceNow・Siemens・FedEx・Volkswagen等（CloudSEK集計、要検証）

## タイムライン

- [2026-08-13 LiteLLM侵害の全容：153GBの認証情報アーカイブが流出、2,500社超に影響か](../articles/2026-08-13-litellm-teampcp-credential-leak-153gb.md)
- [2026-06-22 TeamPCPによるサプライチェーン攻撃：Trivy・Bitwarden CLI・Checkmarxを2ヶ月間侵害](../articles/2026-06-22-teampcp-trivy-bitwarden-checkmarx.md)
