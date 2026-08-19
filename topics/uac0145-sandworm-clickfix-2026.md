# UAC-0145（Sandworm系）ClickFix・Android偽アプリキャンペーン（2026年）

## 概要

GRU（ロシア軍参謀本部情報総局）関連の高度なハッキング部隊Sandwormのサブクラスター「UAC-0145」による、ウクライナ標的への攻撃キャンペーン。改ざんしたWebサイト上に独自ツール「SMARTAXE」で偽CAPTCHA（ClickFix手法）を表示しPowerShellコマンド実行を誘導、GHETTOVIBE・SCOUTCURLマルウェアを展開する。並行してメッセージアプリ経由でセキュリティツールに偽装したAndroid APKも配布。EtherHiding（Ethereumスマートコントラクトを用いたC2秘匿）技術を使用。

**同一性の判断に役立つ情報：**
- 脅威アクター: UAC-0145（Sandwormのサブクラスター、GRU関連）
- 追跡機関: CERT-UA
- 手法: ClickFix（偽CAPTCHA経由のPowerShell実行誘導）
- 独自ツール: SMARTAXE（動的ページ改変）
- マルウェア: GHETTOVIBE、SCOUTCURL
- 秘匿技術: EtherHiding（Ethereumスマートコントラクト経由のC2ドメイン取得）
- 侵害サイト数: 少なくとも10（2026年6〜7月）
- 並行キャンペーン: メッセージアプリ経由のAndroid偽APK配布によるバックドア化

## タイムライン

- [2026-07-19 Sandworm系UAC-0145、改ざんWebサイトの偽CAPTCHAとAndroid偽アプリでウクライナ標的を感染](../articles/2026-07-20-uac0145-sandworm-clickfix-ukraine.md)
