# npm keyv/cacheable サプライチェーン攻撃「Mini Shai-Hulud」（2026年8月）

## 概要

2026年8月4日、npmの人気キャッシュパッケージ群（keyv、cacheable等）のメンテナーJared Wray氏（jaredwray）のGitHubアカウントが乗っ取られ、月間20億ダウンロード超の9コアパッケージに認証情報窃取マルウェア（クレデンシャルスティーラー）を仕込んだ悪意あるバージョンが公開された。ワーム的な自動連鎖により下流パッケージにも波及し、影響パッケージ数は約400〜2,200件超。Wizは攻撃者を「Mini Shai-Hulud」ファミリーに帰属。

**同一性の判断に役立つ情報：**
- 侵害日: 2026年8月4日
- 侵害対象: npmメンテナー Jared Wray（jaredwray）のGitHubアカウント
- 直接侵害パッケージ: keyv, cacheable-request, cache-manager, @cacheable/utils, flat-cache, file-entry-cache, cacheable, @cacheable/memory, @cacheable/node-cache（計9パッケージ、月間20億+DL）
- マルウェア: preinstallフック経由の難読化ローダー→クレデンシャルスティーラー（npm/GitHub/AWS/HashiCorp Vault認証情報窃取）
- 攻撃者ファミリー帰属（Wiz）: Mini Shai-Hulud（TeamPCP・@antvキャンペーンとの類似性を指摘、同一犯行と断定はせず）
- 影響規模: 約400〜2,200件超のパッケージ・成果物

## タイムライン

- [2026-08-06 npmの人気キャッシュパッケージ keyv・cacheable がサプライチェーン攻撃で侵害、メンテナーアカウント乗っ取りから拡散](../articles/2026-08-06-npm-keyv-cacheable-mini-shai-hulud-2026.md)
