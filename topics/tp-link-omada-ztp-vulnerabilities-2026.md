# TP-Link Omada ZTP 脆弱性群（2026年8月）

## 概要

Forescout Vedere LabsがBlack Hat USAで公表した、TP-Link Omadaのゼロタッチプロビジョニング（ZTP）機構に存在する15件の脆弱性群。ハードコードされた暗号鍵、認証情報の弱い保護、証明書検証不備によるMITM、クラウド自動採用時のレースコンディション、コントローラーWeb管理画面のXSSなどが含まれ、連鎖させることでデバイス乗っ取り・なりすまし・ネットワーク侵入拠点構築が可能。同種の設計上の弱点はOmada以外のVIGI・Festa・Tapo・Kasa製品にも存在。TP-Linkはパッチ提供済み。

**同一性の判断に役立つ情報：**
- 対象製品: TP-Link Omadaネットワーク機器のゼロタッチプロビジョニング（ZTP）機構
- 発見数: 15件の脆弱性
- 調査元: Forescout Vedere Labs（Black Hat USA 2026で発表）
- 主な脆弱性類型: ハードコード鍵/証明書、認証情報の弱い保護、証明書検証不備(MITM)、クラウド自動採用のレースコンディション、コントローラーWeb UIのXSS
- 波及製品: VIGI IPカメラ、Festaルーター、Tapo/Kasaスマートホーム製品
- 対応: TP-Linkがファームウェアパッチをリリース済み

## タイムライン

- [2026-08-06 TP-Link Omadaのゼロタッチプロビジョニング機能に15件の脆弱性、ネットワーク乗っ取りへ連鎖可能](../articles/2026-08-06-tp-link-omada-ztp-vulnerabilities-2026.md)
