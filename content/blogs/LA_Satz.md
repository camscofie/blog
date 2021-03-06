---
title: "LA Sätze Interpretation"
description: "Linearen Algebra"
date: 2019-09-20T22:41:21+02:00
tags: ["math","linear algebra"]
---

## III.Vektorräume
--------------------------------
### 7 Basis und Dimension von Vektorräumen
---------------
Eine Teilmenge B eines Vektorraumes V heißt Basis von V , wenn sie erzeugend und linear unabhängig ist.

**解读**： 所谓一个线性空间的basis，就是一组vektor。这组vektor 满足erzeugend 和linear unabhängigkeit 的关系。

#### 7.3 Basisdarstellung und Basiswechsel
Sei V ein n-dimensionaler -Vektorraum und B = {b1,..,bn} eine Basis von V. Nach der Deﬁnition einer Basis als linear unabhängiges Erzeugendensystem hat jeder Vektor v ∈ V eine Basisdarstellung

+ v = sum(vi*bi,i=1→n)

**言辞**： Basisdarstellung 就是用basis 来表示一个vektor。vi 是 bi 的Koeffizienten, 即需要多少个bi。

Die Koeffizienten v1,...,vn ∈ K heißt **Komponenten** von v in der Basis B. Der **Komponentenvektor** von v bezüglich B ist das n-Tupel ΘB(v) := (v1,..,vn)∈K^n

### 8.1 Untervektorräume
----------------

### Faktorräume (商空间)
-------------------------------
Sei U ein UVR eines Vektorraumes V. Die Menge der Aquiv¨ lenzklassen von V bez¨uglich der durch U definierten Aquiv¨alenzrelation ~ heisst **Faktorraum** oder **Quotientenraum** und wird mit V/U bezeichnet. Die Elemente ˜x ∈ V/U haben die folgende Form:
+ ~x = {x+u, u∈U} =: x+U

Sei V ein K-Vektorraum U ⊂ V ein Untervektorraum. Dann ist der Faktorraum V/U ein K-Vektorraum mit der folgenden Addition und skalaren Multiplikation
+ ~x + ~y := ~(x+y)
+ λ * ~x = ~(λx)
fuer x,y ∈ V, K∈K

**解读**：所谓商空间，即 K域 上的一个线性空间V 坍塌与其下的一个子空间U。我们在 V 上定义一个等价类~
+ 如果x-y∈U，则x~y

## IV. Lineare Abbildungen und Matrizen（线性变换）
-------------------
### Lineare Abbildungen
V und W seien K-Vektorräume. Eine Abbildung Φ: V→W heißt **linear**, wenn für alle x,y ∈ V und alle λ ∈ K gilt:
+ Φ(x+y) = Φ(x) + Φ(y)
+ Φ(λx) = λΦ(x)

**解读**：
所谓一个在向量空间的的映射是线性的，是指这个映射满足Homomorphismus 的关系。

#### lineare Fortsetzung
Sei V ein K-Vektorraum und {v1,...,vn} eine Basis von V. Weiter seien w1,...,wn beliebig vorgegebene Vektoren eines K-Vektorraumes W. Dann gibt es genau eine lineare Abbildung Φ: V→W mit 
+ Φ(vi) = wi, i =1,2,...,n

**言辞**：对一组给定的V 空间里的basis {v1,...,vn} 和任意的一组W 空间里的向量 w,...,wn。都有且只有一种线性变换满足Φ(vi)=wi 的映射关系。

**Hilfsatz**:
1. 在 Φ: V→W 中，如果{v1,..,vk} 是线性相关，那么 {Φ(vi)} 必然线性相关。
2. 如果 Φ: V→W 是injektiv, 那么如果{vi} 线性无关，那么{Φ(vi)}也线性无关。

### Kern und Bild einer linearen Abbildung
---------------
+ **KernΦ: = {v∈V,phi(x) = 0}**
+ der Kern einer Linearen Abbildung phi: V->W ist ein Untervektorraum von V
+ Eine lineare Abbildung phi: V->W ist genau dann **injektiv**, wenn Kern phi = {0} ∈ V
+ **Bildraum**: Bild phi = phi(V)
+ **Menge aller Urbilder**: phi^(-1) (w) := {x∈V,phi(x)=W}

**Hilfsatz**:
1. Zwei Vektoren x,y ∈ V haben genau dann dasselbe Bild unter phi, wenn x-y ∈ Kern phi
2. die Menge aller Urbilder von w ∈ Bild phi ist eine Nebenklasse im Faktorraum V/Kern phi:
    + Φ^(−1)({w}) = x + KernΦ für ein x ∈ V, f¨ur das gilt Φ(x) = w.

**解读**：所有Urbild 元素组成的集合，是 W/kern Φ 的一个商空间。根据商空间的定理，所有不同urbild元素相加，都会是商空间里的另一个元素。而所有相加等于0 的不同元素，都崩塌在了Kern phi 里了。

Sei Φ : V →W eine lineare Abbildung. Als **kanonische Projektion** (zu Φ) bezeichnet man die Abbildung
+ π : V → V/KernΦ, x → ~x,
  die jedem Vektor v seine Aequivalenzklasse in V/kern phi zuordnet.

**Homomorphiesatz**: Es sei phi: V->W eine lineare Abbildung. Dann ist
+ ~phi: V/Kern Φ ->W, ~x -> Φ(x)
eine injektive lineare Abbildung und es gilt phi = ~Φ * π 

**言辞**：Homomorphiesatz 意指，一个linear Abbildung 其实可以分解为两部，首先是一个kanonische Projektion 让V 崩塌成为一个商空间，在以injektiv 的模式把商空间映射到 线性空间W 上去。


##### Rang einer linearen Abbildung
der **Rang** einer linearen Abbildung phi: V->W ist die Dimension des Bildraumes von phi, also
+ Rang Φ := dim Φ(V) = dim Bild(Φ)
+ Rang Φ = dim V - dim Kern Φ
+ Eine lineare Abbildung Φ: V->W ist genau danninjektiv, wenn Rang Φ = dim V
+ Eine lineare Abbildung Φ: V->W ist genau dann surjektiv, wenn Rang Φ = dim W

#### Der Vektorraum Hom(V,W)
Es seien Φ, Ψ ∈ Hom(V,W) und λ ∈ K. Die **Summe** von Φ und Ψ ist die Abbildung
+ Φ + Ψ:= V -> W; v-> (Φ + Ψ)(v) := Φ(v) + Ψ(v)
+ λΦ = V -> W; v -> (λΦ)(v) := λΦ(v)
+ dim Hom(V,W) = dimV*dimW

### 10.Darstellungen von linearen Abbildungen durch Matrizen
---------------------------

#### 10.1 Abbildungsmatrizen
A =(a mn) eine m x n-Matrix, die man als Abbildungsmatrix von Φ bezüglich der Basen B,C bezeichnet. 
+ In der k-ten Spalte von A stehen die Komponenten von Φ(bk) bezüglich der Basis C gemäß

**解读**：现在在V 空间有basis B = {b1,b2,..,bn},想要得到W 空间的basis C = {c1,...,cn}。有Φ(bk)=sum(aik*ci,i=1 ->m),之后我们在做线性变换时。就可以用matrix A 来从一个basis B表示的vektor 换成basis C 表示的vektor。ΘC(y) = A *ΘB(x); Φ:K^n → K^m,x→Ax。我们把A 叫做Φ 的Darstellungsmatrix

In einem -Vektorraum V der Dimension n sei eine geordnete Basis B und in einem -Vektorraum W der Dimension m sei eine geordnete Basis C gewählt. Weiter sei
+ M(BC) : Hom(V,W) → K^(mxn), Φ → A=M(BC)(Φ)

die Abbildung die jedem Homomorphismus Φ: V →W die Abbildungsmatrix A ∈K^(mxn) bzgl. B,C gemäß zuordnet. Dann ist M(BC) bijektiv.

**解读**：M(BC) 是一个把任何在Hom(V,W) 空间里的元素投影到一个Abbildungsmatrix 的 映射，这个映射是bijektiv 的。

#### 10.2 Basiswechsel für Homomorphismen
**意义**：已有 Φ:V→W; B ={b1,..,bn}; C = {c1,..,cn} 和一个Abbildungsmatrix  A := M(BC)(Φ)。现在找了一组新的basen ~B 和~C， 如果找一个新 ~A？

+ M(~B~C)(Φ) = M(c~c)(idW) * M(BC)(Φ) * M(~BB)(idv)

叫做Basiswechselformel。

+ Zwei Matrizen A,~A ∈ K^(mxn) heißen **äquivalent**, wenn es invertierbare Matrizen S ∈ K^(nxn) und T ∈ K^(mxm) gibt mit ~A = TAS
+ Zwei Matrizen A,~A ∈ K^(nxn) heißen **ähnlich**, wenn es eine invertierbare Matrix T ∈ K^(nxn) gibt mit ~A = TAT^(-1)


## V. Endomorphismen (自同态)
--------------------
### Determinanten
--------------------
Es sei σ ∈ S n eine Permutation der Zahlen 1,2,..,n mit Fehlstandszahl F(σ). Das Signum von σ ist dann deﬁniert durch
+ sign σ :=(-1)^(F(σ))

**解释**：σ 为置换的奇偶性，偶数个反向对则定义为正1。

+ A ist regulär ⇐⇒ det A != 0

### Eigenwerte und Eigenvektoren
----------------
Es seien V ein K-Vektorraum und Φ: V → V ein Endomorphismus. Der Skalar λ heißt **Eigenwert** von Φ, falls ein Vektor x∈V mit x != 0 existiert, so dass:
+ Φ(x) = λx oder, äquivalent, (Φ-λidv)(x) = 0

gilt. Der Vektor x heißt **Eigenvektor** von Φ zum **Eigenwert** λ. 

Die Menge aller Eigenvektoren von Φ zu einem festen Eigenwert λ bildet zusammen mit dem Nullvektor einen Untervektorraum von V. Er heißt der zu λ gehörige **Eigenraum** von Φ und wird mit Eλ bezeichnet. Die Menge aller Eigenwerte von Φ heißt **Spektrum** von Φ. 

**解读**：
Φ 是一个线性变换，实际上就是一个矩阵A。这个变换呢，在某些vector 的时候，它并不改变vector 空间方向，只是其Skalar。

对于每个给定的Skalar ，都和其所有的特征向量和null vector 组成一个线性子空间，称作**特征空间**，所有特征向量的集合，称作**谱**

+ Φ(v) = λv ⇐⇒ Φ(v) - λv = 0 ⇐⇒ (Φ - λ*IdV)(v) = 0 ⇐⇒ v ∈ Kern(Φ- λIdV)
+ Eig(Φ,λ) := Kern(Φ - λ*IdV)


#### Berechnung der Eigenwerte: charakteristischess Polynom (特征多项式)
Das charakteristische Polynom Xa einer quadratischen nxn-Matrix A mit Einträgen aus einem Körper K wird definiert durch:
+ Xa(λ) := det(λEn - A)

Hierbei bezeichnet En die n-dimensionale Einheitsmatrix und det die Determinante. Die Unbestimmte λ steht ebenfalls für ein Element von K. 

**解读**：CP 是用来计算特征值的，因为特征值刚好是CP 的Nullstellen。

以下的几点相等：
+ λ ist ein Eigenwert von A
+ Es gibt ein x ∈ K^n, x!=0 mit Ax=λx
+ (λE - A)x = 0
+ λE - A ist nicht invertierbar
+ det(λE - A) = 0
+ λ ist Nullstelle des charakteristischen Polynoms von A

CP 有以下性质：
+ Die charakteristischen Polynome zweier ähnlicher Matrizen sind gleich. Die Umkehrung ist jedoch im Allgemeinen nicht richtig
+ Die Matrix A und ihre Transponierte besitzen das gleiche charakteristische Polynom

### 14. Diagonalisierbare Endomorphismen (可对角化)
-----------------------

Eine quadratische Matrix A ∈ K^(nxn) heißt **diagonalisierbar**, wenn sie zu einer Diagonalmatrix **ähnlich** ist. Ein Endomorphismus Φ heißt **diagonalisierbar**, wenn es eine Abbildungsmatrix von Φ gibt, die Diagonalgestalt hat.

**解释**：一个矩阵 A 被称作可对角化矩阵，当存在一个可逆矩阵P 使得P^(-1)AP 是对角矩阵。

可对角化矩阵和映射有重要价值，因为对角矩阵特别容易处理：它们的特征值和特征向量是已知的，且其次方可通过计算对角元素同样的次方来获得。

#### 1. Kriterium für Diagonalisierbarkeit eines Endomorphismus
Für einen Endomorphismus Φ eines n-dimensionalen K-Vektorraumes V sind folgende Aussagen äquivalent:

1. Φ ist diagonalisierbar
2. In V gibt es eine Basis aus Eigenvektoren von Φ
3. V ist die direkte Summe der Eigenräume von Φ
4. Die Summe der Dimensionen der Eigenräume von Φ ist n

#### 2. Kriterium für Diagonalisierbarkeit eines Endomorphismus
Φ ist genau dann diagonalisierbar, wenn sein CP pΦ in der Form 
+ PΦ = (-1)^n(X-λ1)^r1 *...*(X-λk)^rk  (*)
+ dim Bild(Φ-λi*idV) = n-ri
darstellbar ist.

**Bemerkung**
+ dim Bild(Φ - λi * idV) = n-ri ⇐⇒ dimEλi = dim Kern(Φ - λi * idV) = ri

Besitzt ein Polynom p die Darstellung (*), so sagt man, dass p in **Linearfatoren zerfällt**. Die Zahl ri in der Darstellung ( *) nennt man **algebraische Vielfachheit** des Eigenwertes λi. Die Dimension des Eigenraumes Eλi heißt **geometrische Vielfachheit** des Eigenwertes λi.

**解读**：一个Endomorphismus Φ 是刚好可对角化的，当CP 可以被Linearfaktoren 分解，并且所有的特征值的geometrische 和 algebraische Vielfachheit 都相等。

### Trigonalisierbare Endomorphismen (可三角化)
-------------------
Ein Endomorphismus Φ: V→V eines endlich dimensionalen K-Vektorraumes V heißt **trigonalisierbar**, wenn eine Basis von V existiert bezüglich der Φ durch eine (obere) Dreiecksmatrix dargestellt wird.

+ Ein Endomorphismus Φ ∈ Hom(V,V) ist genau dann trigonalisierbar, wenn das charakteristische Polynom pΦ in Linearfaktoren zerfällt.

**解读**：相比于Diagonalisierbarkeit，只要CP 能被Linearfaktoren 分解就可以三角化。→ 任何在复数空间里的有限Endomorphismus 都可以被三角化。 

### 16. Der Satz von Cayley-Hamilton
--------------------
Es sei V ein K-Vektorraum, Φ ein Endomorphismus von V sowie 
+ p = a0 + a1X + a2X^2 +...+anX^n ∈K[X]
ein Polynom. Dann sei p(Φ) der Endomorphismus
+ p(Φ):= a0idV + a1Φ + a2Φ^2 +...+anΦ^n ∈ Hom(V,V)
wobei Φ^k = Φ◦Φ◦...◦Φ (k Faktoren) gilt.

#### Cayley-Hamilton
Es seien V ein n-dimensionaler K-Vektorraum, Φ ein Endomorphismus von V und pΦ das charakteristische Polynom von Φ. Dann gilt pΦ(Φ) = 0 (=Nullabbildung)

### Die Jordansche Normalform(若尔当标准型)
-------------------
**解读**： 若尔当矩阵，这种矩阵接近对角矩阵：除了主对角线上方元素之外，其余都是零且主对角线上方的对角线的系数若不为零只能为1，且这1左方和下方的系数都有相同的值。

若尔当标准型的目标就是将更多的矩阵简化到一类只比对角矩阵稍微复杂的矩阵。

Ein Endomorphismus Φ eines K-Vektorraumes heißt **nilpotent**, falls ein k∈N existiert, so dass Φ^k = 0 ist.

Es seien V ein n-dimensionaler komplexer Vekttorraum und Φ ein Endomorphismus von V. Für einen Eigenwert λ ∈ C von Φ und k∈N0 definieren wir
+ Kk := Kern(Φ-λid)^k

Für die Kerne Kk (k=0,1,2...) zum Eigenwert λ gilt:
1. Alle Kk sind Φ-invariant, d.h. Φ(Kk) ⊆ Kk
2. Es ist K0 ⊂ K1 ⊆ K2 ⊆ ...
   
#### Hauptraum
Ein Vektor v ∈ V mit v != 0 heißt **Hauptvektor** (oder **verallgemeinerter Eigenvektor**) von Φ zum Eigenwert λ, wenn es eine Zahl k ∈ N gibt mit
+ (Φ -λid)^k(v) = 0

Für q ∈ N heißt Nq = Kern (Φ-λid)^q der zum Eigenwert λ gehörige **Hauptraum** (oder **verallgemeinerte Eigenraum**) Hλ von Φ. Diese Zahl q heißt **Index** von Hλ.

**解释**： 广义特征向量相比于特征向量，就是利用广义特征向量的重数加起来整好是空间的维数来替代特征向量。

#### Die Hauptraum-Zerlegung

Sei Hλ ein Hauptraum von Φ mit dem Index q. Der Bildraum Bλ := Bild(Φ-λid)^q ist ein Vektorraum-Komplement von Hλ = Kern(Φ-λid)^q, d.h. es gilt 
+ V = Hλ ⊕ Bλ
Außerdem ist Bλ invariant unter Φ

**Hauptraumzerlegung**: Sei Φ ein Endomorphismus eines komplexen Vektorraums V mit charakteristischem Polynom 
+ pΦ = (-1)^n * (X-λ1)^r1 ... (X-λk)^rk

Dann ist V die direkte Summe der zugehörigen Haupträume von Φ:
+ V = Hλ1 ⊕ Hλ2 Φ....⊕ Hλk

Außerdem gilt für 1<=i<=k, dass dim Hλi = ri

