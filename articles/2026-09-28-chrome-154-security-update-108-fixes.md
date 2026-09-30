# Chrome 154、108件のセキュリティ修正（Critical 11件）、Android/iOS版も更新

- **日付**: 2026-09-28
- **出典**: [TechRepublic / Digital Citizen](https://www.techrepublic.com/article/news-google-chrome-154-108-security-flaws/)
- **トピック**: [Chrome 154 セキュリティアップデート（2026年9月）](../topics/chrome-154-security-update-2026.md)
- **分類**: 関連

## 概要

GoogleはChrome 154を2026年9月23日にリリースし、108件の脆弱性を修正した。うち11件がCriticalで、ANGLE・WebGL・GPUのメモリ破壊やServiceWorker等のUse-After-Free。実悪用の報告はない。Android版・iOS版も更新されている。

## 詳細

報道によれば、Critical 11件はANGLEのバッファオーバーフロー3件、WebGLのバッファオーバーフロー1件、GPUのOOB書き込み2件、ServiceWorker・Fullscreen・WindowDialog・AdFilterのUse-After-Freeを含む。108件中76件は社内発見、32件は外部研究者によるVRP報告。配布バージョンは Linux 154.0.8037.57、Windows/macOS 154.0.8037.57/.58、Android 154.0.8037.57、iOS 154.0.8037.55。HTTPサイトへのアクセス前に警告を出す変更も含まれると報じられている。

Webアプリ開発では、Chromiumベースのブラウザ（Edge等）やElectron/WebViewを使うモバイル・デスクトップアプリも上流の修正取り込みが必要となるため、更新状況の確認が推奨される。

出典: [TechRepublic](https://www.techrepublic.com/article/news-google-chrome-154-108-security-flaws/)、[Digital Citizen](https://www.digitalcitizen.life/chrome-154-fixes-108-security-flaws-including-11-critical-vulnerabilities/)

---

## 関連記事

- [Chrome 152 セキュリティアップデート](../articles/2026-09-01-chrome-152-security-update.md) - 同一プロジェクトの直近アップデート
