# 偽装ITヘルプデスクの電話で幹部を騙しMicrosoft 365を乗っ取る「PREY-0058」キャンペーン

- **日付**: 2026-09-08
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/09/08/vishing-microsoft-365-data-theft-extortion/), [The Hacker News](https://thehackernews.com/2026/09/microsoft-365-attackers-use-help-desk.html), [Security Affairs](https://securityaffairs.com/198634/cyber-crime/it-help-desk-impersonation-lets-hackers-bypass-mfa.html)
- **トピック**: [「PREY-0058」ITヘルプデスク偽装ビッシングによるMicrosoft 365侵害（2026年）](../topics/prey-0058-helpdesk-vishing-m365-2026.md)
- **分類**: 新規

## 概要

セキュリティ企業Arctic Wolfが、社内ITヘルプデスクを装った電話（ビッシング）で企業幹部を騙し、Microsoft 365などSaaSアカウントへの不正アクセス・データ窃取・恐喝を行う攻撃クラスター「PREY-0058」を報告した。窃取したセッショントークンを住宅用プロキシ経由で再生し、多要素認証（MFA）を実質的に回避する手口が特徴。

## 詳細

PREY-0058と名付けられた攻撃クラスターは、取締役・副社長クラスの経営幹部を主な標的とする。攻撃者は社内のIT部門を装って電話をかけ、被害者を偽の認証ポータルへ誘導する。この偽ポータルで入力された認証情報やセッション情報が攻撃者の手に渡る。

窃取したセッショントークンは、被害組織の通常のアクセス元に近い場所からのアクセスに見せかけるため、住宅用IPアドレスを利用するプロキシサービス経由で再生（リプレイ）される。これにより、フィッシング耐性のないMFA実装であっても、正規セッションへの割り込みという形で実質的に回避されてしまう。侵入後はSharePoint、OneDrive、Exchange、Boxなど企業が日常的に利用するMicrosoft 365関連サービスからデータが収集され、収集後に金銭を要求する恐喝が行われる。

Arctic WolfはこのクラスターについてTTP（戦術・技術・手順）面で、Google Threat Intelligence Groupが「UNC6671」と呼ぶデータ恐喝グループと顕著な類似性があると指摘している。UNC6671系のグループは過去にBlackFile、Pink、Helix、Cinder、Redactなど複数の名称で活動が確認されてきた恐喝クラスターであり、SaaS環境を狙った同種の攻撃が継続的に行われていることを示している。

Arctic Wolfは対策として、条件付きアクセス（Conditional Access）設定を強化してプロキシ・ホスティング由来のトラフィックをブロックまたは追加検証の対象とすること、フィッシングされたセッショントークンでは迂回できないフィッシング耐性MFA（パスキー等）への切り替え、単一のSharePointアカウントがアクセスできる範囲の最小化、そしてヘルプデスク担当者がビッシングの兆候を見抜けるようにするトレーニングの実施を推奨している。ITヘルプデスクを装ったソーシャルエンジニアリングは、ShinyHuntersなど他の大規模恐喝グループでも近年多用されている手口であり、企業のSaaS環境全般にとって継続的な脅威となっている。
