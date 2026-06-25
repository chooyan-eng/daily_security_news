# Apple A12/A13 SecureROM usbliter8 修正不可能な BootROM エクスプロイト（2026年6月）

## 概要

セキュリティ研究グループ Paradigm Shift が 2026年6月18〜19日に公開した、Apple A12/A13 チップの SecureROM を標的とした修正不可能なエクスプロイト「usbliter8」。Synopsys DWC2 USB コントローラのハードウェアバグとファームウェア設定の欠陥を組み合わせ、アプリケーションプロセッサのブートチェーン全体を侵害可能。物理的なデバイスアクセスと DFU モードが必要で、Secure Enclave は影響を受けない。

**同一性の判断に役立つ情報：**
- エクスプロイト名: usbliter8
- 発見者/公開者: Paradigm Shift
- 影響チップ: Apple A12 Bionic、A13 Bionic
- 影響デバイス: iPhone XS/XS Max/XR（A12）、iPhone 11/11 Pro/11 Pro Max（A13）
- 脆弱性の種別: BootROM（SecureROM）レベルのハードウェア脆弱性（修正不可能）
- 攻撃要件: 物理アクセス + DFU モード + 専用ハードウェア（RP2350 ベースケーブル）
- CVE: 未発行（2026年6月19日時点）
- Secure Enclave への影響: なし（ユーザーデータは保護される）
- 類似エクスプロイト: checkm8（2019年、A5〜A11 対象）

## タイムライン

- [2026-06-20 Apple A12/A13 SecureROM に「usbliter8」修正不可能なBootROMエクスプロイト公開](../articles/2026-06-20-apple-a12-a13-securerom-usbliter8.md)
