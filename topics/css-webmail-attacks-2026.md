# CSS Webメール攻撃「CSS: The Bomb Inside Your Inbox」（2026年）

## 概要

PortSwiggerの研究者Gareth Heyes氏がBlack Hat USA 2026で発表した、悪意あるメール内のCSSを悪用しWebメールの信頼されたUIを乗っ取る新種の攻撃研究。JavaScriptを使わずCSSのみで、開封追跡・UI乗っ取り・クリックのリダイレクト・偽サインインフォームによるパスワード窃取といった実際の攻撃チェーンをOutlook・Gmail・Fastmail・Proton Mail・Yahoo Mail・AOL Mail向けに構築した。

**同一性の判断に役立つ情報：**
- 研究者: Gareth Heyes（PortSwigger）
- 発表: Black Hat USA 2026、研究名「CSS: The Bomb Inside Your Inbox」
- 攻撃手法: CSSのみ（JavaScript不使用）でWebメールインターフェースに干渉
- 対象サービス: Outlook、Gmail、Fastmail、Proton Mail、Yahoo Mail、AOL Mail
- 主な攻撃例: 開封追跡、UI乗っ取り、クリックのリダイレクト、偽サインインフォームによるパスワード窃取
- 波及リスク: AIメールエージェントの誤解釈を誘発する可能性も指摘

## タイムライン

- [2026-08-10 新種のCSS攻撃、主要Webメールサービスの防御を突破しパスワード・トークンを窃取可能に](../articles/2026-08-10-css-webmail-attacks.md)
