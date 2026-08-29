# Next.jsに2件の重大脆弱性、AVIF画像処理とWindowsパストラバーサルで未認証RCE

- **日付**: 2026-08-29
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/nextjs-patches-critical-avif-and.html), [Next.js公式ブログ](https://nextjs.org/blog/august-2026-security-release), [Vercel Changelog](https://vercel.com/changelog/nextjs-august-2026-security-release)
- **トピック**: [Next.js 未認証RCE脆弱性2件（AVIF画像処理／Windowsパストラバーサル、2026年8月）](../topics/nextjs-avif-windows-path-traversal-rce-2026.md)
- **分類**: 新規

## 概要

Webアプリケーションフレームワーク「Next.js」に、未認証のリモートコード実行につながる重大な脆弱性2件が発見された。1件はAVIF画像処理時のヒープバッファオーバーフロー、もう1件はWindowsファイルシステム上で稼働するサーバーを狙ったパストラバーサルで、Vercelは2026年8月25日にNext.js 15.5.24／16.3.3で修正版をリリースした。

## 詳細

1件目は、Next.jsが画像最適化に使用する「sharp」パッケージが依存するCライブラリ「libheif」のAVIFファイルパース処理に存在するヒープバッファオーバーフロー（GHSA-2xp9-vwfh-vxw4）で、攻撃者が細工したAVIF画像をNext.jsアプリケーションに処理させることでリモートコード実行に至る可能性がある。CVSS v4スコアは9.5と非常に高い深刻度が付与されている。この脆弱性はNext.jsバージョン10.0.0から15.5.23まで、および16.x系列の16.3.2までの全リリースに影響する。

2件目のCVE-2026-75604は、PagesルーターまたはCache Componentsを使用しないAppルーターを利用するNext.jsアプリケーションに影響するパストラバーサル脆弱性（CWE-22）で、対象アプリケーションがWindowsファイルシステム上で稼働しているサーバーで動作している場合に悪用され得る。GitHubはこの脆弱性をCriticalと分類している。

Next.jsは月間4500万件超のダウンロード数を誇る主要なReactフレームワークであり、多数の商用Webサービスの基盤として利用されている。今回の2件はいずれも未認証での攻撃が可能とされ、影響範囲の広さから注視されている。修正版はNext.js 15.5.24（Maintenance LTS）および16.3.3（Active LTS）として2026年8月25日にリリースされ、`npm install next@15.5.24`または`npm install next@16.3.3`で適用できる。2026年8月27日時点では、いずれの脆弱性についても実際の悪用は報告されていない。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
