---
title: "Orthogonal und unitäre Matrizen"
date: 2019-11-12T22:07:03+01:00
draft: false
math: ture
tags: ["linear algebra","math"]
---

Gegeben sei ein Vektorraum $V$ mit Skalarprodukt, eine Orthonormalbasis $B=\\{e\_1,\ldots,e\_n\\}$ von $V$ und eine Matrix $A=(a\_{ij})\in GL(n,\Bbb{C})$. Wir definieren eine lineare Abbildung $\Phi\_A:V\to V$ durch
$$
\Phi\_A(e\_j):=\sum^n\_{k=1}a\_{kj}e\_k,\ \ \ \ 1\le j\le n
$$
Dann ist $\\{e^\prime\_j := \Phi\_A(e\_j)\ |\ 1\le j\le n\\}$ auch eine basis von $V$.

__Frage__: Wann ist $B^\prime = \\{e\_1^\prime,\ldots,e\_n^\prime\\}$ auch wieder eine ONB?

Dazu rechnen wir
$$
\langle e\_j^\prime,e\_k^\prime\rangle=\langle\sum^n\_{r=1}a\_{rj}e\_r\ ,\ sum^n\_{s=1}a\_{sk}e\_s\rangle=\sum^n\_{r,s=1}a\_{rj}\overline{a}\_{sk}\delta\_{rs}=\sum^n\_{r=1}a\_{rj}\overline{a}\_{rk}
$$

Also ist $B^\prime$ genau dann auch eine Orthonormalbasis, wenn gilt:
$$
\begin{aligned}
\sum^n\_{r=1}a\_{rj}a\_{rk}=\delta\_{jk}\ ,\ \ j,k=1,\ldots,n \ \ \ \Leftrightarrow\ \ \ A^\top A = E\_n & \ \ \ \ \text{Für einen euklidischen Vektorraum } V \newline
\sum^n\_{r=1}a\_{rj}\overline{a}\_{rk}=\delta\_{jk}\ ,\ \ j,k=1,\ldots,n \ \ \ \Leftrightarrow\ \ \ A^\top \overline{A} = E\_n & \ \ \ \ \text{Für einen unitären Vektorraum } V
\end{aligned}
$$

## Theorie

### Definition

Eine reelle bzw. komplexe $n\times n$-Matrix $A$ heißt __orthogonal__ bzw. __unitär Matrix__, falls gilt
$$
A^\top A=E\_n\ \ \ \ \text{bzw.}\ \ \ \ A^\top\overline{A}=E\_n
$$

### Satz(ohne Beweis)

Sind $B$ und $B^\prime$ zwei Orthonormalbasen eines euklidischen (bzw. unitären) Vektorraumes $V$, so ist die Matrix des Basiswechsels orthogonal (bzw. unitär). Ist umgekehrt $B=\\{e\_1,\ldots,e\_n\\}$ eine Orthonormalbasis von $V$ und $A$ eine orthogonale (bzw. unitäre) $n\times n$-Matrix, so ist auch $B^\prime := \\{\Phi\_A(e\_1),\ldots,\Phi\_A(e\_n)\\}$ eine Orthonormalbasis von $V$.

---

#### Charakterisierung von orthogonalen Matrizen

Sei $A\in \Bbb{R}^n\times n$. Folgende Aussagen sind äquivalent:

1. $A$ ist orthogonale Matrix.

2. $A$ ist regulär und $A^{-1}=A^\top$.

3. Die Spaltenvektoren (bzw. die Zeilenvektoren) von $A$ bilden eine Orthonormalbasis von $\Bbb{R}^n$ bzgl. des Standardskalarproduktes.

Analog gitl für unitäre Matrizen.

---

#### Charakterisierung von unitären Matrizen

Sei $A\in \Bbb{C}^n\times n$. Folgende Aussagen sind äquivalent:

1. $A$ ist unitäre Matrix.

2. $A$ ist regulär und $A^{-1}=\overline{A}^\top$.

3. Die Spaltenvektoren (bzw. die Zeilenvektoren) von $A$ bilden eine Orthonormalbasis von $\Bbb{C}^n$ bzgl. des Standardskalarproduktes.

##### Folgerung

1. Für eine orthogonale Matrix gilt: $\det A = \pm 1$.

2. Für eine unitäre Matrix gilt: $| \det A|=1$.

---

#### Matrizen-Gruppen

Für jedes $n \in \Bbb{N}$ bilden die orthogonalen (bzw. unitären) $n \times n$-Matrizen bezüglich der Matrizen-Multiplikation eine Gruppe:

Die __orthogonale Gruppe__
$$
O(n):=\\{A\in GL(n,\Bbb{R})\ |\ A^\top A =E\_n\\}
$$
bzw. die __unitäre Gruppe__
$$
U(n):=\\{A\in GL(n,\Bbb{C})\ |\ \overline{A}^\top A=E\_n\\}
$$

##### Bemerkung

Wir erinnern an die Definition der komplexen bzw. reellen speziellen linearen Gruppe:
$$
SL(n,\Bbb{C})=\\{A\in \Bbb{C}^{n\times n}\ |\ det(A)=1\\},\ \ \ \ SL(n,\Bbb{R}):=SL(n,\Bbb{C})\cap GL(n,\Bbb{R})
$$
Die Gruppe
$$
SO(n):= O(n)\cap SL(n,\Bbb{R})\ \ \ \text{bzw. } SU(n)=U(n)\cap SL(n,\Bbb{C})
$$
heißt __spezielle orthogonale__ bzw. __spezielle unitäre Gruppe__.


$\ast$: Die Untergruppe $SO(n):=\\{A\in O(n)\ |\ det(A)=1\\}\subset SL(n,\Bbb{R})$ heißt __spezielle orthogonale Gruppe__. (bzw. $SU(n)\subset SL(n,\Bbb{C})$ :__spezielle unitäre Gruppe__)

$\ast\ast$: Die Menge $GL(n,\Bbb{K})$ aller invertierbaren $n\times n$-Matrizen über dem Körper ist bezüglich der Matrizen-Multiplikation eine Gruppe.

---

#### Iwasawa Zerlegung

Wir führen noch drei weitere Untergruppen von $GL(n,\Bbb{R})$ ein. Es sei 

+ $B(n)\subset GL(n,\Bbb{R})$ die Gruppe der oberen Dreiecksmatrizen mit positiven Diagonalelementen

+ $A(n)\subset GL(n,\Bbb{R})$ bezeichne die (abelsche) Gruppe der Diagonalmatrizen mit positiven Diagonaleinträgen und Determinante $1$ 

+ $N(n)\subset GL(n,\Bbb{R})$ die Gruppe der oberen Dreieckmatrizen mit Einsen auf der Diagonalen.

Es ist
$$
GL(n,\Bbb{R})=O(n)B(n)\ \ \text{und}\ \ SL(n,\Bbb{R})=SO(n)A(n)N(n)
$$
Genauer gilt: Jede Matrix $A\in GL(n,\Bbb{R})$ kann eindeutig geschrieben werden als Produkt $A=TB$ mit $T\in O(n)$ und $B\in B(n)$. Jede Matrix $A\in SL(n,\Bbb{R})$ kann geschrieben werden als Produkt $A=TDN$ wobei $T\in SO(n), D\in A(n)$ und $N\in N(n)$.
