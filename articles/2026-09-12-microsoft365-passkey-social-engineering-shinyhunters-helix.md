# ShinyHunters・Helix関連アクター、パスキー/SSO更新を装った電話ソーシャルエンジニアリングでMicrosoft 365アカウントを侵害

- **日付**: 2026-09-12
- **出典**: [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/09/09/passkey-themed-social-engineering-leads-identity-cloud-compromise/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/passkey-themed-phishing-attacks-lead-to-microsoft-365-data-theft/), [Help Net Security](https://www.helpnetsecurity.com/2026/09/10/microsoft-365-social-engineering-personal-phones/), [GBHackers](https://gbhackers.com/microsoft-365-accounts-hijacked/)
- **分類**: 関連

## 概要

Microsoftは、ShinyHunters/Falcon恐喝グループに関連する「Storm-3121」と、Helix名で活動するBlackFile系グループに関連する「Storm-3032」が、パスキーやSSO（シングルサインオン）の更新を口実にした電話・SMSによるソーシャルエンジニアリングで企業のMicrosoft 365アカウントを侵害していると報告した。2026年5月頃から観測されている手口で、ITヘルプデスクを装う点や窃取したセッションを悪用する点で、既報の「PREY-0058」ビッシングキャンペーンと類似の特徴を持つ。

## 詳細

Microsoftのセキュリティチームは2026年9月9日、パスキーおよびSSO設定変更を口実とした新たなソーシャルエンジニアリング活動について報告した。この活動は少なくとも2026年5月から観測されており、攻撃者はまず標的組織や従業員に関する事前調査を行った上で、社内ITヘルプデスクになりすまして従業員に電話やメッセージを送りつける。攻撃者は、パスキー・多要素認証（MFA）・シングルサインオン（SSO）の設定を緊急に更新しなければ社内システムへのアクセスを失うと従業員に告げ、心理的な圧力をかける。

被害者はその後、正規のMicrosoftログインページを模したフィッシングサイトへ誘導される。リンクは従業員の個人携帯電話宛のSMSで送られるケースもある。Microsoftによれば、攻撃者の口実には頻繁に「パスキー」という語が登場するものの、実際には被害者にパスキーを登録させようとしているわけではなく、あくまで正規の認証プロセスを装ってセッション情報や認証情報を窃取することが目的だという。

Microsoftは、本活動に関与するクラスターとして、ShinyHunters・Falcon恐喝グループに関連する「Storm-3121」と、BlackFile系の恐喝グループメンバーが現在「Helix」名義で活動しているとされる「Storm-3032」の2系統を挙げている。

この手口は、Arctic Wolfが追跡する攻撃クラスター「PREY-0058」（社内ITヘルプデスクを装う電話で企業幹部を偽の認証ポータルへ誘導し、窃取したセッショントークンを住宅用プロキシ経由で再生してMFAを回避する手口。Google Threat Intelligence GroupはUNC6671〈別名BlackFile/Pink/Helix/Cinder/Redact〉として追跡）と、標的（Microsoft 365）・手口（ヘルプデスクを装う電話・SSO/MFA関連の口実・セッション窃取）の両面で強い類似性が見られる。また、OAuthデバイス認証フローの悪用によりパスワードやMFAを回避する「デバイスコードフィッシング」の系譜とも、Microsoft 365を主要標的とする点で軌を一にしている。同一の攻撃キャンペーンと断定するには材料が不足するものの、SaaS環境を狙う恐喝グループ群が同種のソーシャルエンジニアリング手口を並行して用いている状況がうかがえる。

## 関連記事

- [「PREY-0058」ITヘルプデスク偽装ビッシングによるMicrosoft 365侵害（2026年）](../topics/prey-0058-helpdesk-vishing-m365-2026.md) - ITヘルプデスクを装う電話でMFAを回避しMicrosoft 365を侵害する手口が酷似
- [デバイスコードフィッシング / AiTM セッショントークン窃取（2026年）](../topics/device-code-phishing-aitm-2026.md) - Microsoft 365を主要標的とするセッション窃取型フィッシングの系譜として関連
