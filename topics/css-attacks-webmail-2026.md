# CSS属性セレクタ悪用によるWebメール攻撃チェーン（2026年）

## 概要

PortSwiggerの研究者Gareth Heyes氏がBlack Hat USA 2026で発表した、メール本文内のCSSがWebメールのUI境界を越えて干渉できることを示す一連の攻撃チェーン。CSSミューテーション、属性セレクタ、`:before`・`:after`・`:has()`・`:checked` などの疑似要素を悪用し、JavaScriptを使わずにパスワード窃取・トークン漏洩・UIなりすましを実現する。Outlook、Gmail、Fastmail、Proton Mail、Yahoo Mail、AOL Mailが対象。

**同一性の判断に役立つ情報：**
- 発表者: Gareth Heyes（PortSwigger）
- 発表イベント: Black Hat USA 2026
- 対象サービス: Outlook, Gmail, Fastmail, Proton Mail, Yahoo Mail, AOL Mail
- 攻撃手法: CSSミューテーション、属性セレクタ、疑似要素（:before/:after/:has()/:checked）の悪用
- 修正状況（2026年8月8日時点）: Fastmail・Proton Mailは一部修正済み、Outlook・Gmailは未修正の攻撃チェーンあり

## タイムライン

- [2026-08-08 新型CSS攻撃、主要Webメールの防御を突破しパスワード・トークンを窃取可能に](../articles/2026-08-09-css-attacks-webmail-passwords-tokens.md)
