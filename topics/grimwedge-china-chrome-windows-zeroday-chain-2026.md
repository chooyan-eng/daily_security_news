# UTA0560/APT31 Chrome-Windowsゼロデイ連鎖攻撃「GRIMWEDGE」NGO標的キャンペーン（2026年9月）

## 概要

中国系脅威アクター「UTA0560」（Volexity命名、キャンペーン名「BlueMoon」）が、2026年9月1日に複数のNGOへ標的型メールを送付し、米大学サイトの反射型XSS脆弱性を悪用して攻撃者インフラへリダイレクトさせるエクスプロイトチェーンを展開した事案。チェーンはCVE-2026-85046（Chrome V8 type confusion）→CVE-2026-87491（Chromeサンドボックス脱出）→CVE-2026-85880（Windows ALPC、コード注入）の3段構成で、最終的にバックドア「GRIMWEDGE」が投下される。同一チェーンは中国系別グループAPT31による「LONGTALE」展開にも使われた。GoogleおよびMicrosoftの修正は既に存在するが、Chromiumのオープンソースコミットが安定版Chromeへ反映されるまでの「パッチギャップ」期間を突いた攻撃である点が特徴。

**同一性の判断に役立つ情報：**
- 脅威アクター: UTA0560（Volexity命名）、APT31（別キャンペーンで同チェーンを使用）
- キャンペーン名: BlueMoon
- マルウェア: GRIMWEDGE（UTA0560）、LONGTALE（APT31）
- 悪用CVE: CVE-2026-85046（Chrome V8）、CVE-2026-87491（Chromeサンドボックス脱出）、CVE-2026-85880（Windows ALPC）
- 初期侵入経路: 米大学サイトの反射型XSS脆弱性
- 標的: 複数のNGO
- 攻撃観測日: 2026年9月1日

## タイムライン

- [2026-09-20 中国系APT、Chrome/Windowsゼロデイ連鎖でNGOを標的に「GRIMWEDGE」を展開](../articles/2026-09-20-grimwedge-china-chrome-windows-zeroday-chain-2026.md)
