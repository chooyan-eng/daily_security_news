# JadePuffer — LLMエージェント駆動型自律ランサムウェア（2026年）

## 概要

Sysdigが報告した、LLMエージェントが人間の介入なしに偵察・認証情報窃取・横展開・データ暗号化までを自律的に実行したとされる初の事例「JadePuffer」。侵入経路はAI開発プラットフォームLangflowの未認証RCE脆弱性CVE-2025-3248。本番MySQL/Nacos環境まで横展開し、1,342件の設定項目を暗号化・原本削除した。

**同一性の判断に役立つ情報：**
- 攻撃名: JadePuffer（JADEPUFFER）
- 初期侵入CVE: CVE-2025-3248（Langflow 未認証RCE、コード検証エンドポイントの認証欠如）
- 横展開時の悪用CVE: CVE-2021-29441（Alibaba Nacos 認証バイパス）
- 報告元: Sysdig
- 特徴: LLMエージェントによる完全自律型攻撃（偵察〜認証情報窃取〜横展開〜暗号化）
- 被害: Nacosサービス設定項目1,342件を暗号化・原本削除
- 持続性確保: Langflowホストへcronジョブ設置（30分毎にC2ビーコン）
- 関連トピック: [Langflow RCE脆弱性（CVE-2026-5027）](./langflow-rce-cve-2026-5027.md)（別CVE・同一製品）

## タイムライン

- [2026-07-07 「JadePuffer」— AIエージェントが自律的に実行した初のランサムウェア攻撃、Langflow脆弱性を悪用](../articles/2026-07-07-jadepuffer-agentic-ransomware-langflow.md)
