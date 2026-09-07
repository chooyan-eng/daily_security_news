# WPFunnels「Mail Mint」PHPオブジェクトインジェクション脆弱性群（2026年）

## 概要

メールマーケティング用WordPressプラグイン「Mail Mint」（WPFunnels開発、バージョン1.31.0以下）における、未認証のPHPオブジェクトインジェクション（CVE-2026-84753、CVE-2026-10196）と認可バイパス（CVE-2026-84755）の脆弱性群。`handle_form_submission`関数のデシリアライズ処理に起因し、POPチェーンと組み合わせることでコード実行につながる恐れがある。

**同一性の判断に役立つ情報：**
- 対象製品: Mail Mint（WordPressプラグイン、WPFunnels開発）
- 影響バージョン: 1.31.0以下
- CVE: CVE-2026-84753、CVE-2026-10196（PHPオブジェクトインジェクション）、CVE-2026-84755（認可バイパス）
- 脆弱性種別: CWE-502（信頼できないデータのデシリアライズ）、CWE-862（認可制御の欠落）
- 悪用条件: 未認証（`handle_form_submission`関数経由）
- 関連する過去の脆弱性: CVE-2026-2025（REST APIの認可欠落による情報漏洩）

## タイムライン

- [2026-09-05 WordPress「Mail Mint」にPHPオブジェクトインジェクションと認可バイパスの脆弱性群](../articles/2026-09-05-wpfunnels-mail-mint-object-injection.md)
