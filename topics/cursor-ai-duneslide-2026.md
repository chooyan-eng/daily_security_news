# Cursor AIコードエディタ サンドボックス脱出脆弱性「DuneSlide」（2026年）

## 概要

AIコードエディタ Cursor に存在した2件の脆弱性「DuneSlide」（CVE-2026-50548／CVE-2026-50549、共にCVSS 9.8）。プロンプトインジェクションを通じてAIエージェントのターミナルサンドボックスから脱出し、任意コマンド実行を可能にする。Cato AI Labsが発見、Cursor 3.0（2026-04-02）で修正済み。

**同一性の判断に役立つ情報：**
- 製品: Cursor（AIコードエディタ）
- CVE: CVE-2026-50548, CVE-2026-50549（CVSS 9.8）
- 脆弱性名: DuneSlide
- 発見者: Cato AI Labs
- 修正バージョン: Cursor 3.0（2026-04-02リリース）
- 攻撃手法: 間接プロンプトインジェクション → サンドボックス脱出 → 任意コマンド実行

## タイムライン

- [2026-07-01 Cursor AIコードエディタの重大脆弱性「DuneSlide」、プロンプトインジェクションでサンドボックス脱出](../articles/2026-07-01-cursor-ai-duneslide-prompt-injection.md)
