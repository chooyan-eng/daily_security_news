# AIコーディングアシスタントのセッション乗っ取りからShai-Hulud系ワームが社内リポジトリ約100件に拡散（Mandiant報告）

- **日付**: 2026-09-16
- **出典**: [NetManageIT（Mandiant報告の転載）](https://blog.netmanageit.com/attacker-hijacks-ai-coding-assistant-session-spreads-shai-hulud-across-about-100-repositories/), [Thomas Harris（転載）](https://thomasharris6.wordpress.com/2026/09/16/attacker-hijacks-ai-coding-assistant-session-spreads-shai-hulud-across-about-100-repositories/)
- **分類**: 関連

## 概要

Mandiantは、ある未公表のSaaS事業者において、稼働中のAIコーディングアシスタントのセッションが攻撃者に乗っ取られ、攻撃者が汚染したパッケージをアシスタントが推奨・採用させたことを起点に、Shai-Hulud系の自己増殖ワームが社内コードリポジトリ約100件に拡散した事例を報告した。GitHub OAuthトークンや各種シークレット、ソースコードが窃取された。

## 詳細

Mandiantが2026年9月に公表した報告によれば、攻撃者はあるSaaS事業者において稼働中のAIコーディングアシスタントのセッションを乗っ取ることに成功した。攻撃者が事前に汚染していたサードパーティ製ソフトウェアを、アシスタントが開発者に推奨し、その推奨が受け入れられたことが侵害の起点となった。

その後、攻撃者はGitHubのOAuthトークンを窃取し、これを足がかりにShai-Hulud系統（Mini Shai-Hulud派生）の自己増殖型ワームを社内の約100件のコードリポジトリへ拡散させた。ワームはリポジトリ内のシークレット情報や、同社製品のソースコードを窃取した。さらに、攻撃者は同社の公式パッケージ名前空間に汚染済みパッケージを公開し、これを別の従業員が誤って取得したことで二次感染も発生している。

Mandiantの公開情報では、侵入の発生時期や、攻撃者がどのようにして稼働中のAIコーディングアシスタントセッションを乗っ取ったのか具体的な手口までは明らかにされていない。Mandiantは、AI支援開発を行う組織向けの対策として、(1) AIが推奨するサードパーティ依存関係を暗号学的チェックサムや承認済みアローリストと照合すること、(2) 生のAPIキーや長期間有効なOAuthトークン等のシークレットを拡張機能から直接アクセスできない場所に置くこと、(3) 依存関係の取得を組織が管理する内部リポジトリ経由に限定すること、の3点を推奨している。

本件は、2026年8月のkeyv/cacheableパッケージ侵害に端を発する「ChainDrop」ことMini Shai-Hulud系ワームの系譜に連なる事例であり、GitHubメンテナーアカウントの直接侵害という従来型の侵入経路に加え、AIコーディングアシスタントのセッション乗っ取りという新たな侵入経路が実際に悪用されたことを示す点で注目される。

---

## 関連記事

- [npmパッケージ keyv/cacheable が乗っ取り被害 – ワーム化し868超のパッケージに拡散](../articles/2026-08-15-keyv-cacheable-npm-supply-chain.md) - 同じMini Shai-Hulud（ChainDrop）系統のワームによるサプライチェーン侵害
