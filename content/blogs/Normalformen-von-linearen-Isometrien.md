---
title: "Normalformen von linearen Isometrien"
date: 2019-11-24T01:30:27+01:00
math: true
tags: ["linear algebra","math"]
---

本章的目的是对所给出的 lineare Isometrie 找出一组Basis，这样我们能有一个相对容易的针对这组Basis 的Abbildungsmatrix。

## Theorie

### Satz (ohne Beweis)

#### Diagonalisierbarkeit

Sei $V$ ein endlich-dimensionaler unitärer Vektorraum und $\Phi:V\to V$ eine lineare Isometrie. Dann ist $\Phi$ diagonalisierbar. Genauer: Es existiert eine Orthonormalbasis von $V$, die aus Eigenvektoren von $\Phi$ besteht.

Die Diagonalmatrix heißt die __(unitäre) Normalform der linearen Isometrie__ $\Phi$. Sie ist bis auf die Reihenfolge der Eigenwerte $\lambda\_k$ durch $\Phi$ eindeutig festgelegt. Damit ist auch eine __Klassifikation der linearen Isometrien__ eines unitären Vektorraumes gegeben: Zur selben Klasse gehören alle linearen Isometrien mit derselben Normalform (einschließlich permutierter Diagonalelemente).

##### Folgerung (Unitäre Normalform ist diagonal)

Ist $A$ eine unitäre $n\times n$-Matrix, so existiert eine unitäre Matrix $T$ mit
$$
T^\ast AT=\begin{pmatrix}
    \lambda\_1&&0\newline
    &\ldots&\newline
    0&&\lambda\_n
\end{pmatrix}
$$
dabei sind die $\lambda\_k$ die Eigenwerte von $A$ und es gilt $|\lambda\_k|=1\ \ \ (k=1,\ldots,n)$

---

#### euklidische Normalform: Dreh-Kästchen

Ist $\Phi$ eine lineare Isometrie eines $n$-dimensionalen euklidschen Vektorraumes $V$, so existiert eine Orthonormalbasis von $V$, bezüglich der die Abbvildungsmatrix von $\Phi$ die folgende Form hat:
$$
\begin{pmatrix}
1&&0&&&&&&& \newline
&\ldots &&&&&&0&& \newline
0&&1&&&&&&& \newline
&&&-1&&0&&&& \newline
&&&&\ldots&&&&& \newline
&&&0&&-1&&&& \newline
&&&&&&\cos \omega\_1&-\sin\omega\_1&&& \newline
&&&&&&\sin\omega\_1&\cos\omega\_1&&&\newline
&&&&&&&\ldots&&\newline
&0&&&&&&&\cos\omega\_r&\sin\omega\_r\newline
&&&&&&&&\sin\omega\_r&\cos\omega\_r
\end{pmatrix}
$$
mit $0\lt\omega\_j\lt\pi;j=1,\ldots,r$. Die Matrix ist bis auf die Reihenfolge der Kästchen durch $\Phi$ eindeutig bestimmt und heißt die __euklidische Normalform der linearen Isometrie__ $\Phi$.

##### Bemerkung

1. Der Kästchenform entspricht eine Zerlegung des Vektorraumes $V$:
$$
V=E\_1\oplus E\_{-1}\oplus W\_1\oplus\ldots\oplus W\_r
$$
dabei sind $E\_1,E\_{-1}$ die Eigenräume zum Eigenwert $1,-1$ (die auch fehlen können), und die $W\_j$ sind $2$-dimensionale $\Phi$-invariante Untervektorräume (die ebenfalls fehlen können).

2. Eine lineare Isometrie eines euklidische Vektorraumes ist also durch die geometrischen Vielfachheiten $p$ und $q$ der Eigenwerte $+1$ und $-1$ und die $r$ Winkel $\omega\_j$ charakterisiert (wobei $p+q+2r=\dim V$ ist).

---

##### Bemerkung

1. In der Literatur wird manchmal auch eine andere Maltrix als Normalform bezeichnet. Sie unterscheidet sich von der obigen Form dadurch, dass die Zweierkästchen die transponierte Form
$$
\begin{matrix}
\cos\omega &\sin\omega\newline
-\sin\omega&\cos\omega
\end{matrix}
$$
besitzen. Jede der Normalformen geht aus der anderen dadurch hervor, dass bei jedem Zweierkuastchen jeweils die Reihenfolge der zugehörigen orthonormalen Basisvektoren $x,y$ vertauscht wird oder dass $y$ durch $-y$ ersetzt wird.

2. Ist $A\in \Bbb{R}^{n\times n}$ orthogonal, so liefert das obige Beweisverfahren, angewandt auf die symmetrische Hilfsmatrix $B:=A=A^\top$, eine orthogonale Matrix $S\in\Bbb{R}^{n\times n}$, sodass $S^\top AS$ obige Normalform besitzt. 

---

#### Satz ohne Name

Zu jeder orthogonalen Matrix $A$ gibt es eine orthogonale Matrix $S$, so daß
$$
B=S^\top AS
$$
gilt, wobei $B$ die Gestalt vom Satz "euklidische Normalform: Dreh-Kästchen" hat.

Diesen Satz kann man auffassen als eine __Klassifikation der linearen Isometrien__ eines $n$-dimensionalen euklidischen Vektorraumes, wobei alle linearen Isometrien mit derselben Normalform - einschließlich der verschiedenen Diagonalordnungen - zur selben Klasse zählen.

Aus Satz "euklidische Normalform: Dreh-Kästchen" ergibt sich die folgende geometrische Beschreibung einer lineare Isometrie $\Phi:V\to V$. Es gibt eine Orthogonalzerlegung
$$
V=U\_1\oplus U\_2\oplus W\_1\oplus\ldots\oplus W\_k
$$
so dass

+ $\Phi|\_{U\_1}=id\_{U\_1}$ ist, also $U\_1$ Fixunterraum ist

+ dass weiter $\Phi|\_{U\_2}:x\mapsto -x$ gilt, $\Phi$ also die Vektoren aus $U\_2$ an $U\_2^\bot = U\_1\oplus U\_2\oplus W\_1\oplus\ldots\oplus W\_k$ spiegelt

+ und so dass $\Phi|\_{W\_i}$ für $i=1,\ldots,k$ Drehungen in den zweidimensionalen Untervektorräumen $W\_i$ darstellen.

Ist die Dimensionen von $V$ speziell $2$ oder $3$, so haben wir:

+ $n=2$: Satz "Nach euklidische Normalform: Dreh-Kästchen" treten $4$ Klassen von linearen Isometrien auf. Diese lassen sich durch die Normalformen
$$
B\_1=\begin{pmatrix}
1&0\newline
0&1\newline
\end{pmatrix},
B\_2=\begin{pmatrix}
1&0\newline
0&-1\newline
\end{pmatrix},
B\_3=\begin{pmatrix}
-1&0\newline
0&-1\newline
\end{pmatrix},
B\_4=\begin{pmatrix}
\cos\omega&-\sin\omega\newline
\sin\omega&\cos\omega\newline
\end{pmatrix}
$$
mit $0\lt\omega\lt\pi$ beschreiben. Die entsprechenden linearen Isometrien sind der Reihe nach die Identität, eine (Geraden-)Spiegelung, die Spiegelung an 0 und eine Drehung um $0$ mit Drehwinkel $\omega$.

+ $n=3$: Ist $\det\Phi=1$, so gibt es einen Vektor $v\neq 0$, der Fixvektor ist. Im Orthogonalraum $[v]^\bot$ ist $\Phi$ eine Drehung. $\Phi$  heißt dann __Drehung__ des Vektorraums $V$ mit der __Drehachse__ $[v]$ und der Drehebene $[v]^\bot$.

Ist $\det\Phi=-1$, so gibt es ein $v\neq 0$ mit $\Phi(v)=-v$. Im Orthogonalraum $[v]^\bot$ ist $\Phi$ eine Drehung. $\Phi$ ist dann Produkt einer Drehung um die Achse $[v]$ mit einer Speigelung an der Drehebene $[v]^\bot$ und heißt deswegen __Drehspiegelung__ von $V$.

##### Bemerkung

Eine Klasse von Endomorphismen, die lineare Isometrien und selbstadjungierte lineare Abbildungen verallgemeinert sind die sogenannten normalen Selbstabbildungen. Ein Endomorphismus $\Phi:V\to V$ eines $n$-dimensionalen euklidischen oder unitären Vektorraumes $V$ heißt __normal__, wenn gilt
$$
\Phi \circ \Phi^\ast=\Phi^\ast \circ \Phi
$$
Übersetzt in die Matrizensprache haben wir die folgende Definition. Eine Matrix $A\in\Bbb{C}^{n\times n}$ bzw. $\Bbb{R}^{n\times n}$ heißt __normal__, falls gilt
$$
AA^\ast=A^\ast A \ \ \ \ bzw.\ \ AA^\top=A^\top A
$$