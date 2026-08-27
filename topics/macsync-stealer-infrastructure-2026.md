# MacSync Stealer macOS情報窃取マルウェア（2026年）

## 概要

Microsoft Defender Expertsが特定した、macOSを標的とする情報窃取マルウェア「MacSync Stealer」。ドメイン名ではなくプロセス系譜・コマンドライン・通信パターンなど複数の挙動特徴の一致を条件に、ローテーションする30以上の攻撃基盤ドメインを特定。ClickFix型のソーシャルエンジニアリングでターミナルにコマンドを実行させ感染させる。

**同一性の判断に役立つ情報：**
- マルウェア名: MacSync Stealer
- 対象OS: macOS
- 発見: Microsoft Defender Experts
- 特定された関連ドメイン数: 30以上（ローテーション運用）
- 感染経路: ClickFix型ソーシャルエンジニアリング（ターミナルでのコマンド実行誘導）
- 窃取対象: 認証情報、ブラウザデータ、クラウドアクセスキー、SSH鍵、機密ファイル
- 検知手法: プロセス系譜・コマンドラインパターン・通信パス（/curl/, /dynamic?txd=, /gate?buildtxd= 等）の突合

## タイムライン

- [2026-08-24 Microsoft、macOS狙いの情報窃取マルウェア「MacSync Stealer」の攻撃基盤ドメイン30件超を特定](../articles/2026-08-24-macsync-stealer-infrastructure.md)
