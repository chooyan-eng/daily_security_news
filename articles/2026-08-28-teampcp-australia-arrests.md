# TeamPCPサプライチェーン攻撃、豪州で首謀者とされる男2人を逮捕・起訴

- **日付**: 2026-08-28
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/australia-arrests-alleged-teampcp-hackers-behind-supply-chain-attacks/), [TechCrunch](https://techcrunch.com/2026/08/27/australian-police-arrest-two-over-teampcp-hacks-targeting-mercor-openai-and-others/), [The Register](https://www.theregister.com/security/2026/08/28/australian-cops-cuff-alleged-teampcp-masterminds/5293157)
- **トピック**: [TeamPCPサプライチェーン攻撃（Trivy/Bitwarden/Checkmarx）（2026年）](../topics/teampcp-supply-chain-2026.md)
- **分類**: 続報

## 概要

オーストラリア連邦警察は、Trivy・LiteLLM・Checkmarx等を踏み台にした大規模サプライチェーン攻撃「TeamPCP」の首謀者として21歳と23歳の男2人を逮捕・起訴したと発表した。両名は最大20年の禁錮刑に相当する計14件の容疑で訴追されている。

## 詳細

オーストラリア連邦警察（AFP）は西オーストラリア州警察・米FBIと連携した捜査の結果、TeamPCPとして知られる脅威アクターグループの中心人物とされるRuben Ian Thomson（21歳）とLouis Michael Gaebler（23歳）の2人を逮捕したと発表した。両名は、コンピュータ犯罪目的でのデータ保有・提供、重大犯罪を助長するためのデータ改ざんなどに関連する計14件の容疑で起訴されており、容疑1件あたり最大3年から20年の禁錮刑が科される可能性がある。

TeamPCPは2026年2月末から複数月にわたり、コンテナセキュリティスキャンツールTrivyのGitHubサービスアカウントに対する不完全な認証情報ローテーションを突破口として侵入し、そこで得た認証情報を足がかりにAIゲートウェイLiteLLM、パスワードマネージャーBitwarden CLI、セキュリティ分析ツールCheckmarx、通信SDKのTelnyx Python SDK、IaCスキャナーKICSなどを連鎖的に侵害した。捜査当局によれば、この攻撃で配布された悪意あるコードにより、世界で1,000を超える組織が侵害された可能性があり、少なくとも50万件の認証情報が窃取され、300GB以上のデータが外部に持ち出されたと推定されている。高名な被害組織としては、欧州委員会、Mistral AI、OpenAI、GitHubなどが挙げられている。

とりわけ2026年8月にはLiteLLM経由の被害の全容が明らかになり、侵害されたリポジトリが2,038件、影響を受けた組織が2,500社超、暴露されたCI/CDパイプラインが43万4,000件超に達すると報告されるなど、被害規模の大きさが際立っていた。TeamPCPを巡っては、盗んだ認証情報を悪用した二次侵害がOpenAIやVercelなど大手テクノロジー企業にも及んだとされ、サプライチェーン攻撃の連鎖がどこまで広がるかが大きな注目を集めていた。

今回の逮捕・起訴は、半年近くにわたり業界を騒がせてきた大規模サプライチェーン攻撃キャンペーンの実行者特定における大きな進展であり、開発者向けツールチェーンを狙った攻撃に対する法執行機関の摘発事例として今後の捜査・公判の行方が注目される。

---

## 関連記事

- [TeamPCPサプライチェーン攻撃の全容判明 ― LiteLLM経由で2,500社超・43.4万件のCI/CDパイプラインに影響](../articles/2026-08-18-litellm-supply-chain-teampcp-followup.md) - 同一脅威アクターによる攻撃の実行者逮捕
