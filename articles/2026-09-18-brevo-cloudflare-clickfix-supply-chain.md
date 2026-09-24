# メール配信SaaS「Brevo」でCloudflare APIキー窃取、10万超サイトにClickFix型マルウェアを配信するサプライチェーン攻撃

- **日付**: 2026-09-18
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/brevo-supply-chain-attack-injected-clickfix-scripts-on-customer-sites/), [SecurityWeek](https://www.securityweek.com/brevo-supply-chain-attack-injects-malware-into-100000-websites/), [Sansec](https://sansec.io/research/brevo-supply-chain-attack)
- **トピック**: [メール配信SaaS「Brevo」Cloudflare APIキー窃取サプライチェーン攻撃（2026年9月）](../topics/brevo-cloudflare-clickfix-supply-chain-2026.md)
- **分類**: 新規

## 概要

メールマーケティングSaaS「Brevo」で、アプリケーションのソースコードにハードコードされていた長期有効なCloudflare APIキーが窃取された。攻撃者はこのキーで悪意あるCloudflare Workerを作成し、CDNエッジ上でBrevo本体および顧客サイトに埋め込まれたフォーム・ウィジェット・SDKスクリプトを改ざん。約5時間半にわたり、Brevoの埋め込みスクリプトを利用する10万件超のWebサイトにClickFix型の偽エラー表示とWordPressバックドアが配信された。

## 詳細

報道によれば、攻撃者は2026年8月下旬にBrevoの全権限を持つ長期有効なCloudflare APIキーを不正入手していたが、当初は顧客向けページへの悪意あるコンテンツ注入は確認されていなかった。9月14日16:05〜20:13（UTC）の約5時間半、攻撃者はこのAPIキーを用いて悪意あるCloudflare Workerを作成し、CDNエッジでコンテンツを動的に改ざんする手法を用いた。

改ざんの対象には、brevo.com本体のページに加え、login／account／my／onboardingサブドメイン、sibforms.comのフォームページ、そして顧客が自社サイトに埋め込んで利用するBrevoフォームスクリプト、Brevo Conversationsウィジェット、Brevo SDKローダースクリプトが含まれた。これらのスクリプトを埋め込んでいた10万以上のサイトが影響を受け、訪問者に「人間であることを確認してください」といった偽の検証画面を表示し、クリップボード経由でPowerShellコマンド等を実行させる「ClickFix」型の手口でマルウェア感染を誘導した。セキュリティ企業Sansecの調査では、WordPressサイトへのバックドア設置も確認されている。

原因は、アプリケーションのソースコードに全権限のCloudflare APIキーがハードコードされていたことであり、シークレット管理の不備が侵害の起点となった。Brevoは検知後にAPIキーの無効化と悪意あるWorkerの削除を実施したとされる。SaaS事業者のCDN連携用APIキーが漏えいした場合、当該SaaSの埋め込みスクリプトを利用する無数の第三者サイトが同時に汚染される「サプライチェーン型」の被害拡大パターンを示す事例といえる。
