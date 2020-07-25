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

__WCR__ $= Oprative.Vermögenswerte - Operative.Verbindlichkeiten$

__Operative Vermögenswerte__ 运营资本 $= Forderungen.aus.Lieferungen.und.Leistungen + Vorräte + gezahlte. Anzahlung + Aktive.Rechnungsabgrenzungsposten$

__Operative Verbindlichkeiten__ 运营债务 $= Verbindlichkeiten.aus.Lieferungen.und.Leistungen + Sonstige.Verbindlichkeiten.für.das.operative.Geschäft + erhaltene.Anzahlung + Passive.Rechnungsabgrenzungsposten$

__Investiertes Kapital__ （投入资本）(Aktiva) $= Zahlungsmittel + WCR + langfristige.Vermögensgegenstände (+ ggf. nicht.operative.kurzfristige.Vermögensgegenstände)$

__Capital Employed__(eingesetztes Kapital) （运用资本） (Passiva) $= kurzfristige.nicht.operative.Schulden + langfristige.Schulden + Eigenkapital$

__Finanzschulden__ = IK - EK

#### Mathcing Stragie für das WCR

在Matching strategy 看来，permanente WCR （永久性运营资本）应作为长期投资来看，且应被长期资本支持。反过来 saisonale WCR（临时性运营资本）应被短期资本支持。 如果刚好这样做，叫做 Konservative Strategie，如果用更多的短期资本来支持长期WCR，就是Aggressive Strategie。

<img src="/postImage/Rechnungswesen/WCR.png" alt="WCR" width="500" class="center" />

__Net long-term Financing(NLF)__ $= long.term.Financing - langfristige.Vermögenswerte = langfristige.Schulden + EK - langfristige.Vermögenswerte$

__Net short-term Financing(NSF)__ $= kurzfristige.nicht.operative.Shulden - ZM$

__Luquidity Ratio__ $= \frac{long.term.Financing - langfristige.Vermögenswerte}{WCR} = \frac{NLF}{WCR}$

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

__Lieferantenziel__ $= \frac{Verbindlichkeiten.aus.Lieferung.und.Leistungen.am.Ende.der.Jahresperiode \times 365Tage}{Wareeingang}$

__Wareneingang__ $= Endbestand.an.Vorräten -  Anfangsbestand.an.Vorräten + Umsatzkosten - Fertigungskosten$

<img src="/postImage/Rechnungswesen/cash-to-cash.png" alt="cash-to-cash" width="500" class="center" />

#### Traditionelle Liquiditätsmaße

* __Net.Working.Capital__ $= Umlaufvermögen - kurzfristige.Schulden$
* __Liquidität 1. Grades__ (Barliquidität) $= \frac{ZM}{kurzfristige.Schulden}$
* __Liquidität 2. Grades__ (Liquidität auf kurze Sicht) $= \frac{monetäres.Umlaufvermögen}{kurzfristige.Schulden}$
* __Liquidität 3. Grades__ (Liquidität auf mittlere Sicht) $=\frac{monetäres.Umlaufvermögen + Vorräte}{kurzfristige.Schulden}$

---

## 5. Jahresabschlussanalyse: Rentabilität （盈利能力）

### ROI Kennzahlensystem

#### Absolute Kennzahlen

__EAT__ (Earnings After Tax) := Jahresüberschuss

__EBT__ (Earnings Before Tax) := EAT + Steuern

__EBIT__ (Earnings Before Interest and Tax) := EBT + Finanzergebnis (Finanzergebnis = Zinsaufwand - Zinsertrag)

__EBITA__ (Earnings Before Interest, Tax and Mortization) := EBIT + Abschreibungen auf immaterielle Vermögenswerte und Impairment Loss

__EBITDA__ (Earnings Before Interest, Tax, Amortization and Depreciation) := EBITA + Abschreibungen auf Sachanlagen

#### Relative Kennzahlen

__ROS__ (Return on Sales, Umsatzrentabilität) = $\frac{Jahresüberschuss + Zinsaufwand + Steuern}{Umsatz} = \frac{EBITT}{Umsatz}$

__ROE__ (Return on Equity, Eigenkapitalrentabilität) = Jahresüberschuss/EK

__ROBA__ (Return on bussiness assets)$=\frac{EBIT}{WCR + langfristige.Vermögenswerte}$

__ROTA__ (Return on total assets) $= \frac{EBIT}{Alle.Vermögenswerte}$

__$ROIC\_{BT}$__ $= \frac{EBIT}{Investiertes Kapital} = \frac{EBIT}{Capital Employed}$


<img src="/postImage/Rechnungswesen/ROI.png" alt="cash-to-cash" width="700" class="center" />

#### ROE Kennzahlensystem

__Financial Cost Ratio__ $=\frac{EBT}{EBIT}$

__Financial Structure Ratio__ $=\frac{Investiertes.Kapital}{EK}$

__Financial Leverage Multiplier__ $Financial.Cost.Ratio * Financial Structure Ratio$

__Tax-Effect Ratio__ $=\frac{Jahresüberschuss}{EBT} = 1-effektiver.Steuersatz$ 

$$ROE = \frac{Jahresüberschuss}{EK}
$$
$$=\frac{EBIT}{Umsatz} \times\frac{Umsatz}{Investiertes Kapital}\times\frac{EBT}{EBIT} \times\frac{IK}{EK}\times \frac{Jahreüberschuss}{EBT}$$
$$=ROIC\_{BT}\times Financial.Cost.Ratio\times FinancialStructure.Ratio \times Tax.Effect.Ratio 
$$
$$=ROIC\_{BT}\times Financial.Leverage.Multiplier\times(1-effektiver.Steuersatz)
$$

<img src="/postImage/Rechnungswesen/ROE.png" alt="ROE" width="700" class="center" />


## 6.Steuern im externen Rechnungswesen

__Umsatzsteuer__ 周转税：周转税是按商品生产或销售量的流转额征收的一种税。周转税的征税对象是生产、销售或采购商品的流转额。周转税的纳税人是从事生产和销售商品的销售组织。

__Mehrwertsteuer__ 增值税： 增值税是对生产经营活动的增值额征收的一种间接税或是以商品在流转过程中产生的增值额作为计税依据而征收的一种流转税。

__Latente Steuern__ 递延所得税: 自己的帐和工商局做的帐，对如Abschreibung 类的算法时间上的延误，而列出的“提前税”。


<img src="/postImage/Rechnungswesen/latente.png" alt="latente" width="700" class="center" />


## 7.Bilanzpolitik und Compliance (收支平衡的政策和合规)

## 8.Geshäftsbericht und Investor Relations

## 9. Unternehmensbewertung

#### CAPM (Capital Asset Pricing Models)

$$
k\_e = r+(\mu\_M -r)\times \beta
$$

wobei:

$r$ =: Rendite der sicheren Anlage

$\mu\_M$ =: die erwartete Rendite des Marktporfolies

$\beta$ das Beta der Aktie

__WACC__ (Weighted Average Cost of Capital, Gesamtkapitalkostensatz) $=\frac{EK}{EK+FS}\times k\_e + \frac{FS}{EK+FS}\times k\_f \times (1-s)$

wobei:

$FS$ =: Finanzschulden

$k\_f$ =: Fremdkapitalkostensatz

$k\_e$ =: Eigenkapitalkostensatz

$s$ =: Marginaler Steuersatz

#### Economic Value Added

__NOPAT__ (Net Operating Profit After Tax) = Jahresüberschuss + Zinsaufwand x (1-s)

__EVA__ (Economic Value Added) = NOPAT - WACC x Capital Employed 

<img src="/postImage/Rechnungswesen/eva.png" alt="eva" width="700" class="center" />

#### Marktwertbasierte Kennzahlen

__EPS__(Earnings per share, Gewinn je Aktie) $=\frac{Jahresüberschuss}{Durchschnittliche Anzhal der Aktien} = \frac{Jahresüberschuss}{\frac{Durchschnittlisches gezeichnetes Kapital}{Nennwert je Aktie}}$

__KGV__ (Kurs-Gewinn-Verhältnis, price-to-earnings ratio) $= \frac{Preis.je.Aktie}{EPS}$

__Dividendenrendite__ $= \frac{Devidende.je.Aktie}{Preis.vor.Dividendenzahlung.je.Aktie}$

__Market-to-Book Ratio__ $=\frac{Preis.je.Aktie}{Buchwert.des.Eigenkapial.je.Aktie}=\frac{Preis.je.Aktie}{\frac{Buchwert.des.Eigenkapitals}{Anzahl.der.Aktien}}$

#### EBIT-Multiple

__EBIT-Multiple__ $=\frac{Enterprise.Value}{EBIT} =\frac{Marktwert.des.EK + Netto - FS}{EBIT} = \frac{Martwert.des.EK + FS - ZM}{EBIT} = \frac{1}{i-g}$

__g__ (Geometrisch-durchschnittliche Wachstumsrate) $=\sqrt[n]{\frac{EBIT\_n}{EBIT\_0}} -1 = i-\frac{EBIT}{Enterprise.Value}$

__Enterprise.Value__ $=\frac{EBIT}{i-g}$


wobei:

i := risikoadäquate Kapitalkostensatz

#### Aktienbewertung

Aktienrendite $=\frac{Div\_1}{P\_0}+\frac{P\_1 - P\_0}{P\_0}= \frac{Div\_1 + P\_1}{P\_0} - 1$ = Dividendenrendite + Rendite aus Kursveränderung

##### DDM (Dividend Discount Model)

$P\_0 = \frac{Div\_1+P\_1}{1+r\_E}$ ,wobei $r\_E$ ist Diskontierungssatz

$P\_1 = \frac{Div\_2+P\_2}{1 + r\_E}$

damit haben wir

$P\_0=\frac{Div\_1}{1+r\_E}+\frac{1}{1+r\_E}(\frac{Div\_2+P\_2}{1+r\_E})=\frac{Div\_1}{1+r\_E}+\frac{Div\_2+P\_2}{(1+r\_E)^2}$


$P\_0 = \frac{Div\_1}{1+r\_E}+\frac{Div\_2}{(1+r\_E)^2}+\frac{Div\_3}{(1+r\_E)^3}+\dots =\sum^\infty\_{t=1}\frac{Div\_t}{(1+r\_E)^t}$