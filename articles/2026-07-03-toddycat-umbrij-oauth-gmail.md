# 中国系APT「ToddyCat」、新型マルウェア「Umbrij」でOAuthトークンを窃取しGmailにアクセス

- **日付**: 2026-07-03
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/toddycat-linked-umbrij-malware-abuses.html), [Kaspersky Securelist](https://securelist.com/toddycat-apt-umbrij-tool-and-oauth/120251/)
- **トピック**: [ToddyCat APT「Umbrij」マルウェア・OAuthトークン窃取キャンペーン（2026年）](../topics/toddycat-umbrij-oauth-malware-2026.md)
- **分類**: 新規

## 概要

2020年頃から欧州・アジアの組織を標的に活動するAPTグループ「ToddyCat」が、新型マルウェア「Umbrij」を用いて被害者のGmail・企業メールへのOAuthトークンを窃取するキャンペーンを展開していることが判明。Chromiumブラウザのリモートデバッグポートに接続してアクティブなセッションからOAuthアクセストークンを生成する手法「Shadow Token via Remote Debug（STRD）」が用いられている。

## 詳細

### ToddyCatについて

ToddyCatは2020年頃から活動が確認されている高度標的型攻撃グループで、主に欧州およびアジアの政府機関・企業を標的にサイバースパイ活動を行ってきたとされる。Kasperskyのセキュリティ研究チーム（Securelist）が継続的に活動を追跡している。

### 新型マルウェア「Umbrij」と攻撃手法

今回確認された新型マルウェア「Umbrij」は、Windowsホスト上でDLLサイドローディングの手法により展開される。研究者は3種類の亜種を確認しており、いずれも被害者のメールアカウントへの不正アクセスを最終目的としている。

注目すべき技術的特徴は「Shadow Token via Remote Debug（STRD）」と呼ばれる手法で、被害者が使用しているChromiumベースブラウザ（Google Chrome、Microsoft Edgeなど）のリモートデバッグポートに接続し、既にログイン済みのセッションからOAuthアクセストークンを静かに生成・窃取する。この手法により、パスワードや多要素認証を直接突破することなく、ログイン済みセッションを持つブラウザから認証済みトークンを取得できるため、被害者に気づかれにくい。

窃取したOAuthトークンを用いて、被害者のGmailアカウントや企業のメールシステムへの不正アクセスが可能になり、機密情報の窃取やさらなる侵害の足がかりとして利用される。

### 対策上の示唆

本手法は、Chromiumベースのブラウザでログイン状態を維持している限り、どのブラウザに対しても悪用され得るとされる。組織としては、リモートデバッグ機能の無効化、ブラウザセッションの定期的な再認証要求、異常なOAuthトークン発行の監視などが対策として考えられる。

---

## 関連記事

なし
