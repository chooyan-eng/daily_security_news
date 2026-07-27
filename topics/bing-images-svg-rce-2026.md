# Bing Images SVG経由のリモートコード実行（CVE-2026-32194/CVE-2026-32191）

## 概要

セキュリティ研究企業XBOWが発見した、Microsoft Bingの画像検索機能における重大な脆弱性。細工したSVGファイルを「画像で検索」機能からアップロードするだけで、Bingの本番画像処理サーバー上でWindowsはSYSTEM権限、Linuxはroot権限のコマンドが実行できた。認証・ログイン・クリックは一切不要。根本原因はImageMagickのデフォルト設定にあり、2016年の「ImageTragick」（CVE-2016-3714）と同じ脆弱性クラス。Microsoftは公表前にサーバー側の修正を完了済み。

**同一性の判断に役立つ情報：**
- 対象サービス: Microsoft Bing Images（画像検索）
- CVE: CVE-2026-32194（コマンドインジェクション、アップロード経路）、CVE-2026-32191（SSRF、クローラー取り込み経路）
- CVSS: 両方とも9.8
- 発見者: XBOW
- 脆弱性クラス: ImageTragick系（ImageMagick経由のSVGコマンドインジェクション）
- 対応状況: Microsoftが事前に修正済み、ユーザー側対応不要

## タイムライン

- [2026-07-27 Bing Images の脆弱性、細工SVGファイルでMicrosoftサーバー上のSYSTEM権限コード実行が可能に](../articles/2026-07-27-bing-images-svg-rce.md)
