# GitLab Oj gem ヒープリーク連鎖RCE（2026年）

## 概要

RubyのJSONパーサgem「Oj」のヒープポインタリークを起点に、自己ホスト型GitLab（18.11.3以前）でgit権限のコマンド実行を可能にする脆弱性連鎖。細工したJupyterノートブックのコミット差分を利用してメモリ配置を特定し、追加のノートブックでペイロードを発火させる。プロジェクトへのプッシュ権限を持つ認証済みユーザーであれば管理者権限や被害者操作なしに悪用可能。GitLabは2026年6月10日にパッチ済みで、研究者depthfirstが7月24日にPoCを公開した。

**同一性の判断に役立つ情報：**
- 発見者: depthfirst
- 起点コンポーネント: Ruby JSONパーサgem「Oj」
- 対象: 自己ホスト型GitLab 18.11.3以前
- 攻撃条件: プロジェクトへのプッシュ権限を持つ認証済みユーザーのみで可（管理者権限・CI/ランナーアクセス・被害者操作不要）
- Oj側修正: 3.17.3（2026年6月4日リリース）
- GitLab側パッチ日: 2026年6月10日
- PoC公開日: 2026年7月24日
- CVE/CVSS: 未付与
- 実悪用: depthfirstの公開時点で確認なし
- CVE: 未割り当て（depthfirstがCVE識別子を要求せず）
- 影響バージョン: GitLab CE/EE 15.2.0〜18.10.7、18.11.0〜18.11.4、19.0.0〜19.0.1
- 修正バージョン: 18.10.8、18.11.5、19.0.2
- 修正日: 2026年6月10日（GitLab側）
- PoC公開日: 2026年7月24日（depthfirst）
- 攻撃前提条件: プロジェクトへのプッシュ権限を持つ認証済みユーザー
- 攻撃手法: 細工Jupyter Notebookのdiff表示によるヒープポインタリーク → メモリ配置特定 → 追加Notebookでペイロード発火
- 根本原因ライブラリ: Ruby用JSONパーサー「Oj」（parser/loader/dumper/document APIにまたがる9件のアドバイザリが関連）
- 対象製品: GitLab CE/EE（セルフホスト型）
- 修正バージョン: 18.11.3以下が脆弱（GitLabが6/10に静かに修正）
- CVE: 未採番
- 発見・PoC公開者: 研究者「depthfirst」
- 悪用経路: Jupyter Notebookプレビュー処理のOjパーサー、ヒープポインタリーク
- 実行権限: gitユーザー
- 前提条件: プロジェクトへのプッシュ権限を持つ認証済みユーザー

## タイムライン

- [2026-07-27 GitLab の未修正インスタンス向けRCE実証コードが公開、Jupyter Notebookのメモリリークを悪用](../articles/2026-07-27-gitlab-oj-parser-rce-poc.md)
- [2026-07-26 GitLab セルフホスト版に未修正時代の完全RCEチェーン公開 — Oj JSONパーサーのメモリ破壊を悪用](../articles/2026-07-26-gitlab-oj-jsonparser-rce-poc.md)
- [2026-07-25 GitLab、Oj gemのヒープリーク連鎖を突くRCEのPoCが公開される](../articles/2026-07-25-gitlab-oj-heap-leak-rce.md)
