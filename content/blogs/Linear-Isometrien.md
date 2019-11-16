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