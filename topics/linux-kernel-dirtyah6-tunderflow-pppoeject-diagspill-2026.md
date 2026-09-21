# Linuxカーネル「DirtyAH6」等4件のローカルroot権限奪取脆弱性（2026年9月）

## 概要

セキュリティ研究者Asim Manizada氏が発見・報告したLinuxカーネルの4件のメモリ安全性脆弱性「DirtyAH6」「TUNderflow」「PPPoEject」「DiagSpill」。いずれもカーネルのネットワーキング関連コードに起因し、動作するローカルroot権限奪取エクスプロイトとともに2026年9月18日に技術解説が公開された。各ディストリビューションと事前調整のうえ既に修正済み。

**同一性の判断に役立つ情報：**
- 脆弱性名: DirtyAH6（IPv6 IPsec AHヘッダー処理）、TUNderflow、PPPoEject（PPPoE Use-After-Free）、DiagSpill（SCTPレポーティング、16bitカウンタのオーバーフロー）
- 発見者: Asim Manizada氏（AI支援によるカーネルメモリレイアウト解析で発見）
- 報告〜公開: 2026年7月中旬に報告、2026年9月18日に実証エクスプロイト付き技術解説を公開
- 対象: Linuxカーネル（各ディストリビューションで事前調整のうえ修正済み）
- 悪用状況: 報道時点で実環境での悪用報告なし
- 類似の既存トピック「Linuxカーネル ローカルroot権限奪取 公開エクスプロイト群」（copy.fail／ssh-keysign-pwn／XFRM ESP-in-TCP／Dirty Frag）とはCVE・脆弱性名が異なる別系統

## タイムライン

- [2026-09-21 Linuxカーネルに新たな4件のローカルroot権限奪取脆弱性、研究者がAI支援で発見・実証エクスプロイトを公開](../articles/2026-09-21-linux-kernel-dirtyah6-quartet.md)
