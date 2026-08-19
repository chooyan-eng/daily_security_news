# AIオーケストレーション基盤Langflowに複数の重大脆弱性（Rubrik Zero Labs調査）

- **日付**: 2026-07-01
- **出典**: [SecurityWeek](https://www.securityweek.com/hackers-exploit-langflow-vulnerability-for-remote-code-execution/) / [CSO Online](https://www.csoonline.com/article/4151203/attackers-exploit-critical-langflow-rce-within-hours-as-cisa-sounds-alarm.html)
- **トピック**: [Langflow RCE脆弱性（CVE-2026-5027）](../topics/langflow-rce-cve-2026-5027.md)
- **分類**: 関連

## 概要

セキュリティ企業Rubrik Zero Labsが、AIエージェント構築基盤Langflow（および n8n、Activepieces）に複数の重大脆弱性を発見した。公開チャットボットのリンクを持つ第三者が認証なしでサーバーを完全に乗っ取れる問題も含まれ、既知のLangflow脆弱性（CVE-2026-5027）とは異なる新たな欠陥群である。

## 詳細

### 発見された脆弱性

最も深刻な問題は、Langflowの「公開チャットリンク」機能を経由して、アプリケーションの内部設計（Pythonコードを含む）が丸ごとリクエストに含まれてしまう欠陥であり、リンクを知る誰もが接続先の認証情報やDB等のシステムを掌握できてしまう。

関連するCVEとして以下が言及されている：
- **CVE-2026-7528**: 無認証でのストレージ圧迫・サーバーファイルパス漏洩
- **CVE-2026-48520**: 無認証でのローカルファイル読み込みからRCEに繋がる、RAG経由の悪性文書投入（「RAGPull」と呼称）

これらは既存トピックで扱っている CVE-2026-5027（POST /api/v2/files のパストラバーサル）とは異なる根本原因・エンドポイントの脆弱性である。

### 対応状況

Rubrikは2026年2月に開発元へ報告し、5月にパッチが完了している。CISAもこれらの脆弱性について警告を発している。

### 位置づけ

Langflow単体に留まらず、n8nやActivepiecesといった他のAIワークフロー／エージェントオーケストレーション基盤についても同種の脆弱性が指摘されており、「AIエージェント基盤のセキュリティ」という2026年に急速に注目されているテーマの一部である。

---

## 関連記事

- [AIアプリ開発プラットフォームLangflowのパストラバーサル脆弱性（CVE-2026-5027）が野放し状態で悪用中](../articles/2026-06-16-langflow-path-traversal-cve-2026-5027.md) - 同じLangflow製品における別の脆弱性。根本原因・CVEは異なるが、AIワークフロー基盤のセキュリティという共通テーマ。
