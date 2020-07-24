---
title: "Betriebswirtschaftslehre - Rechnungswesen"
date: 2020-07-23T16:22:29+02:00
math: true
tags: ["BWL"]
---

这门课的目标：

nach Deutschland gültigen Rechnungslegungsstandards IFRS 和HGB 里实现BWL-FR 里介绍的Principal 和 Mehthods.

---

## 1. Einführung in Rechnungslegungstandards

__Reinvermögen__ zum Zeitpunkt $t\_0 :=R\_{t\_0} =$ Wert der Vermögensgegenstände zum Zeitpunkt $t\_0 -$ Wert der Schulden zum Zeitpunkt $t\_0$

__Erfolg__ der Periode $i := R\_{t\_i} - R\_{t\_{i-1}}$ 

__Gewinn__ des Rechnungswesens $=$ Erträge $-$ Aufwendungen

Aufbau des IFRS Rechnungslegungssystem:

<img src="/postImage/Rechnungswesen/IFRS.png" alt="IFRS Rechnungslegungssystem" width="500" class="center" />

__Realisationsprinzip__: 什么时候才实现了Umsätze(Erträge)？ -> 当交易所绑定的风险从A方转移到B方，例：完成了送货。

__Matching Prinziple__: 什么时候把交易产生的Aufwendung 记上账？ -> 和Gewinnberechnung 同时记。

---

## 2. Bewertung von Vermögensgegenständen

__Fair Value 公允价值__: 黑话就是市价，如果确定市价？ ->

1. 如果有的话，参照和本交易相同的Transaktion 的Marktpreis - mark-to-market。例：一栋楼的另一套房的交易金额。
2. 不行的话，参照和本交易大致相同且可比较的Transation，如两年钱的历史交易金额。
3. Parameter orientierend。

__Impairment Test 减值测试__
当市场存在该资产存在Wertminderungen 时，就是做减值测试的时候了。减值测试做出后的两个结果分别是：

1. __erzielbare Betrag (recoverable amount 可回收金额)__： 使用改资产能带来的收益
2. __Buchwert (carrying amount)__：直接出售该资产能带来的收益。

__Goodwill 商誉__： 商誉是收购一个公司会凭空产生的价值，换而言之就是信仰。例：一个公司把里面的门和电脑拆了能卖50块钱，那如果想收购这家公司就肯定不止花50元了，不然为啥不拆了卖？如果公司拆了卖值50元，那收购花了80 元，这其中多出了30元就为信仰充值了，所谓商誉+30。反过来就是Badwill

做完减值测试后，减值先虚后实，先从goodwill 开始减值。

<img src="/postImage/Rechnungswesen/ImpairmentTest.png" alt="Impairment Test" width="500" class="center" />

#### Langfristige Fertigungsaufträge 长期建造合同

当建造合同需要多年才能实现，那该如何才能记账？ -> 

1. __percentage of completion- Method__: Periodengewinnanteil = Leistungsfortschritt der Periode x erwarteter Auftragsgewinn:= 已知整个Projekt 的Gesamtertrag 和每个Periode 的Aufwand， 那么每个Periode Erlös 就是 Gesamtertrag/总Aufwand x 当前aufwand 占总aufwand 的比重。
2. __modifizierten completed contract-Methode__ 在项目结束前，每个Periode 的Erlös 最高只能是Aufwand 的高度。


---

## 3. Jahresabschluss 财务表表

#### Lagebericht

根据 HGB, Lagebericht 有以下的报表组成：

- Wirtschaftsbericht 经济报表
- Risiko- und Prognosebericht 风险和预测报表
- Nachtragsbericht 补充报表
- Bericht über die Finanzrisiken
- Forschungs- und Entwicklungsbericht
- Zweigniederlassungsberecht 分公司报表
- Vergütungsbericht 保持报表
- Bericht über die Übernahmesituation 收购情况报表
- Bericht über das interne Kontroll- und Risikomanagement

Komponenten des Eigenkapitals:
<img src="/postImage/Rechnungswesen/EK.png" alt="EK" width="500" class="center" />

资本增加：

例：curraxit 公司发行 100股股票，每股市值12元，而股票面值Nennwert(par value) 1元。那么股票一经发行 curraxit 就收的流动资金(Liquide Mittel) 1200元，其中已Gezeichnetes Kapital(发行股本) +100元，Kapitalrücklage(资本储备)+1100元。

---

## 4. Jahresabschlussanalyse: Liquidität (偿付能力)

#### Working Capital Requirement 运营资本需求

__WCR__ $=$ __Oprative Vermögenswerte__ $-$ __Operative Verbindlichkeiten__

__Operative Vermögenswerte__ 运营资本 = Forderungen aus Lieferungen und Leistungen + Vorräte + gezahlte Anzahlung + Aktive Rechnungsabgrenzungsposten

__Operative Verbindlichkeiten__ 运营债务 = Verbindlichkeiten aus Lieferungen und Leistungen + Sonstige Verbindlichkeiten für das operative Geschäft + erhaltene Anzahlung + Passive Rechnungsabgrenzungsposten

__Investiertes Kapital__ （投入资本）(Aktiva) = Zahlungsmittel + WCR + langfristige Vermögensgegenstände (+ ggf. nicht operative kurzfristige Vermögensgegenstände)

__Capital Employed(eingesetztes Kapital)__ （运用资本） (Passiva) = kurzfristige nicht operative Schulden + langfristige Schulden + Eigenkapital

#### Mathcing Stragie für das WCR

在Matching strategy 看来，permanente WCR （永久性运营资本）应作为长期投资来看，且应被长期资本支持。反过来 saisonale WCR（临时性运营资本）应被短期资本支持。 如果刚好这样做，叫做 Konservative Strategie，如果用更多的短期资本来支持长期WCR，就是Aggressive Strategie。

<img src="/postImage/Rechnungswesen/WCR.png" alt="WCR" width="500" class="center" />

__Net long-term Financing(NLF)__ = long-term Financing - langfristige Vermögenswerte = langfristige Schulden + EK - langfristige Vermögenswerte

__Net short-term Financing(NSF)__ = kurzfristige nicht operative Shulden - ZM

__Luquidity Ratio__ = (long-term Financing - langfristige Vermögenswerte)/WCR = NLF/WCR

总结： WCR - NLF = NSF

#### 如何增加Liquidität?

-> 增加Liquidity Ratio

* 增加long-term Financing
* 降低langfristigen Vermögenswerte
* 降低WCR

决定WCR 的因素有:

* 分公司的性质
* operative Zykus 的Effizienz
* Umsatz 的增长率

#### Effizienz

__WCR-to-Sales Ratio__ = $\frac{WCR}{Umsatz}$

__Umschlagshäufigkeit des Vorrats "Fertige Erzeugnisse und Waren(FE)"（库存周转率）__ $= \frac{Abgang.in.der.Periode}{Bestand.des.Vorrats.FE.am.Ende.der.Jahrespeiode}$

* Abgang in der Periode 以Umsatzkosten 来算

__Umschlagsdauer des Vorrats FE__ $= \frac{365Tage}{Umschlagshäufigkeit.des.Vorrats.FE}$

库存周转率越高，那么给vorrats 和WCR 的投入就越低，那么Operative Effizienz 就高。

__Lieferantenziel__ $= \frac{Verbindlichkeiten.aus.Lieferung.und.Leistungen.am.Ende.der.Jahresperiode * 365Tage}{Wareeingang}$

__Wareneingang__ $= Endbestand.an.Vorräten -  Anfangsbestand.an.Vorräten + Umsatzkosten - Fertigungskosten$

<img src="/postImage/Rechnungswesen/cash-to-cash.png" alt="cash-to-cash" width="500" class="center" />

#### Traditionelle Liquiditätsmaße

* __Net.Working.Capital__ $= Umlaufvermögen - kurzfristige.Schulden$
* __Liquidität 1. Grades__ (Barliquidität) $= \frac{ZM}{kurzfristige.Schulden}$
* __Liquidität 2. Grades__ (Liquidität auf kurze Sicht) $= \frac{monetäres.Umlaufvermögen}{kurzfristige.Schulden}$
* __Liquidität 3. Grades__ (Liquidität auf mittlere Sicht) $=\frac{monetäres.Umlaufvermögen + Vorräte}{kurzfristige.Schulden}$

---

## 5. Jahresabschlussanalyse: Rentabilität （盈利能力）

#### ROI Kennzahlensystem

##### Relative Kennzahlen

__ROS__ (Return on Sales, Umsatzrentabilität) = $\frac{Jahresüberschuss + Zinsaufwand + Steuern}{Umsatz} = \frac{EBITT}{Umsatz}$

__ROE__ (Return on Equity, Eigenkapitalrentabilität) = Jahresüberschuss/EK

__$ROIC\_{BT}$__ $= \frac{EBIT}{Investiertes Kapital} = \frac{EBIT}{Capital Employed}$