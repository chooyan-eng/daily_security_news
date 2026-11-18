# ロシア系COLD RELIC、Google Workspaceから窃取した情報を足がかりに別の米国組織を侵害 Google/Mandiantが事例公開

- **日付**: 2026-11-18
- **出典**: [The Hacker News](https://thehackernews.com/2026/11/russian-cold-relic-hackers-use-stolen.html), [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/russian-star-blizzard-cloud-data/), [SC World](https://www.scworld.com/brief/russian-cyber-espionage-group-cold-relic-leverages-cloud-compromises-for-linked-intrusions)
- **トピック**: [COLD RELIC（Star Blizzard）によるクラウドID連鎖侵害（2026年11月公表）](../topics/cold-relic-google-workspace-chained-intrusion-2026.md)
- **分類**: 新規

## 概要

GoogleとMandiantは11月17日、ロシア系スパイ集団COLD RELIC（別名Star Blizzard）が、ある米国組織のGoogle Workspace特権管理者アカウントを侵害して全データを持ち出し、その情報で同組織の従業員になりすまして2026年に別の米国組織をフィッシングで侵害した連鎖事例を公開した。

## 詳細

### 第1の侵害（2025年後半）

- 窃取済みの認証情報でGoogle Workspaceの特権管理者（Super Admin）アカウントへログイン。アカウント所有者が多要素認証（MFA）の承認要求を承認してしまったことで突破された（プッシュ承認の誤承認）。
- 組織のクラウドドライブ全体を取得。ファイルの直接ダウンロードに加え、攻撃者管理下のメールアドレスへの共有も併用した。
- 職員ディレクトリをエクスポートし、テナント全体を対象とするGoogle Workspaceの「Customer Takeout」エクスポートを開始。
- セキュリティアラートを削除して痕跡を隠した。

### 第2の侵害（2026年）

- 第1の被害組織から得たやり取りや関係性の情報を口実作りに利用し、第1組織の従業員を装って第2の組織へ接触。
- 会話を重ねたうえでフィッシングリンクを送付。リンクは認証情報とログイントークンを取得した後、会話内容に沿った実在の文書へリダイレクトし、不審に思われないようにしていた。
- 第2組織はGoogle WorkspaceのフェデレーションSSOにMicrosoft Entra IDを使っていたため、フィッシングはEntra IDの認証情報・トークンを標的とした（中間者型フィッシングと推測される）。
- SSO側に新しいMFAデバイスを登録して持続的アクセスを確保し、侵害ユーザーがアクセスできるクラウドドライブのファイルを一括ダウンロードした。

Googleは両組織の名称や窃取データの内容を明らかにしていない。

### 推奨される対策・検知

- Workspace監査ログの`CUSTOMER_TAKEOUT_CREATED`イベントを監視する（組織全体のエクスポートの兆候）。
- 侵害が疑われる場合、Google WorkspaceとEntra IDの双方でセッション・トークンを失効させる。片方だけでは不十分。
- MFAデバイスの新規登録、外部アドレスへのドライブ共有、アラートの削除を検知対象にする。

### 技術的な補足

- プッシュ承認型MFAやTOTPは、誤承認や中間者型フィッシング（AiTM）で突破される。特権管理者にはパスキー／FIDO2セキュリティキーなどフィッシング耐性のあるMFAを必須とし、Super Admin権限は日常業務用アカウントから分離するのが基本となる。
- SSOをフェデレーションしている場合、IdP（本件ではEntra ID）のトークン窃取がそのままSaaS側の侵害になる。条件付きアクセス（準拠デバイス要求、トークン保護）とMFA登録時の再認証強化が有効。
- 本件の特徴は、1件目の侵害で得た「実在の関係性」を2件目のソーシャルエンジニアリングに転用した点にある。取引先・協力組織からの連絡であっても、文書共有リンク経由のログイン要求は別経路で確認する運用が求められる。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事
