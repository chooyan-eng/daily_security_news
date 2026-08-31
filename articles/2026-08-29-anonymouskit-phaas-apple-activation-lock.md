# 盗難iPhone解除を支援するPhaaS「AnonyMousKIT」、AI音声エージェントで被害者を欺く

- **日付**: 2026-08-29
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/anonymouskit-phaas-uses-voice-ai-agents-to-phish-iphone-passcodes/), [The Hacker News](https://thehackernews.com/2026/08/fake-apple-support-ai-calls-target.html), [Help Net Security](https://www.helpnetsecurity.com/2026/08/26/anonymouskit-phishing-stolen-iphone/)
- **トピック**: [AnonyMousKIT AI音声悪用フィッシング・Apple Activation Lock解除サービス（2026年）](../topics/anonymouskit-phaas-apple-activation-lock-2026.md)
- **分類**: 新規

## 概要

盗難・紛失したApple製端末の「アクティベーションロック」解除に必要な情報を、フィッシングとAI音声エージェントを組み合わせて詐取するPhaaS（フィッシング・アズ・ア・サービス）「AnonyMousKIT」が確認された。506ドメイン・168のストアフロントブランドを展開する大規模なクレジット制サービスとして運営されている。

## 詳細

AnonyMousKITは、盗難・紛失したApple製端末のアクティベーションロックを解除するためのコードを自動的に取得することに特化したフィッシング・アズ・ア・サービスのプラットフォームである。フィッシングメール、SMS、WhatsAppメッセージ、録音音声、そしてAI音声エージェントを組み合わせ、クレジット制で運用される点が特徴だ。

研究者は、このサービスが「Apple Support」を装う高度なAI音声エージェントを利用していることを確認しており、5種類の異なるペルソナで構成された55件の対話トランスクリプトを扱う音声AIエージェントによる200件の通話記録を復元した。その一つである「Alice from Apple Support」というペルソナでは、自動応答エージェントが被害者に対し「Appleが紛失した端末を回収した」と偽って伝え、4桁または6桁の端末パスコードの確認を求める手口が使われていた。

確認された通話は2025年8月から2026年5月の間に行われたもので、1件あたりの通話コストは運営者にとって約0.10ドルと安価であり、通話対象の9割はブラジルの被害者に向けられていた。フィッシングページでは端末パスコード、Apple IDの認証情報、そしてリアルタイムの2要素認証コードが順番に要求され、取得された情報は運営者のパネルとTelegramのWebhookへ転送される仕組みになっている。

盗難端末の転売市場においては、アクティベーションロックの解除が端末の商品価値を左右する最大の要因であり、こうした「盗難端末解除support」を専門とするサービスの登場は、スマートフォン盗難という物理的犯罪とAIを活用したソーシャルエンジニアリングが直結する新たな脅威モデルを示している。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
