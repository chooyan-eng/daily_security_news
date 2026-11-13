# wfx-loot GitHub CIシークレット窃取キャンペーン（2026年11月）

## 概要

2026年11月10日に始まったGitHubサプライチェーン攻撃。窃取済みGitHubトークンで `wfx-docs` ブランチからプローブPR（「docs: dependency audit notes」）を作成後、CIワークフロー／シェルスクリプト／npm postinstallにシークレット窃取コードを注入し、直後にrevertとログ削除を行う。侵害アカウント4,837、プローブ対象61,764リポジトリ、実行1,800超。永続化の指標はEntra IDの `wfx-ci-*` フェデレーション資格情報など。命名はAikido Security。

## タイムライン

- [2026-11-13 「wfx-loot」キャンペーン、窃取したGitHubトークンで6万超のリポジトリにCIシークレット窃取コードを注入](../articles/2026-11-13-wfx-loot-github-ci-secret-stealer.md)
