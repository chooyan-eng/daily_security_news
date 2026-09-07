# ClickFix「EtherHiding」BNBスマートチェーン悪用キャンペーン（2026年）

## 概要

5,400件超の侵害Webサイト（主にWordPress／PrestaShop製）を通じて展開されているClickFix型マルウェア配布キャンペーンに関するトピック。偽のCloudflare風CAPTCHA画面で訪問者にコマンド実行を促す典型的なClickFix手口に加え、次段ペイロード情報をBNBスマートチェーン（BSC）上のスマートコントラクトに格納する「EtherHiding」技術を組み合わせている点が特徴。最終的にLumma Stealer等の情報窃取マルウェアを配布する。

**同一性の判断に役立つ情報：**
- 手口: 侵害サイト上の偽CAPTCHA→クリップボード経由のコマンド実行誘導（ClickFix／ClearFake系）
- 技術的特徴: BNBスマートチェーン上のスマートコントラクトを悪性インフラのホスティング先として利用する「EtherHiding」
- 最終ペイロード: Lumma Stealer等の情報窃取マルウェア
- 報告元: Microsoft Threat Intelligence
- 規模: 侵害サイト5,400件超（WordPress／PrestaShop中心）
- 他のClickFix系キャンペーンとの違い: Microsoftが別途報告した「TerminalFix」（偽CAPTCHA→Windows Terminal経由のリバーストンネル攻撃）とは配布インフラの隠蔽手法（ブロックチェーン利用の有無）が異なる別系統のキャンペーン

## タイムライン

- [2026-09-06 侵害サイト5,400件超がBNBスマートチェーン悪用のClickFixマルウェアを配信](../articles/2026-09-06-clickfix-etherhiding-bnb-smartchain.md)
