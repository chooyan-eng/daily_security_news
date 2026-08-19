# GitHub署名付きコミットのハッシュ可鍛性（2026年7月）

## 概要

カーネギーメロン大学のJacob Ginesin氏（Cure53暗号監査担当）が、GitHubで「Verified」表示される署名付きGitコミットについて、署名鍵を持たない第三者でも同一内容・作者・日時のまま異なるハッシュ値・有効な署名を持つ複製コミットを生成できることをarXiv論文で実証。ECDSA・RSA/EdDSA・S/MIMEの3系統すべてに対応する攻撃手法と公開ツール、実証リポジトリを公開。ハッシュベースのブロックリスト防御が回避され得る。

**同一性の判断に役立つ情報：**
- 研究者: Jacob Ginesin（カーネギーメロン大学博士課程／Cure53）
- 論文公開日: 2026年7月2日（arXiv）
- 問題名: ハッシュチェーン可鍛性（hash chain malleability）、原因は署名の可鍛性（signature malleability）
- 攻撃対象の署名方式: ECDSA（(r,s)→(r,n-s)変換）、RSA/EdDSA（OpenPGP署名パケットの未署名領域へのサブパケット追加）、S/MIME（CMS構造の長さフィールドのBER再エンコード）
- 影響: コミットハッシュベースのブロックリスト・悪意あるコミット検知策の回避
- 公開ツール: 3攻撃すべてを実行可能なツールと2つの実証リポジトリを公開

## タイムライン

- [2026-07-09 GitHubの「Verified」署名付きコミット、署名を壊さずハッシュを書き換え可能と判明](../articles/2026-07-09-github-verified-commit-hash-malleability.md)
