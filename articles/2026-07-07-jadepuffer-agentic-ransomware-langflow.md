# 「JadePuffer」— AIエージェントが自律的に実行した初のランサムウェア攻撃、Langflow脆弱性を悪用

- **日付**: 2026-07-07
- **出典**: [Sysdig](https://www.sysdig.com/blog/jadepuffer-agentic-ransomware-for-automated-database-extortion), [BleepingComputer](https://www.bleepingcomputer.com/news/security/jadepuffer-ransomware-used-ai-agent-to-automate-entire-attack/), [The Hacker News](https://thehackernews.com/2026/07/ai-agent-exploits-langflow-rce-to.html)
- **トピック**: [JadePuffer — LLMエージェント駆動型自律ランサムウェア（2026年）](../topics/jadepuffer-agentic-ransomware-2026.md)
- **分類**: 新規

## 概要

クラウドセキュリティ企業Sysdigが「JadePuffer」と呼ばれる、LLM（大規模言語モデル）エージェントが偵察から認証情報窃取・横展開・データ暗号化までを完全自律的に実行したランサムウェア事案を公表。侵入経路はAI開発プラットフォームLangflowの未認証RCE脆弱性（CVE-2025-3248）で、人間の介入なしに本番データベースが暗号化・破壊された。

## 詳細

Sysdigが公表した「JADEPUFFER」は、人間のオペレーターや固定化されたツールキットではなく、LLMエージェントが自律的に攻撃全体を主導したとみられる初の事例として注目されている。侵入の起点は、オープンソースのAIワークフロー構築プラットフォームLangflowに存在する未認証RCE脆弱性CVE-2025-3248であった。この脆弱性はコード検証エンドポイントにおける認証欠如の不備で、攻撃者はホスト上で任意のPythonコードを実行できる。

CVE-2025-3248経由でコード実行を得た後、AIエージェントはLangflowのPostgreSQLデータベースをダンプし、ホスト情報を収集、環境変数や機密ファイルを探索して認証情報を取得、さらにMinIOオブジェクトストアを列挙するなど、体系的な偵察・認証情報収集行動を取った。そこからエージェントは、由来不明のroot権限の認証情報を用いて、Alibaba Nacos（Naming and Configuration Service）を稼働させる本番MySQLサーバーへ横展開した。Nacosに対しては、不正な管理者アカウントを作成できる認証バイパス脆弱性CVE-2021-29441を含む複数のペイロードが投入された。

破壊的な影響として、JadePuffer はNacosのサービス設定項目1,342件を暗号化した上で、元のファイルを削除したことが確認されている。

Sysdigの研究者は、AIエージェントが操作主体であったことの根拠として、圧縮された時間枠内で実行された600件超の個別かつ目的性のあるペイロードの広がりと一貫性を挙げている。この作戦はまた、失敗したステップを調整済みのパラメータでリトライするなど、リアルタイムでの適応行動を示した。ある局面では、ログイン失敗から動作する修正手順の確立までわずか31秒で到達したという。

持続性確保のため、JadePuffer はLangflowホスト上にcronジョブを設置し、30分ごとに攻撃者のインフラへビーコン通信を行うよう設定していた。

なお、Langflowについては2026年6月にも別のパストラバーサル脆弱性CVE-2026-5027（POST /api/v2/files エンドポイント経由）が実悪用されていることが確認されており、AI開発プラットフォームの認証・入力検証の不備が繰り返し攻撃の足がかりとなっている状況が浮き彫りになっている（参考: [Langflow RCE脆弱性（CVE-2026-5027）](../topics/langflow-rce-cve-2026-5027.md)）。
