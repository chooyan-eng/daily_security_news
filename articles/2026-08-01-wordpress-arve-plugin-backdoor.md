# WordPressプラグイン「Advanced Responsive Video Embedder」にバックドア混入、約2万サイトが管理者権限乗っ取りの危険に（CVE-2026-18072）

- **日付**: 2026-08-01
- **出典**: [Hackread](https://hackread.com/wordfence-critical-backdoor-arve-wordpress-plugin/) / [Cyberpress](https://cyberpress.org/wordpress-plugin-backdoor-exposes-20000-sites/) / [ToolsLib Blog](https://blog.toolslib.net/2026/07/29/cve-2026-18072-arve-backdoor/)
- **トピック**: [WordPress ARVEプラグイン バックドア混入 CVE-2026-18072（2026年）](../topics/wordpress-arve-plugin-backdoor-cve-2026-18072.md)
- **分類**: 新規

## 概要

WordPress用動画埋め込みプラグイン「Advanced Responsive Video Embedder（ARVE）」バージョン10.8.7にサプライチェーン型のバックドアが混入していたことが判明した（CVE-2026-18072、CVSS 9.8）。約2万サイトが未認証での管理者アカウント乗っ取りのリスクにさらされた。

## 詳細

ARVEはYouTube・Vimeo・Rumble・Odysee・Kickなど各種動画サービスの埋め込みを支援する人気プラグインで、約2万件のアクティブインストールを持つ。今回確認されたのは典型的な脆弱性ではなく、正規のプラグイン配布物にステルスな認証バイパス機構が混入させられたサプライチェーン侵害である。

バックドアは、受信したリクエストパラメータの値を、プラグインコード内にハードコードされたハッシュ値と比較する仕組みになっており、値が一致すると既存の管理者アカウントを1つ選択し、そのユーザーとしてログイン済みセッションを確立する。これにより未認証の攻撃者が単一のHTTPリクエストだけで管理者権限を取得できた。

バックドアの実装は`_arve_uc_init()`という関数を通じて行われ、WordPressの初期化処理中に`init`フックで早期に実行される。悪意あるロジックは、一見無害な通常のプラグイン機能を装う「fn-update-check.php」というファイル名のファイルを通じて有効化されており、検知を逃れる工夫が凝らされていた。

WordfenceのAI駆動型脅威インテリジェンスプラットフォーム「PRISM」が、2026年7月28日の混入からわずか2時間以内に悪意あるコードを検知。WordPress.orgのプラグインチームは即座に当該プラグインのダウンロードを停止し、Wordfenceは同日中にプレミアムユーザー向けにファイアウォールルールを展開した（無料ユーザー向けの保護は2026年8月27日提供予定）。管理者には、プラグインの即時削除、WordPressセキュリティキーのローテーション、全管理者アカウントの監査、アクティブセッションの無効化、ファイル・データベースへの永続化痕跡の確認が強く推奨されている。
