# 「Pass-ta-key」攻撃、Googleパスワードマネージャーの同期パスキーをマルウェア経由で乗っ取り可能とUnit 42が実証

- **日付**: 2026-08-04
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/google-password-manager-attacks-could.html)
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/new-pass-ta-key-attacks-let-malware-hijack-google-synced-passkeys/)
- **トピック**: [Pass-ta-key：Googleパスワードマネージャー パスキー攻撃（2026年8月）](../topics/pass-ta-key-google-password-manager-2026.md)
- **分類**: 新規

## 概要

Palo Alto Networks傘下のUnit 42は、既にマルウェアに感染したWindows端末上から、Google Chromeの「Googleパスワードマネージャー」に同期されたパスキーを乗っ取る3種類の攻撃手法「Pass-ta-key」「Silver Pass-ta-key」「Golden Pass-ta-key」を実証した。パスキー自体の暗号方式を破るものではないが、端末侵害を前提に認証情報を窃取・悪用できる点が示された。

## 詳細

Unit 42が2026年8月3日に公開した調査によると、これら3つの攻撃はいずれもWindows端末上で既に権限を持たないマルウェアが動作していることを前提とする。TPM（Trusted Platform Module）を備えたWindows環境のChrome上のGoogleパスワードマネージャー（クラウド認証器）が対象。

- **Pass-ta-key**：非特権のマルウェアが信頼済みデバイスになりすまし、被害者のパスキーに対する有効な認証応答を要求する。
- **Silver Pass-ta-key**：デバイスのオンボーディングや復旧の仕組みの弱点を突き、攻撃者制御下のユーザー検証キーをサイレントに設置する。
- **Golden Pass-ta-key（最も深刻）**：同期パスキーの秘密鍵を復号する32バイトの「Security Domain Secret（SDS）」を抽出できる。SDSを取得されると、Googleパスワードマネージャー、Chrome、GitHub、eBayなど同期対象の全パスキーの秘密鍵が復元可能になるおそれがある。

研究チームは、パスキーの暗号理論そのものは破られておらず、悪意あるWebサイトを閲覧しただけで攻撃が成立するわけではないと強調している。攻撃の起点は常に「端末侵害済みのマルウェア」であり、Chromeおよびクラウド認証器のデバイス信頼・オンボーディング・復旧・同期処理の実装上の弱点を突くものである。

### 影響範囲

- 対象：Windows上のChromeにおけるGoogleパスワードマネージャーの同期パスキー機能
- 前提条件：端末が既にマルウェアに感染していること
- 最大の影響：Security Domain Secret抽出による同期パスキー全体の秘密鍵復元

### セキュリティ上の考察

パスキーはフィッシング耐性の高い認証手段として普及が進む一方、今回の研究は「クラウド同期」の仕組みそのものが新たな攻撃面になり得ることを示した。パスキー導入企業・サービス提供者は、エンドポイントのマルウェア対策を引き続き強化するとともに、Google側の同期・復旧フローの改善状況を注視する必要がある。

---

## 関連記事

なし（新規トピック）
