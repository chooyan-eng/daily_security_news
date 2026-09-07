# MikroTik RouterOS「MikroTrick」SSH認証バイパス連鎖脆弱性（2026年9月）

## 概要

CERT PolskaがMikroTik RouterOSに発見した複数脆弱性のうち、CVE-2026-67276（SSH公開鍵検証の不備）とCVE-2026-86060（SSHログイン時のユーザー名引数処理不備による権限昇格）を連鎖させる「MikroTrick」攻撃チェーンに関するトピック。SSHサービスを外部公開したRouterOS機器に対し、未認証のまま完全な管理者権限を奪取できる。

**同一性の判断に役立つ情報：**
- 対象製品: MikroTik RouterOS（6.x/7.x系）
- 関連CVE: CVE-2026-67276, CVE-2026-67277, CVE-2026-67278, CVE-2026-67279, CVE-2026-67281, CVE-2026-86060（攻撃チェーン名「MikroTrick」はCVE-2026-67276＋CVE-2026-86060）
- 修正版: RouterOS 7.25 beta3、7.24.2、7.23.4、6.49.21
- 悪用状況: SSHサービスを外部公開した機器に対する実悪用をCERT Polskaが確認
- 報告元: CERT Polska、MikroTik公式セキュリティアドバイザリ

## タイムライン

- [2026-09-06 MikroTik RouterOS「MikroTrick」攻撃チェーン、SSH経由の未認証RCEが実悪用中](../articles/2026-09-06-mikrotik-routeros-mikrotrick-rce.md)
