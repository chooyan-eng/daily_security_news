# ClickFix キャンペーン拡大：BabaDeda・Lorem Ipsum・Potemkin の3系統ローダーが登場

- **日付**: 2026-06-26
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/clickfix-campaigns-expand-malware.html)
- **トピック**: [ClickFix キャンペーン拡大（BabaDeda/Lorem Ipsum/Potemkin、2026年6月）](../topics/clickfix-babadeda-lorem-ipsum-2026.md)
- **分類**: 新規

## 概要

Morphisec・BlueVoyant・Huntress の3社が独立して、ClickFix 手法を使った3系統の新しいマルウェアローダーキャンペーンを報告した。「BabaDeda」「Lorem Ipsum」「Potemkin」と呼ばれる各ローダーは侵害済みWordPressサイト経由で配信され、インフォスティーラー・RATや、Chromium の App-Bound Encryption をバイパスするブラウザ資格情報窃取ツールを最終ペイロードとして展開する。

## 詳細

**ClickFix 手法の概要**

ClickFix は、偽のブラウザアップデートや CAPTCHA 認証を騙った「修正手順」をユーザーに実行させる社会工学的な初期アクセス手法。ユーザーが「Fix」ボタンや手動コマンド実行を行うことでマルウェアの感染チェーンが起動する。今回の3キャンペーンはいずれも侵害済み WordPress サイトをランディングとして使用しており、標的の裾野が大幅に拡大している。

**BabaDeda Loader**

教育・金融業界をターゲットとした 2026年4月以降のキャンペーンで発見。多段階ローダーで、隠蔽された PowerShell → インメモリシェルコード → DLL サイドローディング → 外部ペイロードストレージ → コールバックベース実行のチェーンを使い、インフォスティーラーや RAT を最終ペイロードとして展開。

**Lorem Ipsum Loader**

少なくとも5つの侵害済み WordPress サイトを起点として、新興ローダーおよびバックドアの「Lorem Ipsum Loader」を展開するキャンペーン。Vanilla Tempest（Rapid Brigantine・Vice Society・Vice Spider とも呼ばれる財務目的の脅威アクター）に高信頼度で帰属されており、Rhysida・BlackCat・Zeppelin・Quantum Locker などのランサムウェアファミリーを展開する実績を持つ。

**Potemkin Loader**

MSI パッケージのインストールを起点とし、HTA（HTML Application）ペイロード経由で未文書化ローダー「Potemkin」をドロップする高度な攻撃チェーン。最終ペイロードは以下：
- **EtherRAT**：リモートアクセスツール
- **RMMProject**：Lua スクリプタブル DLL で、リモート画面制御モジュールと、Chromium の **App-Bound Encryption（ABE）** をバイパスするブラウザ資格情報窃取モジュールを持つ

Chromium ABE バイパス機能は Web ブラウザのパスワード保護機能を直接的に無効化するもので、Chrome 124以降で導入されたパスワード暗号化機能を突破する点が特に危険。

**Webアプリへの影響**

ClickFix 経由でブラウザに保存された Web サービスの認証情報（ビジネス SaaS・クラウドコンソール等）が窃取されるリスクが高い。特に Potemkin による ABE バイパスは、Chrome のパスワードマネージャーを信頼していたユーザーの認証情報が平文で窃取される可能性を示している。
