# Microsoft agent-framework PyPIパッケージ侵害（2026年11月）

## 概要

Microsoft Agent Frameworkの公式Pythonパッケージ「agent-framework」に、2026年11月17日、認証情報窃取コードを含む悪性バージョンがPyPIへ公開された事案。

**同一性の判断に役立つ情報：**
- 悪性バージョン: 1.26.1、1.26.2（約33分間隔で公開、いずれも隔離済み）。最後の正常版は1.26.0
- 手口: site-packagesへ.pthファイルを配置し、Python起動のたびに窃取コードを実行
- 窃取対象: Azure CLI／Azure DevOps、Git、Docker、npm／pip設定、Hugging Faceトークン、.env、OIDCトークン
- 侵入経路・帰属: 未確定（再パッケージ説、新規メンテナーアカウント説など）
- 分析元: Socket、Wiz、JFrog、StepSecurity、SafeDep

## タイムライン

- [2026-11-18 Microsoft公式の「agent-framework」PyPIパッケージが侵害、.pth起動フックで認証情報を窃取する1.26.1／1.26.2が公開](../articles/2026-11-18-microsoft-agent-framework-pypi-compromise.md)
