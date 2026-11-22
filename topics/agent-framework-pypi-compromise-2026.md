# Microsoft agent-framework PyPIパッケージ侵害（2026年11月）

## 概要

2026年11月17日、Microsoft公式のAIエージェント開発用PyPIパッケージagent-frameworkに不正版1.26.1・1.26.2が公開された事案（約33分間に連続公開、21:20 UTCごろ削除）。.pth起動フックによりimport不要でPython起動時に実行され、Azure ID・CI/CDトークン・AI関連シークレットを窃取。1.26.0が最後の正常版。JFrog、Elastic、Orca、OX Securityが分析。

## タイムライン

- [2026-11-22 Microsoft公式「agent-framework」PyPIパッケージが乗っ取られ、1.26.1／1.26.2に認証情報窃取コード](../articles/2026-11-22-microsoft-agent-framework-pypi-compromise.md)
