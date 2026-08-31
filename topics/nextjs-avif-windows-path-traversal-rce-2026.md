# Next.js 未認証RCE脆弱性2件（AVIF画像処理／Windowsパストラバーサル、2026年8月）

## 概要

Reactベースの人気Webフレームワーク「Next.js」に、未認証のリモートコード実行につながる重大な脆弱性2件が判明。1件はsharp/libheif経由のAVIF画像処理におけるヒープバッファオーバーフロー（CVSS v4: 9.5）、もう1件はWindowsファイルシステム上で稼働するサーバーを狙ったパストラバーサル（CVE-2026-75604）。Vercelは2026年8月25日にv15.5.24／v16.3.3で修正した。

**同一性の判断に役立つ情報：**
- 対象製品: Next.js（10.0.0〜15.5.23、16.x系列16.3.2まで がAVIF脆弱性の対象。Pages/App Router利用アプリがパストラバーサル脆弱性の対象）
- 脆弱性1: GHSA-2xp9-vwfh-vxw4（AVIF画像処理ヒープバッファオーバーフロー、libheif起因、CVSS v4 9.5）
- 脆弱性2: CVE-2026-75604（Windowsファイルシステム上でのパストラバーサル、CWE-22、GitHub評価でCritical）
- 修正版: Next.js 15.5.24（Maintenance LTS）、16.3.3（Active LTS）、2026年8月25日リリース
- 悪用状況: 2026年8月27日時点で実悪用の報告なし
- 別トピックとの区別: 過去のNext.js脆弱性（認可バイパス等）とは異なる、2026年8月の新規CVE群

## タイムライン

- [2026-08-29 Next.jsに2件の重大脆弱性、AVIF画像処理とWindowsパストラバーサルで未認証RCE](../articles/2026-08-29-nextjs-avif-windows-path-traversal-rce.md)
