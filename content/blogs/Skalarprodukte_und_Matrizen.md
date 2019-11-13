---
title: Skalarprodukte und Matrizen
date: 2019-11-08T17:27:30+01:00
draft: false
math: true
tags: ["linear algebra","math"]
---

在不同向量空间里的线性映射可以被 Matrix 表示，Skalarprodukte 也可以。

## Theorie

### Definition

+ Sei $V$ ein $n-$dimensionaler reeller bzw. komplexer Vektorraum und $\langle,\rangle$ ein Skalarprodukt auf $V$. Wir wählen eine geordnete Basis $B=\{b\_1,\ldots,b\_n\}$ von $V$ und setzen $$g\_{kj} := \langle b\_k,b\_j \rangle \ \ \ \ 1 \le k,j \le n$$ Die $n \times n$-Matrix $G := (g\_{kj}) \in \Bbb{R}^{n \times n}$ bzw. $\Bbb{C}^{c \times c}$ heißt __Matrix des Skalarproduktes__ $\langle,\rangle$ bezüglich der Basis $B$. Da $\langle b\_j,b\_k \rangle = \langle b\_k,b\_j \rangle$ bzw. $\langle b\_j,b\_k \rangle = \overline{\langle b\_k,b\_j \rangle}$ gilt $g\_{jk} = g\_{kj}$ bzw. $g\_{jk} = \overline{g\_{kj}}$. Für die Matrix eines Skalarprodukts gilt also $$G=G^\top$$ $$G=\overline{G}^\top$$ falls $V$ euklidisch oder unitär ist. Sei jetzt $V$ ein _unitärer Vektorraum_ und $B=\{b\_1,\ldots,b\_n\}$ eine Basis von $V$. Dann haben wir für $a=\sum^n\_{n=1} a\_kb\_k$ und $b=\sum^n\_{j=1} \beta\_j b\_j$.
$$ 
\langle a,b\rangle = \sum^n\_{k=1}\sum^n\_{j=1}\alpha\_k\langle b\_k,b\_j \rangle \overline{\beta\_j} = \sum^n\_{k=1}\sum^n\_{j=1}\alpha\_k g\_{kj} \overline{\beta\_j}
$$
$$
= (\alpha\_1,\ldots,\alpha\_n) 
\begin{pmatrix}
g\_{11} & g\_{12} & \ldots & g\_{1n} \newline
\ldots & \ldots & \ldots & \ldots \newline
g\_{n1} & g\_{n2} & \ldots & g\_{nn}
\end{pmatrix}
\begin{pmatrix}
\overline{\beta\_1} \newline
\ldots \newline
\overline{\beta\_n} 
\end{pmatrix}
$$
Mit den Komponentenvektoren
$$
\Theta\_B(a) = 
\begin{pmatrix}
\alpha\_1 \newline
\ldots \newline
\alpha\_n
\end{pmatrix}
, \Theta\_B(b) =
\begin{pmatrix}
\beta\_1 \newline
\ldots
\beta\_n
\end{pmatrix}
$$
von $a$ und $b$ können wir also schreiben 
$$
\langle a,b \rangle = \Theta\_B(a)^\top G \overline{\Theta\_B(b)};\ \ \ \ \ a,b \in V,\ \ \Theta\_C(a),\Theta\_C(b) \in \Bbb{C}^n
$$
Ganz analog erhalten wir für einen _euklidischen Vektorraum_ die Formel
$$
\langle a,b \rangle = \Theta\_B(a)^\top G \Theta\_B(b);\ \ \ \ \ a,b \in V,\ \ \Theta\_B(a),\Theta\_B(b) \in \Bbb{R}^n
$$
Da Skalarprodukte positiv definit sind, ergibt sich als Konsequenz dieser Formel für die Matrix $G$ von $\langle,\rangle$:
Im euklidischen Fall gilt für alle $x \in \Bbb{R}^n, x \neq 0,x^\top Gx \gt 0$, und im unitären Fall gilt $\forall z \in \Bbb{C}^n, z \neq 0,z^\top G \overline{z} \gt 0$.

---

+ Ist $V$ ein endlich dimensionaler Vektorraum über einem Körper $K$, $B=(b\_1,b\_2,\ldots,b\_n)$ eine geordnete Basis von $V$ und $s:V\times V \to K$ eine Bilinearform, so heißt die Matrix
$$
F\_B(s):=\begin{pmatrix}
s(b\_1,b\_1) & \ldots & s(b\_1,b\_n) \newline
\ldots&\ldots &\ldots \newline
s(b\_n,b\_1) & \ldots & s(b\_n,b\_n)
\end{pmatrix} \in K^{n\times n}
$$
__Fundamentalmatrix__ von $s$ bezüglich $B$.

+ Eine Matrix $A \in \Bbb{R}^{n \times n}$ heißt __symmetrisch__, falls gilt $$A^\top = A$$
+ Eine Matrix $A \in \Bbb{C}^{n \times n}$ heißt __hermitesch__, falls gilt $$\overline{A}^\top = A$$ 
+ Eine symmetrische(bzw. hermitesche) Matrix $A$ für die gilt 
$$
\\{ x^\top Gx \gt 0\ |\ \forall x \in \Bbb{R}^n,x\neq 0\\} \text{ bzw. }\\{ z^\top G\overline{z} \gt 0\ |\ \forall z \in \Bbb{C}^n,z\neq 0\\}
$$
heißt __positiv definit__.

### Satz (ohne Beweis)

#### Beschreibung aller Skalarprodukte

Es sei $V$ ein euklidischer bzw. unitärer Vektorraum und $B$ eine geordnete Basis von $V$. Dann ist $F$ genau dann ein Skalarprodukt, wenn eine positiv definite, symmetrische (bzw. hermitesche) Matrix $A \in \Bbb{R}^{n \times n}$ bzw. $A \in \Bbb{C}^{n \times n}$ existiert mit
$$
F(x,y) = \Theta\_B(x)^\top A \Theta\_B(y)\ \ bzw.\ \ F(x,y) = \Theta\_B(x)^\top A \overline{\Theta\_B(y)} \ \ \ \ (x,y \in V)
$$

##### Lemma
Es sei $V$ endlich dimensional, $B$ eine geordnete Basis von $V$ und $s:V\times V\to K$ eine Bilinearform
1. $s$ ist symmetrisch genau dann, wenn $F\_B(s)$ eine symmetrische Matrix ist.
2. $s$ ist schiefsymmetrisch genau dann, wenn $F\_B(s)$ schiefsymmetrische Matrix ist (d.h. $F\_B(s)^\top = -F\_B(s)$)

#### Basiswechsel

Ist $V$ ein endlich dimensionaler $K$-Vektorraum, und sind $B,C$ Basen von $V$, so gilt für jede Bilinearform $s:V\times V \to K$
$$
F\_B(s)=(D\_{CB}(id\_V))^\top \cdot F\_C(s) \cdot D\_{CB}(id\_V) 
$$
Man beachte, dass im Allgemeinen
$$
(D\_{CB}(id\_V))^\top \neq (D\_{CB}(id\_V))^{-1}=D\_{BC(id\_V)}
$$
gilt. Der Basiswechsel für Bilinearformen ist also anders zu berechnen als der von Endomorphismen.

##### Basiswechsel im Unitärer Vektorraumes 

Sei V ein euklidischer bzw. unitärer Vektorraumes mit Basen $B$ und $\widetilde{B}$. Weiter sei $S$ die Matrix des Basiswechsels von $\widetilde{B}$ nach $B$. Dann gelten für die Matrizen des Skalarproduktes die Transformationsformeln
$$
\widetilde{G} = S^\top GS,\ \ \ \ S \in GL(n,\Bbb{R})\ \ \ (euklidischer\  Fall)
$$
$$
\widetilde{G} = S^\top G\overline{S},\ \ \ \ S \in GL(n,\Bbb{C})\ \ \ (unitärer\  Fall)
$$