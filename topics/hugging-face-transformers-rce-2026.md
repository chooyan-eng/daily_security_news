# Hugging Face Transformers RCE 脆弱性（CVE-2026-4372）

## 概要

Hugging Face Transformers ライブラリ（バージョン 4.56.0〜5.2.x）に発見された CVE-2026-4372。悪意ある `config.json` を持つ AI モデルを `from_pretrained()` API で読み込むだけで任意コードが実行される。`trust_remote_code=True` 設定も明示的なユーザー操作も不要で、AI/ML パイプラインのサプライチェーン攻撃を可能にする。Pluto Security の研究者 Yotam Perkal が発見し、修正版 5.3.0 は2026年3月リリース済み。脆弱なバージョンは約2億3200万回ダウンロードされた。

**同一性の判断に役立つ情報：**
- CVE: CVE-2026-4372
- 影響ライブラリ: Hugging Face Transformers 4.56.0〜5.2.x（+ kernels パッケージ使用時）
- 修正バージョン: 5.3.0（2026年3月リリース）
- 脆弱な期間: 2025年8月〜2026年3月（約6ヶ月）
- 発見者: Yotam Perkal（Pluto Security）
- 攻撃要件: `from_pretrained()` 呼び出しのみ（trust_remote_code 不要）

## タイムライン

- [2026-06-18 Hugging Face Transformers に RCE 脆弱性（CVE-2026-4372）：悪意ある AI モデルの読み込みで任意コード実行](../articles/2026-06-18-hugging-face-transformers-cve-2026-4372.md)
