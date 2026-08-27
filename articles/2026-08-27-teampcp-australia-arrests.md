# TeamPCPサプライチェーン攻撃、豪州男性2人が逮捕・起訴 ― Trivy/Checkmarx侵害の首謀者か

- **日付**: 2026-08-27
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/alleged-teampcp-hackers-charged-in.html), [TechCrunch](https://techcrunch.com/2026/08/27/australian-police-arrest-two-over-teampcp-hacks-targeting-mercor-openai-and-others/), [ABC News](https://www.abc.net.au/news/2026-08-27/two-wa-men-charged-after-investigation-into-alleged-cybercrime/107084796)
- **トピック**: [TeamPCPサプライチェーン攻撃（Trivy/Bitwarden/Checkmarx）（2026年）](../topics/teampcp-supply-chain-2026.md)
- **分類**: 続報

## 概要

オーストラリア連邦警察（AFP）は、開発者ツールTrivy・Checkmarx KICS・AIゲートウェイLiteLLM等を連鎖的に侵害した多段階サプライチェーン攻撃「TeamPCP」への関与容疑で、西オーストラリア州の男性2人を合計14件の容疑で起訴した。2人は2026年8月27日にパース治安判事裁判所に出廷した。

## 詳細

TeamPCPは、2026年2月末から4月にかけて実施された多段階サプライチェーン攻撃で、コンテナセキュリティスキャンツールTrivyのGitHubサービスアカウントに対する不完全な認証情報ローテーションを突破口に侵入し、そこで得た認証情報を踏み台にセキュリティ分析ツールCheckmarx、パスワードマネージャーBitwarden CLI、AIゲートウェイLiteLLM、通信SDK Telnyx Python SDK、IaCスキャナーKICSを次々と侵害した。最終的にはCheckmarxの非公開GitHubデータ96GBがLAPSUS$の恐喝ポータルで公開され、OpenAIやVercelなど大手企業への二次被害も確認されている。

今回、オーストラリア連邦警察（AFP）は、この攻撃キャンペーンの実行に関与したとして、西オーストラリア州在住の23歳の男性Louis Michael Gaebler容疑者と21歳の男性Ruben Ian Thomson容疑者を摘発したと発表した。両容疑者はサイバー犯罪関連の容疑で合計14件の罪に問われており、2026年8月27日にパース治安判事裁判所に出廷した。AFPと西オーストラリア州警察（WAPF）は前日にCottesloe、Hamilton Hill、Mandurahの各地で捜索令状を執行し、電子機器をフォレンジック分析のために押収している。警察は、両容疑者がシンジケートの中心的メンバーであり、暗号資産で報酬を受け取っていたとみて捜査を進めている。捜査当局の見積もりでは、本キャンペーンにより50万件超の認証情報が流出し、少なくとも300GBのデータが持ち出され、世界全体の復旧コストは数億ドル規模に上るとされる。

TeamPCPを巡っては、その後の調査でLiteLLM経由の被害が当初想定より遥かに大規模であったことも判明している。侵害されたリポジトリは2,038件、影響を受けた組織は2,500社超、露出したCI/CDパイプラインは43万4,000件超、窃取された認証情報アーカイブは153GB（43万3,909ファイル）に及ぶとされ、AWS・Cisco・Samsung・Salesforce・Nvidiaなど著名企業への影響も指摘されてきた。

今回の摘発は、開発ツールチェーンを狙った大規模サプライチェーン攻撃に対する法執行機関の対応事例として注目される。ソフトウェアサプライチェーンの信頼を悪用した攻撃は被害の把握・全容解明に長期間を要する一方、捜査・訴追には摘発対象の特定や国際的な証拠収集など高いハードルがあるが、本件では発生から半年足らずでの容疑者特定・訴追に至っている。

---

## 関連記事

- [TeamPCPサプライチェーン攻撃の全容判明 ― LiteLLM経由で2,500社超・43.4万件のCI/CDパイプラインに影響](../articles/2026-08-18-litellm-supply-chain-teampcp-followup.md) - 同一攻撃キャンペーンの被害規模判明を報じた記事、今回は容疑者摘発の続報
