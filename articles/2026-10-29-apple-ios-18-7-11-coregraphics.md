# Apple、旧型iPhone向けにiOS 18.7.11を公開しCoreGraphicsの悪用済みゼロデイを修正

- **日付**: 2026-10-29
- **出典**: [Cyber Security News](https://cybersecuritynews.com/apple-fix-for-coregraphics-0-day-flaw/)
- **トピック**: [Apple CoreGraphics CVE-2026-86950 ゼロデイ（2026年9月〜10月）](../topics/apple-coregraphics-cve-2026-86950.md)
- **分類**: 続報

## 概要

Appleは10月26日、iOS 18.7.11およびiPadOS 18.7.11を公開し、標的型攻撃で悪用された可能性のあるCoreGraphicsの脆弱性を旧型デバイス向けにも修正した。

## 詳細

- 既存トピック（CVE-2026-86950）は9月28日にiOS 26系等で修正済みだったが、iOS 18系に留まる旧型端末向けの修正が今回提供された。報道ではCoreGraphicsのゼロデイとされており、CVE番号が同一かは本記事の情報源では明記を確認できていないため、同一事案の続報として扱う。
- 悪用経路は細工したフォント入りPDF等の画像・文書処理で、ユーザー操作を伴わない/最小の操作で攻撃が成立しうる種別。
- 対策: 該当端末はiOS/iPadOS 18.7.11へ更新。メッセージアプリ等で受信した不審なPDFを開かない。

---

## 関連記事


