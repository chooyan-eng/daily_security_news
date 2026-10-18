# npm Trusted Publishing「SlugFest」検証不備（1,500超パッケージ、2026年10月）

## 概要

Bloom Securityの研究により、npmのTrusted Publishingが信頼する発行元をリポジトリの可変な名前で検証していたため、放棄されたGitHubリポジトリ名を再取得した攻撃者が1,500超のパッケージの新版を公開できるおそれが判明した。10月2日に修正が適用された。実被害は未確認。

## タイムライン

- [2026-10-13 npm Trusted Publishingの検証不備「SlugFest」、1,500超のパッケージが乗っ取りリスクに](../articles/2026-10-13-npm-slugfest-trusted-publishing.md)
