# Magento/Adobe Commerceに未認証RCEゼロデイ「StyleSmuggler」、パッチ未提供のまま実悪用が拡大

- **日付**: 2026-09-07
- **出典**: [Sansec](https://sansec.io/research/stylesmuggler-0day), [BleepingComputer](https://www.bleepingcomputer.com/news/security/magento-stylesmuggler-zero-day-exploited-to-deploy-linux-backdoor/), [The Hacker News](https://thehackernews.com/2026/09/unpatched-magento-and-adobe-commerce.html), [SecurityWeek](https://www.securityweek.com/adobe-commerce-zero-day-exploited-to-backdoor-online-stores/amp/)
- **トピック**: [Magento/Adobe Commerce ゼロデイ「StyleSmuggler」未認証RCE（2026年9月）](../topics/adobe-commerce-magento-stylesmuggler-2026.md)
- **分類**: 新規

## 概要

ECプラットフォームMagento／Adobe Commerceの全バージョンに影響する未認証RCEゼロデイ「StyleSmuggler」が実際の攻撃で悪用されていることが判明した。セキュリティ企業Sansecが2026年9月5日に脆弱性を開示したが、Adobeは9月7日時点でCVE番号・パッチ・回避策のいずれも公開していない。

## 詳細

Sansecの調査によれば、StyleSmuggler攻撃は2段階で構成される。まず攻撃者は決済失敗時の障害レポート生成機能を悪用し、Magentoのテンプレートシステムが参照する「styles」プロパティにPHPコードを注入する。次に、故意に決済を失敗させることでMagentoが送信する決済失敗通知メールの処理過程で、注入済みのPHPコードが実行される。この手法は認証を一切必要とせず、標準的な入力検証やWAFのシグネチャをすり抜けやすいという。

Sansecは、最新版であるMagento Open Source 2.4.9を含む2.4.7・2.4.8のクリーンインストール環境で、この未認証攻撃チェーンの再現に成功したと報告している。Adobe Commerce（旧Magento Commerce）の全バージョンも同様に影響を受けるとみられる。攻撃が成功すると、サーバー上で任意のコードが実行され、Rust言語で開発された永続的なバックドアバイナリが設置される。このバックドアは外部のコマンド＆コントロール（C2）サーバーと通信し、攻撃者からの追加指令を待ち受ける仕組みになっている。

実際の攻撃は脆弱性の開示前日にあたる2026年9月4日には既に始まっていたとされ、開示後さらに悪用が広がっている。影響を受けるオンラインストアの規模について、一部報道では11万を超えるMagento/Adobe Commerce導入サイトが潜在的にリスクにさらされていると指摘されている。

最大の懸念点は、9月7日時点でAdobeから正式なセキュリティアドバイザリ、CVE番号の割り当て、修正パッチ、暫定的な緩和策のいずれも提供されていないことである。これにより、サイト運営者は自らの判断で防御策を講じる必要がある。Sansecは、決済関連のメールテンプレート処理やstylesプロパティを経由した異常なコード注入がないか監査すること、WAFルールでの一時的な緩和、疑わしいCronジョブやファイル改ざんの監視強化を推奨している。ECサイトの改ざんはクレジットカード情報を狙うWeb skimming攻撃（Magecartなど）にも直結しやすく、パッチが提供されるまでの間、影響範囲は拡大し続ける可能性が高い。
