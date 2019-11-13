---
title: "Normen"
date: 2019-11-08T23:24:22+01:00
draft: false
math: true
tags: ["linear algebra","math"]
---

在线性空间里表示一个vektor 的范数，长度以及两个vektor 之间的角度。

## Theorie

### Definition

---

#### Norm

Sei $V$ ein reeller oder komplexer Vektorraum. Eine __Norm__ auf $V$ ist eine Funktion $\| \|: V \to \Bbb{R},\ \ a \mapsto \parallel a\parallel$ mit folgenden Eigenschaften:
$\forall \lambda \in \Bbb{R}$(oder $\Bbb{C}$) und: Skalarprodukte (Forts.) alle $a,b \in C$ gilt:
$$
\begin{align}
\parallel\lambda a \parallel = |\lambda|\parallel a \parallel \ \ & \text{(Homogenität)} \newline
\parallel a +b\parallel \le \parallel a \parallel + \parallel b \parallel \ \ & \text{(Dreiecks-Ungleichung)} \newline
\parallel a \parallel \ge 0 \ \ \ und\ \ \ \parallel a \parallel =0 \ \Leftrightarrow \ a = 0\ \ & \text{(Definitheit)}
\end{align}
$$
Ein Paar $(V,\parallel\parallel)$ bestehend aus einem Vektorraum und einer Norm heißt __normierter Vektorraum__

---

#### Metrische Räume

+ Für eine beliebige Teilmenge $M$ von $V$ heißt eine Funktion $d:M\times M \to \Bbb{R}$ eine __Metrik__ (oder __Abstandsfunktion__), wenn $d$ die folgenden drei Eigenschaften erfüllt:
  
  1. $\forall p,q \in M:d(p,q) = d(q,p)\ \ \ (symmetrisch)$
  2. $\forall p,q,r \in M:d(p,r)\le d(p,q) + d(q,r)\ \ \ (dreiecks-Ungleichung)$
  3. $\forall p,q \in M: d(p,q) \ge 0\ und\ d(q,p)=0\ \Leftrightarrow\ p = q \ \ \ (positiv)$

+ Das Paar $(M,d)$ heißt dann __metrischer Raum__.

+ Der __Abstand von $x$ zu $y$__ ist definiert durch
$$
d(x,y) := \parallel y-x\parallel
$$
+  Der __Abstand von $x$ zu $M$__ ist definiert durch
$$
d(x,M) := inf\\{d(x,y)\ |\ y\in M\\}
$$

+ Ist $(V,\parallel\cdot\parallel)$ ein normierter Vektorraum und $x\in V$, so heißt die Menge
$$
\Bbb{S}\_r(x):=\\{y\in V\ |\ d(x,y)=r\\}
$$
aller Vektoren mit Abstand $r\gt 0$ zu $x$ die __Sphäre__ vom Radius $r$ mit Mittelpunkt $x$.

+ Die Sphäre $\Bbb{S}\_1(0)$ vom Radius $1$ mit dem Nullvektor als Mittelpunkt heißt __Einheitssphäre__ und ihre Elemente __Einheitsvektoren__.

+ Im euklidischen Vektorraum $\Bbb{R}^n$ mit dem Standardskalarprodukt $\langle,\rangle$ wird die Einheissphäre auch bezeichnet mit $\Bbb{S}^{n-1}$

##### Bemerkung
Jede Menge kann zu einem metrischen Raum gemacht werden. Druch
$$
d(p,q) :=
\begin{cases}
0 & \text{falls $p=q$,} \newline
1 & \text{sonst}    
\end{cases}
$$
wird auf $M$ die __diskrete Metrik__ definiert.

---

#### Winkel

Seien $a \neq 0,b \neq 0$ zwei Vektoren eines euklidischen Vektorraumes $(V,\langle,\rangle)$. Die eindeutig bestimmte reelle Zahl $\omega(a,b)\in [0,\pi]$ mit 
$$
cos(\omega(a,b))= \frac{\langle a,b \rangle}{\parallel a\parallel \cdot \parallel b \parallel}
$$
heißt __Winkel__ zwischen $a$ und $b$.

Diese Definitionsgleichung kann man auch so schreiben:
$$
\langle a,b\rangle = \parallel a \parallel\cdot\parallel b\parallel\cdot cos\omega(a,b)
$$
Die Abbildung
$$
\omega: V \setminus \\{0\\} \times V\setminus \\{0\\} \to \Bbb{R}; \ \ \ (a,b)\mapsto\omega(a,b)
$$
nennen wir __Winkelfunktion__.

##### Beispiel

$\Bbb{R}^2$ mit Standardskalarprodukt,  $\varphi = \omega(x,e\_1), \alpha=\omega(y,e\_1)$

<img src="/postImage/Normen/winkel.png" alt="norm" width="500" class="center" />

### Satz (ohne Beweis)

#### Norm vom Skalarprodukt

Es sei $(V,\langle, \rangle)$ ein euklidischer oder unitärer Vektorraum. Dann ist die Funktion $\parallel\parallel:V\to\Bbb{R}$ definiert durch
$$
\begin{aligned}
\parallel v\parallel=\sqrt{\langle v, v \rangle} \ \ \ \ & \forall v \in V
\end{aligned}
$$
eine Norm.

##### Beispiel

$\Bbb{R}^2$ mit Standardskalarprodukt $\ \ \leadsto \ \ \parallel\begin{pmatrix}
   x\_1 \newline
   x\_2 
\end{pmatrix} \parallel = \sqrt{x\_1^2+x\_2^2}$
<img src="/postImage/Normen/norm.png" alt="norm" width="300" class="center" />

#### Cauchy-Schwarz Ungleichung

In einem euklidischen oder unitären Vektorraum $(V,\langle,\rangle)$ gilt $\forall a,b \in V$:
$$
| \langle a,b \rangle | ^2 \le \langle a,a \rangle \langle b,b \rangle
$$
Gleichheit gilt genau dann, wenn $a$ und $b$ linear abhängig sind.

#### Parallelogramm-Identität

1. Sei $(V,\langle,\rangle)$ ein euklidischer oder unitärer Vektorraum mit zugehöriger Norm $\parallel\parallel$. Dann gilt die __Parallelogramm-Identität__, d.h. $\forall a,b \in V$ ist
$$
\parallel a+b\parallel^2 + \parallel a -b\parallel^2 = 2\parallel a\parallel^2+2\parallel b\parallel^2
$$

2. Ist umgekehrt $\parallel\parallel$ eine Norm auf einem reellen Vektorraum $V$, die Parallelogramm-Identität erfüllt, so existiert ein Skalarprodukt $\langle,\rangle$ auf $V$ mit $\parallel a \parallel = \sqrt{\langle a,a\rangle}$ für alle $a \in V$

#### Eigenschaften der Winkelfunktion
$\forall a,b \in V\setminus\\{0\\}$ und alle $\alpha,\beta\in\Bbb{R}\setminus\\{0\\}$ gilt:
$$
\omega(a,b)=\omega(b,a)
$$
$$
\omega(\alpha a,\beta b) =\begin{cases}
\omega(a,b) & \text{für} & \alpha\beta \gt 0 \newline
\pi - \omega(a,b) & \text{für} & \alpha\beta \lt 0
\end{cases}
$$
$$
\omega(a,b)=0\ \ \ \ \Leftrightarrow\ \ \ \ b=\lambda a \ \ \text{für ein} \ \ \lambda \gt 0
$$
$$
\omega(a,b) = \pi\ \ \ \ \Leftrightarrow\ \ \ \ b =\lambda a \ \ \text{für ein}\ \ \lambda \lt 0 
$$