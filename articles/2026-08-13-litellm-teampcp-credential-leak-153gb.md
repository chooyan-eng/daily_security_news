# LiteLLM侵害の全容：153GBの認証情報アーカイブが流出、2,500社超に影響か

- **日付**: 2026-08-13
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/08/13/litellm-breach-stolen-credentials-leak/), [Cybernews](https://cybernews.com/security/litellm-supply-chain-attack-credentials-leak/), [SecurityWeek](https://www.securityweek.com/over-2500-organizations-impacted-by-litellm-supply-chain-attack/)
- **トピック**: [TeamPCPサプライチェーン攻撃（Trivy/Bitwarden/Checkmarx）（2026年）](../topics/teampcp-supply-chain-2026.md)
- **分類**: 続報

## 概要

2026年3月に発生したオープンソースAIゲートウェイ LiteLLM への PyPI サプライチェーン攻撃について、脅威インテリジェンス企業 Hudson Rock が窃取データの全容を分析。153GBの認証情報アーカイブ（433,909ファイル）が確認され、AWS・Cisco・Samsung・Salesforce等2,500社超のドメインに影響が波及した可能性があると報告された。同攻撃は「TeamPCP」による多段階サプライチェーン攻撃の一部と見られる。

## 詳細

### 経緯

2026年3月24日、攻撃者はLiteLLMのCI/CDパイプラインを侵害し、悪意あるバージョン（1.82.7・1.82.8）をPyPIに約40分間公開した。LiteLLMのCI/CDパイプラインはコンテナスキャンツール Trivy を検証済みバージョンに固定せずインストールしており、TeamPCPが以前に侵害していた Trivy Action を通じてパイプラインのPyPI公開トークンが窃取された。これにより攻撃者はLiteLLMパッケージに直接マルウェアを混入できた。

### マルウェアの挙動

混入されたマルウェアは「SANDCLOCK Stealer」と呼ばれ、SSH鍵、AWS・Google Cloud・Azureの認証情報、Kubernetesトークン、CI/CDシークレット、AIプロバイダーAPIキーなど機密情報を広範囲に窃取した。インストール時にパイプライン環境内で自動実行され、被害範囲は個々の開発者端末に留まらずCI/CDランナー全体に及んだ。

### 流出データの規模

Hudson Rockが分析した153GBのアーカイブには433,909ファイルが含まれ、うち118,829件がCI/CDランナーのダンプで、2,488の法人ドメインに紐づくと報告されている。CloudSEKは同攻撃を「史上最大級のサプライチェーン攻撃」と評価し、影響を受けた可能性がある組織としてNvidia、AWS、Samsung、Salesforce、Cisco、ServiceNow、Accenture Federal Services、Siemens、Regeneron Pharmaceuticals、London Stock Exchange Group、FedEx、Volkswagen、Orange、HP、Deutsche Bahn、NGINX、Zsealerなどの名前を挙げている。

ただし、報道各社は「2,500社・434,000パイプライン」という数字はあくまで再構築された潜在的露出範囲を示すものであり、これらの組織すべてが実際に侵害された、あるいは認証情報が悪用されたことの証明ではないと注意を促している。

### TeamPCPキャンペーンとの関係

今回のLiteLLM侵害は、Trivy・Trivy Action・Bitwarden CLI・Checkmarx・Telnyx Python SDK・KICSを2026年2月末から4月にかけて連鎖的に侵害した「TeamPCP」による多段階サプライチェーン攻撃の一環である。TeamPCPはTrivyの不完全なクレデンシャルローテーションを突破口とし、そこで得たアクセス権を用いて複数のツール・パッケージへ侵害を拡大していた。今回の分析により、LiteLLMを経由した被害の全体像がより明確になった。

### 対応・推奨事項

LiteLLMを利用している組織は、対象バージョンをインストールしていた期間にCI/CD環境で使用していたAPIキー・トークン・SSH鍵をすべてローテーションすることが強く推奨される。パッチ済みバージョン（1.83.14-stable以降）へのアップデートに加え、CI/CDパイプライン内のツールインストールをハッシュ・バージョン固定で検証する運用の見直しが求められている。

---

## 関連記事

なし（既存トピックの続報）
