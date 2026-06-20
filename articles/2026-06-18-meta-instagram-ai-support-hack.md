# Meta の AI サポートチャットボット「HTS」悪用で Instagram 2万件以上のアカウントが乗っ取り被害

- **日付**: 2026-06-18
- **出典**: [TechCrunch](https://techcrunch.com/2026/06/01/hackers-hijacked-instagram-accounts-by-tricking-meta-ai-support-chatbot-into-granting-access/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/meta-ai-support-data-breach-affects-20-000-instagram-accounts/), [SecurityWeek](https://www.securityweek.com/meta-says-20000-instagram-accounts-hacked-via-ai-tool-abuse/)
- **トピック**: [Meta Instagram AI Supportチャットボット悪用による2万アカウント乗っ取り（2026年6月）](../topics/meta-instagram-ai-support-hack-2026.md)
- **分類**: 新規

## 概要

Meta が AI を活用したアカウント回復サポートツール「High Touch Support（HTS）」に存在した設計上の欠陥を悪用した攻撃で、20,225件の Instagram アカウントが乗っ取られた。攻撃者は HTS がメールアドレスとアカウントの紐付けを確認しないという欠陥を利用し、任意の Instagram アカウントのパスワードリセットリンクを取得できた。Meta は6月19日（日本時間6月20日）に被害者への通知を開始する予定。

## 詳細

### 攻撃の仕組み

Meta の High Touch Support（HTS）は、Instagram アカウントからロックアウトされたユーザーを支援する AI 支援型サポートシステム。この HTS には、提供されたメールアドレスが対象の Instagram アカウントに紐付けられているかどうかを確認しないという重大な欠陥があった。

攻撃の流れ：
1. 攻撃者が任意のメールアドレスを用いて HTS にアクセス
2. 標的の Instagram アカウントに「アクセスできない」と申告
3. HTS がメールと Instagram アカウントの紐付けを検証せずにパスワードリセットリンクを発行
4. 攻撃者がリセットリンクを取得し、2FA なしにアカウントを乗っ取り

### 被害の規模と高プロファイルなターゲット

- **被害アカウント数**: 20,225件（Meta 発表）
- **高プロファイルな被害例**:
  - Obama 政権時代のホワイトハウス公式 Instagram アカウント
  - 米国宇宙軍（Space Force）のチーフ・マスター・サージェント John Bentivegna のアカウント

### 発見と対応の経緯

- **2026年5月31日**: Meta がインシデントを発見
- **2026年6月1日〜**: Reddit・X（旧 Twitter）のユーザーが続々とアカウント乗っ取りを報告
- **6月初旬**: Meta が悪用された脆弱性を修正。生成されたパスワードリセットリンクをすべて無効化
- **6月3日**: Meta が被害を受けたアカウントをセキュリティチェックポイントに登録し、強制的にパスワードリセット
- **2026年6月19日**: Meta が20,225人の被害ユーザーに電子的に通知を送付予定

### AI サポートシステムへの攻撃の意義

この事案は AI 支援型カスタマーサポートシステムが持つ認証・検証プロセスの弱点を突いた新しいタイプの攻撃として注目される。従来の技術的脆弱性とは異なり、AI システムの「信頼モデル」（ユーザーの申告を過度に信頼する設計）が攻撃面となった。

また「攻撃者は Instagram をハックしたのではなく、Meta AI に頼んだだけ」（Bitdefender の分析）という表現が示すように、AI ツールのビジネスロジックの欠陥が新たな攻撃ベクターとなることを示す先例となった。

Meta は HTS の UI ボタンを一時的に削除したが、攻撃者は代替手段でアクセスを継続できたとの報告もあり（Android Authority）、根本的な修正の完全性については引き続き確認が必要。

### 推奨対応

1. Instagram で2段階認証（2FA）を必ず有効化（SMS よりも認証アプリを推奨）
2. Meta からの公式通知（6月19日予定）を確認
3. 自身のアカウントへの不審なログイン・パスワードリセット試行をチェック
4. アカウント復旧コードを安全な場所に保管

---

## 関連記事
