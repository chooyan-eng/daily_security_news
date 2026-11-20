# 恐喝グループ「n0n」、Visa・Mastercard・JPMorganの顧客データをリーク——いずれも外部ベンダー経由、3社が11月19日に認める

- **日付**: 2026-11-20
- **出典**: [Cybersecurity Dive](https://www.cybersecuritydive.com/news/jpmorgan-visa-customer-data-leaked-third-party-hacks/875333/)
- **分類**: 関連

## 概要

JPMorgan Chase、Visa、Mastercardの3社は11月19日、サードパーティベンダーへの侵害により顧客データが露出したことを認めた。恐喝グループ「n0n」が犯行を主張しデータをリークしている。JPMorganはロイヤルティプログラム管理基盤由来とみられるマーケティングデータ（氏名・メールアドレス、約1.6万件）、Mastercardは特典プログラム参加者のメールアドレス、VisaはAPAC地域の委託先が対象。3社とも自社システムや決済網への影響は否定している。

## 詳細

### 各社の説明

- **JPMorgan Chase**: 攻撃者がアクセスしたのはマーケティングデータ（顧客氏名・メールアドレスを含む）とみられ、ロイヤルティプログラムを管理するプラットフォーム由来の可能性が高いと説明。Reutersの集計ではリークファイルに顧客メールアドレス16,000件超と行員のアドレス124件。資産1,000万ドル超の顧客向け招待制カード「Reserve」関連のデータとする報道もある。同週の同行のシステム障害とは無関係としている。
- **Visa**: アジア太平洋地域のサードパーティサービスプロバイダーに関する事案で、Visaのシステムやカード番号は侵害されていないと説明。Cybernewsはプレミアムカード顧客6,000人超が影響と報じている。
- **Mastercard**: ある特典（リワード/ベネフィット）プログラムの一部参加者のメールアドレスが限定的に露出。決済情報は含まれず、決済ネットワークへの影響なし。

### 攻撃者

- 恐喝/ランサムウェアグループ「n0n」が犯行を主張しデータを公開。
- 3社は侵害されたベンダー名を公表しておらず、共通の1社なのか別々のベンダーなのかも明らかにしていない。
- 件数等の一部は攻撃者がリークしたデータに基づくもので、真正性・全容は独立に検証されていない。銀行のパスワードが窃取された、資金にアクセスされたという確認情報はない。

### 技術的な補足

- 侵入手法は不明。対象がいずれも**ロイヤルティ/特典/マーケティング系の外部SaaS**である点が特徴で、決済本体と比べてセキュリティ要件が緩くなりがちな「周辺のWebサービス」が狙われる傾向を示している（同週のOptimizely事案、国内のKARTE事案とも共通する構図）。
- 漏えい情報は氏名・メールアドレスが中心だが、「富裕層向けカードの保有者」という属性付きリストは、標的型フィッシングやビジネスメール詐欺、SIMスワップ等の起点として価値が高い。
- 事業者側の対策: 委託先に渡すデータの最小化（メールアドレスのハッシュ化連携等）、委託先のアクセスログ・インシデント通知条項の整備、プログラム終了時のデータ削除確認。

### 参考

- [Cybernews: Visa confirms cyberattack as hackers claim JPMorgan was hit too](https://cybernews.com/security/visa-jpmorgan-data-breach/)
- [PYMNTS: Visa, Mastercard and JPMorgan Customer Data Leaked in Breach](https://www.pymnts.com/cybersecurity/2026/visa-mastercard-and-jpmorgan-customer-data-leaked-in-breach/)
- [Decrypt: Hackers Leak Visa, Mastercard and JPMorgan Customer Data](https://decrypt.co/383663/hackers-leak-visa-mastercard-jpmorgan-data)

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

- [ランサムウェアグループ「N0n」、ウズベキスタンの小売業向けPOS/バックオフィスソフト事業者を侵害と主張](../articles/2026-09-22-finsoft-kolibri-n0n-ransomware.md) - 同名の恐喝グループ「N0n」による、ソフトウェア/サービス提供事業者経由で顧客データを窃取・公開する同種の手口（同一グループかは未確認）
