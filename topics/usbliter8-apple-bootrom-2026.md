# usbliter8 — Apple A12/A13 パッチ不可能 BootROM エクスプロイト（2026年）

## 概要

Paradigm Shift が2026年6月18日に公開した Apple A12/A13/S4/S5 SoC 搭載デバイスを対象としたパッチ不可能な BootROM エクスプロイト。USB コントローラーのハードウェアバグ（DMA バッファアンダーフロー）とファームウェア設定不備の組み合わせにより SecureROM のコード実行フローを奪取する。checkm8 と同様に物理アクセスと DFU モードが必要だが、iOS アップデートによるパッチは不可能。iPhone 11 以前・Apple Watch Series 5 以前が影響を受け、新機種への移行が唯一の恒久対策。

**同一性の判断に役立つ情報：**
- エクスプロイト名: usbliter8
- 開発元: Paradigm Shift（セキュリティ企業）
- 公開日: 2026年6月18日
- 対象 SoC: Apple A12、A13、S4、S5
- 影響デバイス: iPhone XS/XS Max/XR、iPhone 11/11 Pro/Max、Apple Watch Series 4/5
- 攻撃条件: 物理アクセス必須 + DFU モード
- パッチ可能性: ハードウェアバグのため不可能
- 脆弱性タイプ: USB DMA バッファアンダーフロー + SecureROM コード実行

## タイムライン

- [2026-06-21 usbliter8 — Apple A12/A13 チップのパッチ不可能な BootROM エクスプロイト公開](../articles/2026-06-21-usbliter8-apple-a12-a13-bootrom.md)
