# Click To Pray IDOR脆弱性による個人情報露出（2026年）

## 概要

バチカン公式の祈りアプリ「Click To Pray」における未認証API・IDOR（Insecure Direct Object Reference）脆弱性。連番IDを用いてログインなしに他ユーザーの氏名・メールアドレス・居住国・生年月日・アカウントロール等を取得可能だった。研究者 BobDaHacker が2026年1月に報告したが約半年間放置され、70万件超のアカウントが影響を受けた。

**同一性の判断に役立つ情報：**
- 対象アプリ: バチカン公式「Click To Pray」
- 脆弱性種別: IDOR（未認証API、連番IDによるアカウント情報取得）
- 発見者: BobDaHacker（2026年1月報告）
- 影響件数: 70万件超のユーザーアカウント
- 修正: 2026年7月（報道後）

## タイムライン

- [2026-07-30 バチカン公式祈りアプリ「Click To Pray」、未認証API脆弱性で70万人超の個人情報が半年以上露出](../articles/2026-07-30-vatican-click-to-pray-idor.md)
