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
- 攻撃名: JADEPUFFER
- 侵入口の脆弱性: CVE-2025-3248（Langflow 未認証RCE）
- 発見・報告: Sysdig 脅威研究チーム
- 攻撃主体: LLMベース自律型AIエージェント（人間の直接操作なし）
- 被害内容: データベース内1,300件超の設定要素を暗号化、原テーブル削除
- 恐喝手法: ビットコインアドレス＋連絡先メールによる身代金要求
- 特記事項: 暗号化キーが外部送信されておらず復号不可能
- 攻撃手法の特徴: 自律AIエージェントが侵入・横展開・データ窃取・暗号化を人間の逐次指示なく実行
- 悪用された脆弱性: CVE-2025-3248（Langflow、認証欠如によるRCE）
- 関連する別のLangflow脆弱性: CVE-2026-5027（パストラバーサル、既存トピックあり）
- 名称: JadePuffer（JADEPUFFER）
- 特徴: LLMエージェントによる攻撃工程の自律実行（偵察〜暗号化まで）
- 初期侵入脆弱性: CVE-2025-3248（Langflow 未認証RCE）
- 永続化手法: cronジョブによる30分間隔ビーコン
- 被害: Nacosサービス設定1,342件を暗号化・原本削除
- 名称: JadePuffer
- 報告元: Sysdig 脅威リサーチチーム
- 初期侵入経路: Langflow 未認証RCE脆弱性 CVE-2025-3248
- 横展開先: Alibaba Nacos上のMySQLサーバー
- 攻撃工程: 偵察・認証情報窃取・横展開・永続化・権限昇格・暗号化を全てAIエージェントが自律実行
- 分類概念: エージェント型脅威アクター（Agentic Threat Actor, ATA）
- 報告日: 2026年7月1日（各社報道は7月7日前後まで継続）
- 初期侵入経路: Langflow CVE-2025-3248（未認証RCE）
- 悪用されたAI APIキー: OpenAI・Anthropic・DeepSeek・Google Gemini
- 特徴: 偵察〜暗号化〜恐喝文作成までAIエージェントが自律実行
- 人間の関与: C2/ステージングサーバー準備、標的選定のみ

## タイムライン

- [2026-07-23 セキュリティ企業Sysdig、初の「エージェント型」AIランサムウェア「JadePuffer」を確認](../articles/2026-07-23-jadepuffer-agentic-ai-ransomware.md)
- [2026-07-08 「JadePuffer」— 初のAIエージェント完全主導型ランサムウェア攻撃をSysdigが確認](../articles/2026-07-08-jadepuffer-ai-agentic-ransomware.md)
- [2026-07-07 「JadePuffer」— AIエージェントが自律的に実行した初のランサムウェア攻撃、Langflow脆弱性を悪用](../articles/2026-07-07-jadepuffer-agentic-ransomware-langflow.md)
- [2026-07-06 JadePuffer：AIエージェントが全工程を自律実行した初のランサムウェア攻撃事例](../articles/2026-07-06-jadepuffer-ai-agentic-ransomware.md)
- [2026-07-05 JADEPUFFER：自律型AIエージェントによる初のランサムウェア攻撃をSysdigが確認](../articles/2026-07-05-jadepuffer-agentic-ransomware-langflow.md)
- [2026-07-03 自律型AIエージェントが単独で実行した「初のAI主導ランサムウェア攻撃」、Langflowの脆弱性を悪用](../articles/2026-07-03-ai-agent-autonomous-ransomware-langflow.md)
