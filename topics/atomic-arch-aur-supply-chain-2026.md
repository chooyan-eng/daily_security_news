# Atomic Arch AUR サプライチェーン攻撃（2026年6月）

## 概要

2026年6月11〜12日に発覚した Arch Linux の Arch User Repository（AUR）を標的にした大規模サプライチェーン攻撃。攻撃者は AUR の孤立パッケージ引き継ぎメカニズムを悪用し、1,500件以上のパッケージに悪意あるビルドスクリプトを注入。Rust 製インフォスティーラー（`atomic-lockfile` npm パッケージ）と eBPF ベースのルートキット機能を組み合わせ、開発者ワークステーションや CI/CD 環境の認証情報を狙う。

**同一性の判断に役立つ情報：**
- キャンペーン名: Atomic Arch
- 標的: Arch User Repository（AUR）の孤立パッケージ
- 悪意あるパッケージ: `atomic-lockfile`（npm）、`js-digest`（npm、第2波）
- 侵害パッケージ数: 第1波 約408件 → 最終的に1,500件以上
- 侵害期間: 2026年6月11〜12日に発覚
- マルウェア実装言語: Rust
- 特徴的な機能: eBPF ベースのルートキット（root 取得時）
- 主要標的: 開発者ワークステーション、CI/CD 環境（Arch Linux ベース）

## タイムライン

- [2026-06-20 Atomic Arch：1,500件以上のAURパッケージにeBPFルートキットを注入するサプライチェーン攻撃](../articles/2026-06-20-atomic-arch-aur-supply-chain-ebpf.md)
