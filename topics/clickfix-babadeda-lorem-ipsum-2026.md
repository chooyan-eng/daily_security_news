# ClickFix キャンペーン拡大（BabaDeda/Lorem Ipsum/Potemkin、2026年6月）

## 概要

ClickFix 手法（偽ブラウザアップデートや偽 CAPTCHA による手動コマンド実行誘導）を使った複数系統のマルウェアローダーキャンペーン。2026年6月に Morphisec・BlueVoyant・Huntress の3社が独立して報告。「BabaDeda Loader」「Lorem Ipsum Loader」「Potemkin Loader」の3つのローダーが識別されており、いずれも侵害済み WordPress サイトを配信起点とする。

Potemkin ローダーは最終段階で Chromium の App-Bound Encryption（ABE）をバイパスするブラウザ資格情報窃取モジュールを持ち、Chrome 124 以降で導入されたパスワード暗号化保護を突破する。Lorem Ipsum は Vanilla Tempest（Rhysida・BlackCat 等のランサムウェアオペレーターとして知られる脅威アクター）に帰属される。

**同一性の判断に役立つ情報：**
- 手法：ClickFix（偽ブラウザアップデート・偽 CAPTCHA）
- 配信起点：侵害済み WordPress サイト
- ローダー系統：BabaDeda Loader・Lorem Ipsum Loader・Potemkin Loader
- Lorem Ipsum 帰属：Vanilla Tempest（Vice Society / Vice Spider とも呼ばれる）
- 最終ペイロード：インフォスティーラー・RAT・EtherRAT・RMMProject（ABE バイパス機能付き）
- 特徴：Chromium App-Bound Encryption バイパス（Chrome 124以降のパスワード保護を突破）
- 報告機関：Morphisec・BlueVoyant・Huntress（2026年6月）

## タイムライン

- [2026-06-26 ClickFix キャンペーン拡大：BabaDeda・Lorem Ipsum・Potemkin の3系統ローダーが登場](../articles/2026-06-26-clickfix-babadeda-lorem-ipsum-potemkin.md)
