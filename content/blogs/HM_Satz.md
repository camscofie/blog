---
title: HM Sätze Interpretation 
description: Höhere Mathematik
date: 2019-08-29T22:41:21+02:00
tags: ["math","further mathematics"]

---
## Eindimensionale Analysis

### 1. Zahlen
--------------
#### Axiome der reellen Zahlen
* Sei M ⊂ R, M ≠ ∅: M heißt **nach oben beschränkt**: ⇔ ∃γ∈R, ∀x∈M, x≤γ. In diesem Fall heißt γ **obere Schranke(untere Schranke analog)** von M.
* Ist γ eine obere Schranke von M und gilt für jede weitere obere Schranke ñ von M : γ ≤ ñ, (d.h. γ ist kleinste obere Schranke von M), so heißt γ das **Supremum(Inﬁmum analog)** von M.
* Existiert sup M und gilt sup M ∈ M, so heißt sup M auch **Maximum(Minimum analog)** von M
* M heißt beschränkt, wenn M nach oben **und** nach unten beschränkt ist.
  
### 2. Folge, Konvergenz
--------------

#### Häufungswert
* Sei (a n ) eine reelle Folge und (n 1 , n 2 , n 3 , . . .) eine Folge in N mit n 1 < n 2 < n 3 . . . Setze ∀k∈N, bk := ank, Die Folge (bk) heißt dann Teilfolge von (a n ).
* Sei (a n ) eine reelle Folge und a ∈ R. a heißt Häufungswert von (a n ), wenn eine Teilfolge (a n k ) von (a n ) existiert mit a n k → a für k → ∞. HW(a n ) := {a ∈ R : a ist Häufungswert von (a n )}
* Limes superior（lim sup） 是最大的HW，Limes inferior（lim inf） 是最小的HW，Supremum(sup) 是上限，Infimum（inf）下限

**言辞**：如果有一个an 的teilfolge 在a 点收敛，则a 点是一个极限点。*如果一个序列有多个极限点，那么它离散。*

#### Cauchy-Kriterium
* Eine Folge (a n) heißt eine Cauchy-Folge, wenn gilt: ∀ε > 0 ∃ñ ∈ N ∀n, m ≥ ñ │(a)n − (a)m│ < ε
  
**言辞**: 序列 An 叫做 Cauchy-Folge：对于任意小的一个非负数ε, 都有一个阈值ñ,任何大于ñ 的n 和m 的距离都小于ε。

* (Cauchy-Kriterium). (a n) konvergent ⇔ (a n) Cauchy-Folge.
  
**言辞**: cauchy-folge 会无限的渐进某个点。

### 3. Reihen
-----------------

#### 四个要记住的Reihen
+ geometrische Reihe: sum(x^n,n=0->∞) konvergiert <=> sum(x^n,n=0->∞)=1/(1-x) und │x│<1
+ harmonische Reihe: sum(1/n,n=1->∞) ist divergiert

#### Monotoniekriterium
* sn nach oben beschränkt. Dann ist die Reihe konvergent.
#### Cauchy-Kriterium 
* Eine Reihe (sn) ist konvergent: ∀ε > 0 ∃ñ ∈ N ∀n, m ≥ ñ m > n │sum(ak,k=n -> m)│ <ε
#### absolut konvergent
* sum(ak) heißt absolut konvergent :⇔ sum(│ak│) konvergent.  
* Ist sum(ak) absolut konvergent, so ist (ak) konvergent. (Die Umkehrung ist falsch).

### 4. Potenzreihen
---------------
#### Konvergenzradius
* Eine Reihe der Form: sum(an*(x-x0)^n,n=0->∞) = a0+a1(x1-x0)+a2(x2-x0)^2+... heißt Potenzreihe
* Konvergenzradius r:= sup{│x-x0│ │sum(an*(x-x0)^n,n=0->∞) konvergiert}
* Sei cn := root(│an│,n) , n ∈N
* r:= 0 , falls cn unbeschränkt
* r:= ∞ , falls cn ->0
* r:= (1/lim sup cn), falls cn beschränkt und lim sup cn > 0
**言辞**:收敛半径是所有收敛的Potenzreihe，中│x-x0│的最大值。


### 7. Stetige Funktionen
-------------------
#### Stetigkeit
* f ist stetig in x0 ⇔ lim f(x) = f(x0)， x0 ∈ Häufungspunkt
* f ist stetig in x0 :⇔ ∀ε > 0 ∃δ > 0 ∀x ∈ D,│x − x0│ < δ ⇒ f(x) − f(x0)<ε

**言辞**：function 在 x0 连续：f(x)和f(x0)无论有多相近，都有 x 无限接近于 x0。

#### Kompakte Mengen
* f:D → R heißt beschränkt: ⇔ f(D) ist beschränkt (⇔ ∃C > 0 ∀x ∈ D:│f(x)│ ≤ C)
* D ⊂ R heißt abgeschlossen lim x n ∈ D: ⇔ für jede konvergente Folge (xn) in D gilt: lim(xn,n→∞)∈D
* D ⊂ R heißt kompakt: ⇔ D ist beschränkt und abgeschlossen.

#### Gleichmäßige Stetigkeit
* f:D → R heißt gleichmäßig stetig auf D, wenn gilt:∀ε > 0 ∃δ > 0 ∀x, z ∈ D : │x − z│ < δ ⇒│f(x) − f(z)│  < ε

**言辞**: 一致连续（均匀连续）是指对于函数 f 我们只要在定义域中让任意两点 x 跟 y 距离小于δ，那么f(x)和f(y)距离就小于ε:**f(x)和f(y)之间的距离不依赖x 和y 的位置选择**， 所以更为平滑。

#### Lipschitz–Stetigkeit
* f:D → R heißt Lipschitz-stetig auf D, wenn ein L ≥ 0 existiert mit ∀x, z ∈ D : f(x) − f(z)  ≤ L│x − z│

**言辞**： Lipschitz–Stetigkeit 比一致连续更加光滑： *函数的斜率，必小于一个称为利普希茨常数的实数*

### 8. Funktionenfolgen und –reihen
-------------------
#### Punktweise Konvergenz
* Die Funktionenfolge (f n ) bzw. -reihe f n heißt punktweise konvergent auf D, wenn  P ∀x ∈ D(fn(x)) konvergent bzw. ∀x ∈ D(Sum(fn(x))) konvergent

**言辞**: 逐点收敛是数学中描述一组函数序列向一个函数趋近的一种方式，指在函数序列/极数在定义域中每点的取值都会趋于一个极限值。这个函数f(x) 和s(x) 叫做Grenzfunktion bzw. Summenfunktion.

#### Gleichmäßige Konvergenz
* ∀ε > 0 ∃ñ ∈ N ∀n ≥ ñ ∀x ∈ D : │fn(x) − f(x)│ < ε

**言辞**：对于超过阈值ñ 的所有n，fn(x)都在ε-schlauch 之内。 一致收敛是一个加强版的逐点收敛，保证了fx(x) 与f(x)大致相同的收敛速度以及**连续性**。

### 9.Diﬀerentialrechnung
---------------------
#### diﬀerenzierbar
* lim[((fx)-(fx0))/(x-x0),x->x0] existiert und _.≠ ∞

**言辞**：当x距离x0无限近时，x和x0 和斜率不是无限大或者无限小。（只有离散时斜率可以无限大）

#### Mittelwertsatz der Diﬀerentialrechnung
* f : [a, b] → R sei stetig auf [a, b] und diﬀerenzierbar auf (a, b). Dann existiert ein ξ ∈ (a, b) mit f(ξ) = (f(b)-f(a))/b-a

**言辞**：给定平面上固定两端点的可微曲线，则这曲线在这两端点间至少有一点，在这点该曲线的切线的斜率等于两端点连结起来的直线的斜率

## Mehrdimensionale Analysis, Diﬀerentialgleichungen, Transformationen
