---
title: Skalarprodukte
date: 2019-11-08T16:06:25+01:00
draft: false
math: true
tags: ["linear algebra","math"]
---

这章节的目的，是在实数和复数的向量空间里定义一些几何的概念譬如：长度，角度，垂直。 这里我们需要一种全新的结构，叫做 "Skalarprodukt".

## Theorie

---

在这里我们将在实数和复数空间里理解这种 Skalarprodukt 的结构， Skalarprodukt 在实数和复数空间里的处理方式是不同的。

### Euklidischer Vektorraum

+ Es sei $V$ ein _reeller_ Vektorraum. Eine __Bilinearform__ auf $V$ ist eine Abbildung $$F:V \times V \to \Bbb{R}\ \ \ \ \ \ (a,b)\mapsto F(a,b)$$ die in jedem Argument linear ist; d.h. $\forall x,y,z \in V \text{ und alle }\lambda\ \in \Bbb{K}$ gilt:
$$
\begin{aligned}
  F(x+y,z)= F(x,z)+F(y,z) \newline
  F(x,y+z)=F(x,z)+F(y,z) \newline
  F(\lambda x,y) = \lambda F(x,y) \newline
  F(x,\lambda y) = \lambda F(x,y)
\end{aligned}
$$
Die Menge aller Bilinearformen auf $V$ bezeichnen wir mit $Bil(V)$.

---

+ Eine Bilinearform $F$ heißt __symmetrisch__, wenn gilt: $$\forall a,b \in V: \ \ \ \ F(a,b)=F(b,a)$$

+ Eine Bilinearform $F$ auf $V$ heißt __positiv definit__, wenn gilt: $$Skalarprodukte(Forts.)\ \forall a\in V: F(a,a) \ge 0\ \ \land\ \ F(a,a)=0 \Leftrightarrow a=0$$

+ Eine Bilinearform $F$ heißt __schiefsymmetrisch__, falls $$\forall x,y \in V:\ \ \ \ F(x,y) = -F(y,x)$$

+ Eine Bilieanrform $F$ heißt __alternierend__, falls
$$
\forall x \in V:\ \ \ \ F(x,x) = 0
$$

---

+ Ein __Skalarprodukt__ auf einem reellen Vektorraum $V$ ist 
  1. positiv definite
  2. symmetrische Bilinearform auf $V$

+ Das __Standardskalarprodukt__ zweier Vektoren
$$
x=\begin{pmatrix}
  x\_1 \newline
  \ldots \newline
  x\_n
\end{pmatrix},
y=\begin{pmatrix}
  y\_1 \newline
  \ldots \newline
  y\_n 
\end{pmatrix}
$$
ist definiert durch
$$
\begin{aligned}
\langle x,y \rangle := x^\top \cdot y = x\_1y\_1 + x\_2y\_2+\ldots+x\_ny\_n \newline
\text{ in $\Bbb{C}^n$ bzw. } = x^\top \cdot \overline{y} =x\_1\overline{y\_1}+x\_2\overline{y\_2} +\ldots+x\_n\overline{y\_n}
\end{aligned}
$$

+ Ein Paar $(V,F)$ bestehend aus einem reellen Vektorraum und einem Skalarprodukt $F$ auf $V$ heißt __euklidischer Vektorraum__.

#### NOTATION

Für ein Skalarprodukte $F$ in einem euklidischen oder unitären Vektorraum $V$ schreiben wir $$\langle a,b \rangle := F(a,b)\ \ \ \ (a,b\in V)$$

---



### Unitäre Vektorräume

+ Für eine komplexe Zahl $z=x+iy\in \Bbb{C}$ und ihre komplex __Konjugierte__ $\tilde{z}=x-iy$ ist
$$
z^2=zz=(x+iy)(x+1y)=(x^2-y^2)+2ixy\in \Bbb{C}\ \ \ \text{hingegen}
$$
$$
z\tilde{z}=(x+iy)(x-iy)=x^2+y^2 \in \Bbb{R}
$$

+ Es sei $V$ ein _komplexer_ Vektorraum. Eine Abbildung $$F: V \times V \to \Bbb{C}\ \ \ \ \ (a,b)\mapsto F(a,b)$$ heißt __Sesquilinearform__ , wenn $\forall x,y,z \in V$ und $\forall \lambda \in \Bbb{C}$ gilt: 
$$
\begin{aligned}
F(x+y,z)&=F(x,z)+F(y,z) \newline
F(x,y+z) &= F(x,y) + F(x,z) \newline
F(\lambda x,y)& = \lambda F(x,y) \newline
F(x,\lambda y) &= \overline{\lambda}F(x,y)
\end{aligned}
$$

+ Eine Sesquilinearform $F$ heißt __hermitesch__, falls $\forall x,y \in V$ gilt
$$
F(x,y) = \overline{F(y,x)}
$$

+ Eine hermitesche Form $F$ in einem komplexen Vektorraum $V$ heißt __positiv definit__, wenn gilt: $$\forall a \in V : F(a,a) \ge 0\ \ \land \ \ F(a,a) = 0 \Leftrightarrow a= 0$$

+ Ein __unitäres Skalarprodukt__ ist eine positiv definite, hermitesche Form $F$. Ein Paar $(V,F)$ bestehend aus einem komplexen Vektorraum und einem Skalarprodukt $F$ heißt __unitärer Vektorraum__.

---

+ Sei $s \in Sym(V)$ eine __symmetrische__ Bilinearform. Die Menge
$$
rad(s):=\\{v\_0 \in V | s(v\_0,w)=0 \forall w \in V\\}
$$
heißt __Radikal__ (oder auch __Kern__) von $s$. Weiter heißt $s$ __ausgeartet__ falls
$$
rad(s)\neq \\{0\\}
$$

### Satz (ohne Beweis)

#### Elementare Eigenschaften einer hermiteschen Form

Sei $F$ eine hermitesche Form auf einem komplexen Vektorraum $V$. $\forall a,b\_1,b\_2 \in V$ und $\forall \mu\_1,\mu\_2 \in \Bbb{C}$ gilts:
  
  1. $F(a,\mu\_1b\_1+\mu\_2b\_2) = \overline{\mu\_1}F(a,b\_1) + \overline{\mu\_2}F(a,b\_2)$
  2. $F(a,a)  \in \Bbb{R},\ \ \ \ F(0,0) = 0$

### Cauchy-Schwarzsche Ungleichung

Ist $(V,\langle\rangle)$ ein euklidischer Vektorraum, so gilt $\forall x,y \in V$
$$
\langle x,y\rangle^2 \le \langle x,x\rangle \cdot\langle y,y\rangle
$$
Gleichheit gilt genau dann, wenn $x$ und $y$ linear abhängig sind.

### Bemerkung

Eine Abbildung $s:V\times V \to K$ ist genau dann eine Bilinearform, wenn $\forall x\in V$ die Abbildungen $s(x,\cdot):V\to K$ und $s(\cdot,x):V\to K$ Linearformen sind.

$Bil(V)$ ist Untervektorraum des $K$-Vektorraums $Abb(V\times V,K)$.
