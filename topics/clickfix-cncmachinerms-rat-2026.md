# ClickFix経由の新種RAT「CNCMachineRMS」配布キャンペーン（2026年8月）

## 概要

ClickFix型（偽の「修正手順」でユーザーにコマンドを実行させる）攻撃を起点に、未報告だった新種RAT「CNCMachineRMS」を配布するキャンペーン。正規に署名されたIBM SPSS IDEバイナリと4つのデコイDLL、日付フォーマットAPIを悪用する多段階のBabaDeda系感染チェーンを採用。CNCMachineRMSはインポートテーブルを持たずランタイムハッシングでAPI呼び出しを隠蔽する。2026年8月12日に報告。

**同一性の判断に役立つ情報：**
- 攻撃手法: ClickFix（偽の修正プロンプト/CAPTCHA等でコマンド実行を誘導）
- 悪用される正規バイナリ: IBM SPSS IDE（ローダーとして悪用）
- マルウェア系統: BabaDeda系感染チェーン
- 展開されるRAT名: CNCMachineRMS（x64、約1.14MB、インポートテーブルなし、ランタイムAPIハッシング）
- 報告日: 2026-08-12

## タイムライン

- [2026-08-12 ClickFix型攻撃が新種RAT「CNCMachineRMS」を配布 – 正規署名済みIBM SPSS IDEを悪用したBabaDeda系感染チェーン](../articles/2026-08-12-clickfix-cncmachinerms-rat.md)
