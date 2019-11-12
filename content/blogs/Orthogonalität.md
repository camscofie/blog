---
title: "Orthogonalität"
date: 2019-11-10T18:51:29+01:00
draft: false
math: true
flags: ["linear algebra","math"]
---

在线性空间里定义 “正交”

## Theorie

### Definition

+ Zwei Vektoren $x,y\in V$ heißen __orthogonal__ (oder __senkrecht__), falls
$$
\langle x,y\rangle = 0
$$
gilt; in diesem Fall schreiben wir $x \bot y$.

+ Zwei Teilmengen $N,M \subset V$ heißen __orthogonal__, falls $x\bot y$ für alle $x\in N$ und alle $y\in M$; man schreibt dann $N\bot M$.Besteht $N$ nur aus einem Element $x$, so schreiben wir auch $x\bot M$ anstelle von $\\{x\\}\bot M$.

+ Eine Teilmenge $M \subset V$ heißt __orthogonal__, wenn je zwei verschiedene Elemente von $M$ orthogonal sind.

+ Besteht $M$ zusätzlich nur aus Einheitsvektoren (wenn $\\{\parallel a\parallel=1 \ |\ \forall a\in M\\}$), so sprechen wir von einer __orthonormierten__ oder auch __orthonormalen__ Menge.

+ Eine Basis $B$ von $V$ heißt __Orthogonalbasis__, falls die Elemente von $B$ eine orthogonale Menge bilden. Sind außerdem alle Elemente von $B$ Einheitsvektoren so sprechen wir auch von einer __Orthonormalbasis__.
  
+ Im unitäre Vektorräume, zwei Vektoren $x,y \in V$ heißen __orthogonal__,falls $\langle x,y\rangle = 0$ gilt. Es folgt dann $\langle y,x\rangle = \overline{\langle x,y\rangle}=\overline{0}=0$

#### Bemerkung

+ Jede orthogonale Menge $M \subset V\setminus{\\{0\\}}$ ist linear unabhängig. 

+ Für den Nullvektor $0$ von $V$ gilt $0\bot M$;gilt umgekehrt $x\bot V$ für ein $x\in V$, so folgt $x=0$.

+ $x,y\in V\setminus\\{0\\}:\ \ x\bot y\ \ \ \ \Leftrightarrow\ \ \ \ cos(\omega(x,y))=0\ \ \ \ \Leftrightarrow\ \ \ \ \omega(x,y)=\pi/2$


### Satz (ohne Beweis)

#### Pythagoras

Für $x,y \in V$ gilt $x\bot y$ genau dann, wenn
$$
\parallel x+y\parallel^2=\parallel x\parallel^2+\parallel y\parallel^2
$$
<img src="/postImage/Orthogonalität/Pythagoras.png" alt="pythagoras" width="300" class="center" />

In einem euklidischen Vektorraum gilt auch die Umkehrung:

$$
\parallel x\parallel^2+\parallel y\parallel^2 = \parallel x+y\parallel^2 \ \ \ \ \Rightarrow \ \ \ \ x\bot y
$$

_aber gilt die Umkehrung nicht im unitären Raum !_

#### Kosinussatz

Für $x,y \in V\subset\\{0\\}$ gilt
$$
\parallel x-y\parallel^2 = \parallel x\parallel^2+\parallel y\parallel^2-2\parallel x\parallel\cdot\parallel y \parallel\cdot cos(\omega(x,y))
$$

<img src="/postImage/Orthogonalität/Kosinussatz.png" alt="kosinussatz" width="300" class="center" />

#### Wie konstruiert man eine Orthonormalbasis?
Seien $w,v \in V$. Normiere $w$ und erhalte dadurch $b:=\frac{w}{\parallel w\parallel}$. Es ist $\parallel v,b\parallel\cdot b$ genau der Anteil von $v$ in Richtung $b$, und für
$$
\tilde{c}:=v-\parallel v,b\parallel\cdot b
$$
gilt:
$$
\langle\tilde{c},b\rangle=\langle v-\langle v,b\rangle\cdot b,b\rangle= \langle v,b\rangle-\langle v,b\rangle\cdot\langle b,b\rangle=0
$$

### Gram-Schmidt Orthogonalisierung

Sei $C = \\{c\_1,c\_2,\ldots,c\_k\\}\subset V$ eine linaer unabhängige Menge. Berechne zwei Menge $\\{\tilde{b\_1},\tilde{b\_2},\ldots,\tilde{b\_k},\\},\\{b\_1,b\_2,\ldots,b\_k\\} \subset V$ nach folgender Vorschrift:

1. Setze $\tilde{b\_1} = c\_1$

2. Für $j-2,\ldots,k$ setze $\tilde{b\_j} = c\_j - \sum\_{i=1}^{j-1}\frac{\langle c\_j,\tilde{b\_i}\rangle}{\langle \tilde{b\_i},\tilde{b\_i}\rangle}\tilde{b\_i}$

3. Für $j=1,\ldots,k$ setze $b\_j=\frac{\tilde{b\_j}}{\parallel \tilde{b\_j}\parallel}$

Dann ist $\tilde{B}= (\tilde{b\_1},\tilde{b\_2},\ldots,\tilde{b\_k})$ eine Orthogonalbasis, und $B=(b\_1,b\_2,\ldots,b\_k)$ eine Orthonormalbasis von $\langle C\rangle$.

