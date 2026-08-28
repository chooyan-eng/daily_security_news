# Direwolf ランサムウェアグループ（2026年）

## 概要

2025年5月頃に出現した二重恐喝型ランサムウェアグループ。Go言語製のランサムウェア（Curve25519＋ChaCha20暗号化、拡張子「.direwolf」）を用い、バックアップ削除・ログ無効化・復旧妨害サービスの強制終了といった典型的な二重恐喝手口を持つ。製造業・技術分野を中心に米国・タイ・台湾・シンガポール・トルコなど複数国で被害が確認されている。

**同一性の判断に役立つ情報：**
- グループ名: Direwolf
- 初確認時期: 2025年5月頃
- 実装言語: Go
- 暗号化方式: Curve25519 + ChaCha20
- 暗号化後の拡張子: .direwolf
- 攻撃手口: 二重恐喝（データ窃取＋暗号化）、バックアップ削除、ログ無効化
- 主な標的分野: 製造業、テクノロジー
- 主な被害国: 米国、タイ、台湾、シンガポール、トルコ 他

## タイムライン

- [2026-08-28 DireWolfランサムウェア、臓器移植支援団体National Kidney Registryの253GBデータ窃取を主張](../articles/2026-08-28-national-kidney-registry-direwolf-breach.md)
- [2026-08-19 Direwolfランサムウェア、スウェーデンの健康管理アプリ企業Lifesumをリークサイトに掲載](../articles/2026-08-19-direwolf-lifesum-victim.md)
- [2026-08-18 ランサムウェアグループ Direwolf、AIコンパニオンアプリ運営元 Eva AI Limited をリークサイトに掲載](../articles/2026-08-18-eva-ai-direwolf-ransomware.md)
