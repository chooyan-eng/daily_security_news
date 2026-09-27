# 侵害済みGitHub Actionsが再有効化、休眠していた「Mini Shai-Hulud」ペイロードが再稼働

- **日付**: 2026-09-27
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/compromised-github-actions-came-back.html), [Socket](https://socket.dev/blog/mini-shai-hulud-actions), [BleepingComputer](https://www.bleepingcomputer.com/news/security/github-actions-re-enabled-with-mini-shai-hulud-payload-still-active/)
- **分類**: 関連あり

## 概要

2026年5月のMini Shai-Huludキャンペーンで侵害され無効化されていたGitHub Actions「issues-helper」「maintain-one-comment」が、2026年9月16日に何らかの理由で再有効化され、悪性ペイロードが再びダウンロード・実行される状態となっていたことが判明した。GitHubは9月25日に両アクションを再度無効化した。

## 詳細

「issues-helper」と「maintain-one-comment」は、2026年5月18日に発生したMini Shai-Huludサプライチェーン攻撃キャンペーンの中で侵害され、以降GitHub上で無効化（disabled）状態に置かれていたGitHub Actionsである。侵害されたコード自体はその後もクリーンアップされずリポジトリ内に残存していたが、リポジトリが無効化されていたためダウンロードは不可能な状態だった。

ところが2026年9月16日、GMT+2で11:09〜18:16の間のいずれかのタイミングで、これら2つのリポジトリが何らかの理由で再びダウンロード可能な状態に戻った。原因は2026年9月27日時点で判明していない。この結果、バージョンタグを指定してこれらのActionsを参照していたワークフローは、次回実行時に5月18日時点の悪性コンテンツを再びダウンロード・実行することになった。悪性ペイロードは開発者トークン、認証情報、CI/CDシークレットを標的とするもので、影響範囲は数千のリポジトリに及ぶ可能性があるとSocket社は指摘している。

GitHubは2026年9月25日に両アクションを再度無効化する対応を取った。セキュリティ研究者は、対象アクションをバージョンタグではなくクリーンなコミットハッシュに固定（ピン留め）することや、この期間中に露出した可能性のあるシークレットのローテーションを開発者に推奨している。今回の事案は、一度侵害されたパッケージ・アクションを単に「無効化」するだけでは根本的な対策にならず、悪性コードの完全な削除や、参照側でのコミットハッシュ固定といった防御策の重要性を改めて示すものとなった。

---

## 関連記事

- [npm keyv/cacheableサプライチェーンワーム「Mini Shai-Hulud」、9組織400以上のパッケージに拡散](../articles/2026-08-06-npm-keyv-cacheable-mini-shai-hulud-2026.md) - 同じ「Mini Shai-Hulud」系統のマルウェアを用いた別キャンペーン（発生時期・侵害経路は異なる）
