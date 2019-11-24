---
title: "Linear Isometrien"
date: 2019-11-13T20:18:16+01:00
draft: false
math: true
tags: ["linear algebra","math"]
---

## Theorie

### Definition

+ Es seien $(X,d\_X)$ und $(Y,d\_Y)$ zwei metrische Räume. Eine Abbildung $f:=X\to Y$ heißt __Isometrie__, falls $f$ Abstände erhält, falls also für alle $p,q\in X$ gilt
$$
d\_Y(f(p),f(q))=d\_X(p,q)
$$

---

+ Es seien $V,W$ entweder zwei euklidische oder zwei unitäre Vektoräume. Eine lineare Abbildung $\Phi:V\to W$ heißt __lineare Isometrie__, wenn für alle $x\in V$ gilt
$$
\parallel\Phi(x)\parallel\_W=\parallel x\parallel\_V
$$
d.h. wenn $\Phi$ die Länge jedes Vektors $x\in V$ invariant läßt.

#### Bemerkung

1. Eine allgemeine Isometrie $f$ und damit insbesondere eine lineare Isometrie $\Phi$ ist injektiv:
$$
f(p)=f(q)\Longrightarrow d\_X(p,q)=d\_Y(f(p),f(q))=0
$$
also wegen der Positivität einer Metrik $p=q$.

2. Ein Vektorraum mit Skalarprodukt ist ein normierter Raum und deshalb auch ein metrischer Raum. Die Metrik ist gegeben durch
$$
d(u,v):=\parallel u-v\parallel=\sqrt{\langle u-v,u-v\rangle}
$$
Eine lineare Isometrie ist also auch eine Isometrie im allgemeinen Sinn (für die durch die Skalarprodukte induzierten Metriken).

---

####  Beispiel

##### Drehungen:

Wir vesehen $\Bbb{R}^2$ mit dem Standard-Skalarprodukt und betrachten Polarkoordinaten
$$
\Bbb{R}^2 \ni x=\begin{pmatrix}
    x\_1 \newline
    x\_2
\end{pmatrix}=\begin{pmatrix}
    r\cos\alpha \newline
    r\sin\alpha
\end{pmatrix}
$$
Dann haben wir (mit den Additionstheoremen für Sinus und Cosinus)
$$
D\_\omega(x):=\begin{pmatrix}
    \cos\omega&-\sin\omega \newline
    \sin\omega&\cos\omega
\end{pmatrix}\begin{pmatrix}
    r\cos\alpha\newline
    r\sin\alpha
\end{pmatrix}=\begin{pmatrix}
    r\cos(\alpha+\omega)\newline
    r\sin(\alpha+\omega)
\end{pmatrix}
$$
Für die lineare Abbildung $D\_\omega$ gilt
$$
\parallel D\_\omega(x)\parallel^2=r^2(\cos^2(\alpha+\omega)+\sin^2(\alpha+\omega))=r^2=\parallel x\parallel^2
$$
also ist $D\_\omega$ eine lineare Isometrie von $\Bbb{R}^2$.

Geometrisch ist $D\_\omega$ eine Drehung (im Uhrzeigersinn) um den Ursprung von $\Bbb{R}^2$ mit dem Drehwinkel $\omega$.

<img src="/postImage/LineareIsometrien/Drehung.png" alt="pythagoras" width="300" class="center" />

Entsprechend ist $D\_{-w}$ eine Drehung (im Gegen-Uhrzeigersinn) um den Ursprung von $\Bbb{R}^2$ mit dem Drehwinkel $\omega$. Es ist $\det D\_\omega=\det D\_{-\omega} = 1$. Als Spezialfälle haben wir für $\omega=0,\pi:$
$$
D\_0=\begin{pmatrix}
    1&0\newline
    0&1
\end{pmatrix}\text{ und }D\_\pi=D\_{-\pi}=\begin{pmatrix}
    -1&0\newline
    0&-1
\end{pmatrix}
$$

also die Identität und die Punktspiegelung am Ursprung $(0,0)$.

##### Verallgemeinerung:

Sei $A\in\Bbb{R}^{n\times n}$ eine orthogonale Matrix, also $A^\top A=E$, dann ist die lineare Abbildung $\Phi:\Bbb{R}^n\to\Bbb{R}^n,\ x\mapsto Ax$ eine lineare Isometrie:
$$
\parallel Ax\parallel^2=(Ax)^\top Ax=x^\top A^\top Ax=x^\top x=\parallel x\parallel^2
$$

##### Translationen:

Translationen Sind nicht-lineare Isometrien. Es sei $V$ ein Vektorraum mit Skalarprodukt. Für $a\in V$ ist
$$
T\_a:V\to V;\ x\mapsto x+a
$$
die Translation um den Vektor $a$. Dann ist $T\_a$ (für $a\neq 0$) keine lineare Abbildung, aber eine Isometrie im allgemeinen Sinn:
$$
d(T\_a(x),T\_a(y))=\parallel(x+a)-(y+a)\parallel=\parallel x-y\parallel=d(x,y)
$$

---

### Satz(ohne Beweis)

Es seien $V,W$ zwei unitäre oder zwei euklidische Vektorräume. Folgende Aussagen für eine lineare Abbildung $\Phi :V\to W$ sind äquivalent:

+ $\Phi$ ist eine lineare Isometrie.

+ $\forall x,y\in V$ gilt $\langle\Phi(x),\Phi(y)\rangle\_W=\langle x,y\rangle\_V$.

##### Folgerung

Eine lineare Isometrie zwischen euklidischen Vektorräumen ist "winkeltrue":
$$
\omega(\Phi(x),\Phi(y))=\omega(x,y)
$$

---

#### Lineare Isometrien und Adjungierte

+ Ein Endomorphismus $\Phi: V\to V$ eines endlich-dimensionalen Vektorraums mit Skalarprodukt ist genau dann eine lineare Isometrie, wenn gitl
$$
\Phi^\ast \circ \Phi=id\_V
$$

+ Ein Endomorphismus $\Phi$ eines unitären (bzw. euklidischen) Vektorraums $V$ ist genau dann eine lineare Isometrie, wenn für die Abbildungsmatrix $A$ von $\Phi$ bezüglich einer Orthonormalbasis von $V$ gilt:
$$
A^\ast A=E
$$
d.h. genau dann, wenn $A$ unitär (bzw. orthogonal) ist.

##### Folgerung

+ Ein Endomorphismus $\Phi$ eines $n$-dimensionalen Vektorraumes $V$ mit Skalarprodukt ist genau dann eine lineare Isometrie von $V$, wenn $\Phi^\ast = \Phi^{-1}$ gilt. Insbesondere ist $\Phi^\ast$ auch eine lineare Isometrie von $V$.

+ Die linearen Isometrien eines $n$-dimensionalen euklidischen (bzw. unitären) Vektorraumes $V$ bilden bezüglich der Verkettung von Abbildungen eine Gruppe.

---

Jede lineare Isometrie $\Phi$ eines $n$-dimensionalen euklidischen Vektorraumes $V$ ist ein Produkt von höchstens $n$ Spiegelungen:
$$
\Phi=\sigma\_{a\_1}\circ\sigma\_{a\_2}\circ\ldots\circ\sigma\_{a\_n}
$$

---

Es sei $\Phi$ einen lineare Isometrie von $V$.

+ Es gilt $| \det\Phi|= 1$

+ Ist $\lambda\in \Bbb{C}$ ein Eigenwert von $\Phi$, so gilt $|\lambda|=1$.