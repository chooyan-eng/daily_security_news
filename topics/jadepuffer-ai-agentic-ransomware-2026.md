# JadePuffer AIエージェント主導型ランサムウェア（2026年）

## 概要

Sysdig が報告した、偵察からデータ暗号化まで攻撃の全工程をLLMエージェントが自律的に実行した初の「完全自律型エージェント主導ランサムウェア」事例。Langflowの未認証RCE脆弱性CVE-2025-3248を突破口とし、Alibaba Nacos上のMySQLサーバーへ横展開した。「エージェント型脅威アクター（ATA）」の到来を示す事例として注目されている。

**同一性の判断に役立つ情報：**
- 名称: JadePuffer
- 報告元: Sysdig 脅威リサーチチーム
- 初期侵入経路: Langflow 未認証RCE脆弱性 CVE-2025-3248
- 横展開先: Alibaba Nacos上のMySQLサーバー
- 攻撃工程: 偵察・認証情報窃取・横展開・永続化・権限昇格・暗号化を全てAIエージェントが自律実行
- 分類概念: エージェント型脅威アクター（Agentic Threat Actor, ATA）
- 報告日: 2026年7月1日（各社報道は7月7日前後まで継続）

## タイムライン

- [2026-07-08 「JadePuffer」— 初のAIエージェント完全主導型ランサムウェア攻撃をSysdigが確認](../articles/2026-07-08-jadepuffer-ai-agentic-ransomware.md)
