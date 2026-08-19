# デバイスコードフィッシング / AiTM セッショントークン窃取（2026年）

## 概要

OAuth 2.0 デバイス認証フロー（Device Authorization Grant）を悪用してセッショントークンを直接窃取し、パスワードや MFA を回避する AiTM（Adversary-in-the-Middle）攻撃手法。2026年6月に37倍の検出スパイクを記録し、18種類のフィッシングキットが登場、すべての主要 AiTM プラットフォームが採用したことで犯罪エコシステムへのコモディティ化が確認された。Microsoft 365・Azure AD・Google Workspace 等のクラウドプラットフォームが主な標的。

**同一性の判断に役立つ情報：**
- 攻撃手法: OAuth 2.0 Device Authorization Grant 悪用
- 通称: デバイスコードフィッシング、AiTM Device Code Attack
- 標的: Microsoft 365、Azure AD、Google Workspace 等
- 2026年6月の検出増加率: 37倍
- FBI 警告発出日: 2026年5月21日
- Telegram での販売価格: 月約 $250〜
- 主要ツール/フレームワーク: AiTM キット各種（名称非公開）
- 効果のない防御: パスワード強化・TOTP MFA・SMS MFA・パスキー

## タイムライン

- [2026-06-29 デバイスコードフィッシング 完全なコモディティ化 — 18キット・37倍スパイク・全主要AiTMベンダーが採用](../articles/2026-06-29-device-code-phishing-criminal-commodity.md)
- [2026-06-21 デバイスコードフィッシング（AiTM）が2026年6月に37倍急増 — MFA を無効化するクリミナルコモディティ化](../articles/2026-06-21-device-code-phishing-aitm-37x-spike.md)
