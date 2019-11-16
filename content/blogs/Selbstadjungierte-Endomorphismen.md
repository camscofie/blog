---
title: "Selbstadjungierte Endomorphismen"
date: 2019-11-13T19:14:58+01:00
draft: false
math: true
tags: ["linear algebra","math"]
---

## Theorie

### Definition

Ein Endomorphismus $\Phi:V\to V$ eines endlich-dimensionalen Vektorraumes $V$ mit Skalarprodukt heißt __selbstadjungiert__, wenn $\Phi^\ast=\Phi$ ist, d.h. wenn für alle $x,y\in V$ gilt
$$
\langle\Phi(x),y\rangle=\langle x,\Phi(y)\rangle
$$

### Satz (ohne Beweis)

#### Matrix eines s.a. Endomorphismus

+ Ein Endomorphismus $\Phi$ ist genau dann selbstadjungiert, wenn die Abbildungsmtraix $A$ von $\Phi$ bezüglich einer Orthonormalbasis im euklidischen Fall symmetrisch $(A^\top=A)$ und im unitären Fall hermitesch $(\overline{A}^\top=A)$ ist.

---

+ Es sei $V$ ein $n$-dimensionaler (reeller oder komplexer) Vektorraum mit Skalarprodukt und $\Phi:V\to V$ ein selbstadjungierter Endomorphismus. Dann sind alle Nullstellen des charakteristischen Polynoms von $\Phi$ reell. Das charakteristische Polynom von $\Phi$ zerfällt also in $n$ Linearfaktoren:
$$
p\_\Phi=\pm(X-\lambda\_1)\ldots(x-\lambda\_n),\ \ \lambda\_i\in \Bbb{R}
$$
Insbesondere sind alle Eigenwerte eines selbstadjungierten Endomorphismus (bzw. einer symmetrischen oder hermiteschen Matrix) reell.

---

#### Spektralsatz

+ Es sei $V$ ein $n$-dimensionaler Vektorraum mit Skalarprodukt und $\Phi:V\to V$ ein selbstadjungierter Endomorphismus. Dann ist $\Phi$ diagonalisierbar. Genauer: Es existiert eine Orthonormalbasis $B$ von $V$, die aus Eigenvektoren von $\Phi$ besteht und die Abbildungsmatrix von $\Phi$ bezüglich dieser Orthonormalbasis hat Diagonalform
$$
M^B\_B(\Phi)=\begin{pmatrix}
\lambda\_1 &&0\newline
&\ldots&\newline
0&&\lambda\_n    
\end{pmatrix}
$$
wobei $\lambda\_1,\ldots,\lambda\_n$ die $n$ (reellen) Eigenwerte von $\Phi$ sind.

##### Folgerung (Spektralsatz für Matrizen)

Ist $A$ eine reelle, symmetrische (bzw. komplexe, hermitesche) $n\times n$-Matrix, so ist $A$ diagonalisierbar. Genauer gilt:
Es gibt eine orthogonale (bzw. unitäre) $n\times n$-Matrix $S$ mit
$$
S^\ast AS=S^{-1}AS=\begin{pmatrix}
\lambda\_1 &&0\newline
&\ldots&\newline
0&&\lambda\_n    
\end{pmatrix}
$$
wobei $\lambda\_1,\ldots,\lambda\_n$ die $n$ (reellen) Eigenwerte von $A$ sind.

---

#### Ein Kriterium für "positiv definit"

+ Matrix $A$ ist genau dann positiv definit, wenn alle Eigenwerte von $A$ positiv sind.

##### Folgerung ("Wurzel" aus einer positiv definiten Matrix)

Ist $A\in \Bbb{R}^{n\times n}$ eine positiv definite symmetrische Matrix, so existiert eine Matrix $\sqrt{A}\in \Bbb{R}^{n\times n}$ mit $\sqrt{A}\cdot\sqrt{A}=A$.