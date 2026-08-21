# Stripe加盟店APIキー流出事案（2026年8月）

## 概要

脅威アクター「Satanic」が、サイバー犯罪フォーラム「pwnforums」上で、Stripe決済プラットフォームを利用する加盟店のAPIキーおよび顧客関連データを公開した事案。Stripe自体の基盤侵害ではなく、個々の加盟店が保有するシークレットAPIキーが窃取され、Stripeの正規APIを通じてデータが取得されたとみられている。

**同一性の判断に役立つ情報：**
- 脅威アクター: Satanic（サイバー犯罪フォーラム「pwnforums」）
- 公開日: 2026年8月18日
- 当初公開範囲: 669加盟店、1,033件のAPIキー
- 主張されている総侵害数: 約2万件のAPIキー（複数プラットフォームにまたがる）
- 推計影響顧客レコード数: 約68万8,363件
- 影響加盟店の国数: 42カ国
- 原因: Stripe基盤自体の侵害ではなく、加盟店側のシークレットAPIキーの流出・悪用
- 流出データ内容: 顧客情報、charges、payment intents、Checkoutセッション、invoices、payouts、balance transactions、disputes、subscriptions、products/prices等

## タイムライン

- [2026-08-19 Stripe加盟店APIキー5万件超が公開コード上に流出 ― 研究チームが大規模調査で判明](../articles/2026-08-19-stripe-50000-keys-leaked-research.md)
- [2026-08-18 脅威アクター「Satanic」、Stripe加盟店API鍵1,000件超を流出 ― 69万件近い顧客レコードが露出](../articles/2026-08-18-stripe-vendor-api-key-leak-satanic.md)
