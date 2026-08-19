# Claude Cowork（Windows版）のサンドボックス脱出攻撃チェーンが判明、root権限コマンド実行とネットワーク制限バイパスが可能に

- **日付**: 2026-07-06
- **出典**: [SC Media](https://www.scworld.com/brief/researchers-detail-attack-chain-escaping-anthropics-claude-cowork-sandbox)
- **トピック**: [Claude Code RCE・APIキー窃取脆弱性（CVE-2025-59536/CVE-2026-21852）](../topics/claude-code-rce-cve-2025-59536.md)
- **分類**: 関連

## 概要

セキュリティ研究チームArmadinが、AnthropicのClaude Cowork（Windows版）を対象とする攻撃チェーンを発表した。ローカルでコード実行権限を持つ攻撃者は、Claude Desktopのアプリケーションディレクトリに悪意あるファイルを設置し、Cowork基盤となるVMサービスと通信する信頼済みプロセスを乗っ取ることで、サンドボックス内でroot権限のコマンド実行とネットワーク制限の完全バイパスが可能になる。

## 詳細

### 攻撃チェーンの概要

Armadinの研究によれば、この攻撃はClaude Cowork for Windowsに存在する2つの弱点を組み合わせたものである。

1つ目は、`CoworkVMService`経由で渡される「resumeフラグ」を操作することでroot権限として任意コマンドを実行できる欠陥。本来はコマンドごとに新規の非特権ユーザーが作成される仕組みだが、このフラグ操作によりその仕組みをバイパスし、rootを含む既存の任意ユーザーとしてコマンドを実行できてしまう。

2つ目は、コマンド単位でドメイン許可リストをワイルドカードで上書きし、ネットワークのegress（外向き通信）制限を無効化できる欠陥である。

### 影響

ローカルでコード実行が可能な攻撃者は、Claude Coworkのサンドボックス内でネットワークegress制限なしにroot権限の任意コマンドを実行できる。サービスインターフェース上の2つの未検証パラメータを悪用することで、機密データを攻撃者が制御するインフラへ持ち出すことが可能になる。Armadinはこの攻撃チェーンをClaude Desktop for Windows バージョン1.9255.2.0に対して検証済みとしている。

### 既存のClaude Code脆弱性との関係

本サイトで既報のClaude Code RCE・APIキー窃取脆弱性（CVE-2025-59536／CVE-2026-21852）はプロジェクトファイル経由のフック実行を悪用するものであり、今回のClaude Cowork攻撃チェーンとは具体的な悪用経路・コンポーネントが異なる。しかし、いずれもAnthropicのAIコーディング／エージェント製品におけるサンドボックス・信頼境界の設計課題という共通点があり、同一製品ファミリーにおける脆弱性の継続的な発見傾向を示している。

### 対策

- Claude Desktop／Coworkを最新版へ更新し、Anthropicからのセキュリティアドバイザリを確認
- ローカルでのコード実行を許可するユーザー・プロセスの権限を最小化
- CoworkVMServiceとの通信ログにおける異常なresumeフラグ操作やドメイン許可リストの上書きを監視

---

## 関連記事

- [Claude Code RCE・APIキー窃取脆弱性（CVE-2025-59536/CVE-2026-21852）](../topics/claude-code-rce-cve-2025-59536.md) - 同じAnthropic製AIコーディング/エージェント製品ファミリーにおける別経路の脆弱性
