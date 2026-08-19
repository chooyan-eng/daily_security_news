# Coca-Cola、Fairlifeへのランサムウェア攻撃でデータ窃取を確認 — Anubisが身代金拒否後にデータをリーク

- **日付**: 2026-07-28
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/07/28/coca-cola-fairlife-dairy-subsidiary-ransomware-attack/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/coca-cola-confirms-data-theft-in-fairlife-ransomware-attack/), [Tech Times](https://www.techtimes.com/articles/321777/20260728/coca-cola-refuses-ransom-anubis-leaks-fairlife-data-citrixbleed-opened-door.htm)
- **トピック**: [Anubisランサムウェアグループ（2026年）](../topics/anubis-ransomware-2026.md)
- **分類**: 続報

## 概要

Coca-Cola社は、傘下の乳製品子会社Fairlifeが受けたランサムウェア攻撃について、データ窃取があったことを正式に確認した。攻撃者はランサムウェアグループ「Anubis」で、Coca-Colaが身代金の支払いを拒否したため、盗んだデータをリークサイトで公開したと報じられている。侵入経路にはCitrixBleed系の脆弱性が利用されたとみられる。

## 詳細

Coca-Colaは2026年7月16日、Fairlifeの生産システムに対するランサムウェア攻撃について米SECへのForm 8-K提出を通じて開示していた。攻撃発生直後には米国内のFairlife製品の生産ラインが一時停止するなど、業務への実害も生じていた。今回7月28日の続報では、Coca-Colaがデータ窃取の事実を正式に確認したことが明らかになった。

攻撃を実行したのはRaaS（ランサムウェア・アズ・ア・サービス）グループ「Anubis」で、Coca-Colaが身代金交渉に応じず支払いを拒否したことを受け、Anubisは窃取したFairlife関連データをダークウェブのリークサイトで公開したと報じられている。侵入の足がかりとしては、Citrix NetScalerシリーズに繰り返し発見されているメモリ漏洩系脆弱性群「CitrixBleed」の系譜にあたる脆弱性が悪用された可能性が指摘されている。

Anubisは2024年12月に登場したRaaSグループで、2026年に入り医療・エンジニアリング・建設・プロフェッショナルサービスなど幅広いセクターへ攻撃を拡大し、年内累計35件以上の攻撃（うち米国医療機関17件）を確認済みだった。ファイル暗号化に加えてデータを完全に消去するワイパー機能を備える点が特徴で、大手消費財ブランドの子会社である食品・飲料製造業者を標的に含めたことで、同グループの標的範囲がさらに拡大していることを示す事例となった。
