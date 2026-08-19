# Atlassian Rovo プロンプトインジェクション・データ持ち出し脆弱性（2026年）

## 概要

Atlassianの企業向けAIアシスタント「Rovo」に存在する、間接プロンプトインジェクションを用いたゼロクリックのデータ持ち出し脆弱性。攻撃者はJiraチケットやConfluence文書などに隠したプロンプトを仕込み、RovoのURL取得ツールを悪用してJira・Confluence・Bitbucket・Slack・Google Workspace・Microsoft 365などの機密データを外部へ送信させることができる。組織単位のWeb検索無効化では防げない。PromptArmorが発見し、2026年5月23日にAtlassianへ報告したが2ヶ月以上未修正のまま公開に至った。

**同一性の判断に役立つ情報：**
- 発見者: PromptArmor
- 対象製品: Atlassian Rovo（AIアシスタント）
- 攻撃手法: 間接プロンプトインジェクション（URL取得ツールの悪用）
- 報告日: 2026年5月23日
- 公開日: 2026年8月上旬
- 影響データソース: Jira, Confluence, Bitbucket, Slack, Google Workspace, Microsoft 365, DB, ファイル等

## タイムライン

- [2026-08-09 Atlassian AI「Rovo」、プロンプトインジェクションでJira/Confluenceデータを外部送信可能な脆弱性](../articles/2026-08-09-atlassian-rovo-prompt-injection.md)
