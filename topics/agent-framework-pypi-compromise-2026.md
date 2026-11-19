# Microsoft agent-framework PyPIパッケージ侵害（2026年11月）

## 概要

MicrosoftのAIエージェント開発用公式Pythonパッケージ `agent-framework` の悪性バージョン 1.26.1／1.26.2 が2026年11月17日にPyPIへ公開された事案。`.pth` ファイルによりPython起動のたびに認証情報窃取コードが実行され、クラウド／CI資格情報を webhook.site へ送信する。両版はPyPIが隔離済み。原因（公開用資格情報の窃取か）は確定していない。

**同一性の判断に役立つ情報：**
- パッケージ: PyPI `agent-framework`／悪性: 1.26.1、1.26.2／最後の正常版: 1.26.0
- 公開日: 2026-11-17（約33分間隔）
- 手口: `.pth` スタートアップフック、流出先 webhook.site
- `agent-framework-core` ほか22の関連パッケージは影響なし

## タイムライン

- [2026-11-19 Microsoft公式「agent-framework」PyPIパッケージが改ざん、1.26.1／1.26.2に認証情報窃取マルウェア](../articles/2026-11-19-microsoft-agent-framework-pypi-compromise.md)
