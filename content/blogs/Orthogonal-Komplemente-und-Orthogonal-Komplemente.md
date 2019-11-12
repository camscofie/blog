---
title: "Orthogonal Komplemente und Orthogonal-Projektionen"
date: 2019-11-12T17:42:21+01:00
draft: false
math: true
flags: ["linear algebra","math"]
---

Ist $V$ ein Vektorraum und $U \subset V$ ein Untervektorraum, so hat $U$ im Allgemeinen viele Komplementärräume. Ist hingegen $(V, \langle,\rangle)$ ein euklidischer oder unitärer Vektorraum, so gibt es ein “kanonisches” Komplement.

## Theorie

### Definition

+ Die Menge
$$
U^\bot := \\{x\in V\ |\ \langle x,u\rangle = 0\ \ \ \forall u\in U\\}
$$
heißt __Orthogonal-Komplement__ von $U$ in $V$.

---

+ Ist $M\subset V$ eine Teilmenge von Vektoren in $V$, so heißt
$$
M^\bot := \\{x\in V\ |\ x\bot M\\} = \\{x\in V\ |\ \langle x,y\rangle=0\ \ \ \ \forall y\in M\\}
$$
das __orthogonale Komplement__ von $M$ in $V$.

---

+ Die __Orthogonalprojektion__ von $V$ auf $U$ (in Richtung $U^\bot$) ist die Abbildung:
$$
\pi\_U:V\to U\subset V,\ v=u+u^\bot\mapsto u
$$
<img src="/postImage/Orthogonal_Komplemente/Orthogonalprojektion.png" alt="Orthogonalprojektion" width="500" class="center" />

---

+ $V$ Vektorraum mit Skalarprodukt, $U \subset V$ endlich dimensionaler Untervektorraum.
Für $v\in V$ heißt $\pi\_U(v)$ __Lotfußpunkt__ von $v$ auf $U$, und $v-\pi\_U(v)\in U^\bot$ das __Lot__ (oder der __Lotvektor__) von $v$ auf $U$.
<img src="/postImage/Orthogonal_Komplemente/Lotvektor.png" alt="lotvektor" width="500" class="center" />

---

#### Abstand eines Vektors zu einem Untervektorraum

+ Seien $(M,d)$ ein metrischer Raum und $A,B \subset M$ zwei Teilmengen. Der __Abstand__ von $A$ und $B$ ist definiert durch
$$
d(A,B):= \inf\\{d(a,b)\ |\ a\in A,b\in B\\}
$$
Ist jetzt $V$ ein Vektorraum mit Skalarprodukt, so ist $V$ ein normierter und damit ein metrischer Raum mit Metrik $d(v,w)=\parallel v-w\parallel$. Für $v\in V$ und einen Untervektorraum $U$ wollen wir den Abstand von $v$ und $U$ bestimmen, also
$$
d(\\{v\\},U)=\inf\\{\parallel v-u\parallel\ |\ u\in U\\}
$$
Man beachte, dass die Menge der reellen Zahlen $\parallel v-u$ mit $u\in U$ nach unten durch $0$ beschränkt ist; das Infimum existiert also (das gilt ganz allgemein, da eine Metrik positiv ist).

### Satz(ohne Beweis)

Sind $N,M \subset V$ Teilmengen mit $\emptyset\neq N\subset M$, so gilt

1. $M^\bot \subset N^\bot$

2. $M^\bot$ ist ein Untervektorraum von $V$

3. $\langle M\rangle^\bot = M^\bot$

4. $\langle M \rangle \subset (M^\bot)^\bot$

---

Das Orthogonal-Komplement $U^\bot$ eines Untervektorraumes $U$ eines euklidischen oder unitären Vektorraumes $V$ hat folgende Eigenschaften:

1. $U^\bot$ ist Untervektorraum von $V$

2. $U \cap U^\bot = \\{0\\}$

3. $U \subset (U^\bot)^\bot$

4. Ist $V$ endlich-dimensional, so gilt $U \oplus U^\bot = V$ und $(U^\bot)^\bot = U$

Für __unendlich dimensionale__ Untervektorräume $U\subset V$ ist im Allgemeinen $U \oplus U^\bot \subsetneq V$ und $U\subsetneq (U^\bot)^\bot$.

---

#### Eigenschaften der Orthogonalprojektoin

Für die Orthogonalprojektion $\pi\_U$ eines Vektorraumes $V$ auf einen Untervektorraum $U$ gilt:

1. $\pi\_U$ ist linear und $\pi\_U^2 = \pi\_U \circ \pi\_U = \pi\_U$.

2. Bild $\pi\_U=U$, Kern $\pi\_U=U^\bot$.

3. $\pi\_U$ verkürzt Abstände: Für alle $v,w\in V$ ist
$$
d(\pi\_U(v),\pi\_U(w))=\parallel\pi\_U(v)-\pi\_U(w)\parallel\le\parallel v-w\parallel=d(v,w)
$$

4. $\parallel\pi\_U(v)\parallel\le\parallel v\parallel$ für alle $v\in V$.

---

#### Kürzester Abstand

Es seien $V$ ein endlich-dimensionaler euklidischer oder unitärer Vektorraum und $U$ ein Untervektorraum. Weiter sei $V$ zerlegt als $V=U\oplus U^\bot$. Dann gilt für $v=u+u^\bot \in V$ die Gleichung:
$$
d(\\{v\\},U)=\min\\{\parallel v-u^{\ast}\parallel\ |\ u^\ast \in U\\}= \parallel u^\bot\parallel=\parallel\pi\_{U^\bot}(v)\parallel
$$
<img src="/postImage/Orthogonal_Komplemente/Abstand.png" alt="abstand" width="600" class="center" />
