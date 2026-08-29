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
- LiteLLM侵害パッケージ: v1.82.7 / v1.82.8（PyPI、2026年3月頃公開）
- LiteLLM経由の被害範囲（2026年8月判明）: 侵害リポジトリ2,038件、影響組織2,500社超、CI/CDパイプライン43.4万件超
- LiteLLM経由の窃取マルウェア: SANDCLOCK Stealer（PyPI版 1.82.7/1.82.8 に混入）
- LiteLLM侵害規模: 153GBの認証情報アーカイブ（433,909ファイル）、118,829件のCI/CDランナーダンプ、2,488法人ドメインに波及（Hudson Rock調べ、2026年8月時点）
- 影響が確認された/推測される組織例: AWS・Cisco・Samsung・Salesforce・Nvidia・ServiceNow・Siemens・FedEx・Volkswagen等（CloudSEK集計、要検証）
- 摘発状況: 2026年8月、豪州連邦警察がRuben Ian Thomson（21歳）・Louis Michael Gaebler（23歳）の2容疑者を逮捕・起訴（計14件の容疑、最大禁錮20年）

- 摘発: 2026年8月27日、豪州連邦警察（AFP）が西オーストラリア州の男性2人（Louis Michael Gaebler、23歳／Ruben Ian Thomson、21歳）を合計14件の容疑で起訴、パース治安判事裁判所に出廷
- 捜査当局の被害見積もり: 認証情報50万件超流出、データ持ち出し300GB以上、世界的な復旧コストは数億ドル規模

## タイムライン

- [2026-08-28 TeamPCPサプライチェーン攻撃、豪州で首謀者とされる男2人を逮捕・起訴](../articles/2026-08-28-teampcp-australia-arrests.md)
- [2026-08-27 TeamPCPサプライチェーン攻撃、豪州男性2人が逮捕・起訴 ― Trivy/Checkmarx侵害の首謀者か](../articles/2026-08-27-teampcp-australia-arrests.md)
- [2026-08-18 TeamPCPサプライチェーン攻撃の全容判明 ― LiteLLM経由で2,500社超・43.4万件のCI/CDパイプラインに影響](../articles/2026-08-18-litellm-supply-chain-teampcp-followup.md)
- [2026-08-15 TeamPCPサプライチェーン攻撃、LiteLLM経由で2,500社・43.4万件のCI/CDパイプラインに影響と判明](../articles/2026-08-15-litellm-teampcp-434k-pipelines-exposed.md)
- [2026-08-13 LiteLLM侵害の全容：153GBの認証情報アーカイブが流出、2,500社超に影響か](../articles/2026-08-13-litellm-teampcp-credential-leak-153gb.md)
- [2026-06-26 Shai-Hulud ワーム：6月の新波で 100件超の npm・PyPI パッケージが再度侵害](../articles/2026-06-26-shai-hulud-teampcp-npm-pypi-june-2026.md)
- [2026-06-22 TeamPCPによるサプライチェーン攻撃：Trivy・Bitwarden CLI・Checkmarxを2ヶ月間侵害](../articles/2026-06-22-teampcp-trivy-bitwarden-checkmarx.md)
