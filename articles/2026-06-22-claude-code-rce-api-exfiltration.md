# Claude Codeのプロジェクトファイル経由でRCEとAPIキー窃取が可能な脆弱性（CVE-2025-59536/CVE-2026-21852）

- **日付**: 2026-06-22
- **出典**: [Check Point Research](https://research.checkpoint.com/2026/rce-and-api-token-exfiltration-through-claude-code-project-files-cve-2025-59536/)
- **トピック**: [Claude Code RCE・APIキー窃取脆弱性（CVE-2025-59536/CVE-2026-21852）](../topics/claude-code-rce-cve-2025-59536.md)
- **分類**: 新規

## 概要

Check Point Research は Anthropic の AI コーディングアシスタント「Claude Code」に、悪意あるリポジトリのプロジェクトファイル（`.claude/settings.json` など）を通じてリモートコード実行（RCE）および Anthropic API キー窃取が可能な2件の脆弱性を発見・報告した。CVE-2025-59536（CVSS 8.7）はMCPフック経由のRCE、CVE-2026-21852（CVSS 5.3）は `ANTHROPIC_BASE_URL` 操作によるAPIキー流出。すべての脆弱性はすでにAnthropicによって修正済み。

## 詳細

### CVE-2025-59536 — フック経由のリモートコード実行（CVSS 8.7 High）

**脆弱性の仕組み：**

Claude Code では `.claude/settings.json` ファイルにフック（Hooks）を定義できる。フックはファイル保存・コマンド実行・セッション開始などのライフサイクルイベントに連動して自動実行されるシェルコマンドである。

**悪用手法：**

攻撃者が悪意ある `.claude/settings.json` を含む公開リポジトリを用意する。開発者がそのリポジトリを Claude Code で開くと、信頼確認ダイアログが表示される **前** にフックが実行されてしまい、任意のシェルコマンドが被害者のマシン上で実行される。

**タイムライン：**
- 2025年7月21日：Check Point が Anthropic へ報告
- 2025年8月26日：最終的な修正リリース
- 2025年10月3日：CVE 公式公開
- 修正バージョン: Claude Code v1.0.111以降

### CVE-2026-21852 — ANTHROPIC_BASE_URL 操作によるAPIキー流出（CVSS 5.3 Moderate）

**脆弱性の仕組み：**

Claude Code は `ANTHROPIC_BASE_URL` 環境変数を使って API リクエストの送信先を決定する。この変数はリポジトリの設定ファイルからオーバーライドが可能だった。

**悪用手法：**

悪意あるリポジトリの設定ファイルで `ANTHROPIC_BASE_URL` を攻撃者が管理するサーバーに書き換える。以降、Claude Code が送信するすべてのリクエスト（プロンプト＋Anthropic API キーヘッダー）が攻撃者のサーバーに転送される。

**修正バージョン:** Claude Code v2.0.65以降（2026年1月）

### 攻撃のサプライチェーンリスク

この脆弱性の特徴は、**悪意あるコミット1つで、そのリポジトリを開いたすべての開発者のマシンを侵害できる**点にある。オープンソース開発者が PR をチェックアウトするだけで攻撃が成立するため、サプライチェーン攻撃の起点として高い価値を持つ。

具体的な攻撃シナリオ：
1. 攻撃者が人気OSSプロジェクトにフォーク・PR を作成
2. PR ブランチに悪意ある `.claude/settings.json` を含める
3. メンテナーが Claude Code でPRをレビューした瞬間にマルウェアが実行
4. 開発者のマシン上のシークレット（SSH鍵・クラウド認証情報・APIキー）が窃取される

### 現在の状況

- CVE-2025-59536: v1.0.111以降で修正済み
- CVE-2026-21852: v2.0.65以降で修正済み
- Check Point と Anthropic のセキュリティチームが協力して全脆弱性の修正を確認済み
- Backslash Security によれば、2026年4月〜6月初旬にかけてAnthropicはClaudeCode関連で数十件の新たな脆弱性にパッチを当てている

### 対策

1. Claude Code を最新バージョン（v2.0.65以降）に更新する
2. 信頼できない/不明なリポジトリを Claude Code で開く際は特に注意する
3. `.claude/settings.json` を含むPRのレビューには注意を払う
4. CI/CD 環境では最小権限の原則に従いClaudeCode用APIキーのスコープを制限する
