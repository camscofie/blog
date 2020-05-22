---
title: "SAT"
date: 2020-05-22T02:08:20+02:00
draft: false
math: true
tags: ["TGI"]
---

## Definition von SAT

Sei $U = \\{u\_1,\dots,u\_m\\}$ eine Menge von booleschen Variablen. ($u\_i,\overline{u\_i}$ heißen __Literale__). Eine __Wahrheitsbelegung__ für $U$ ist eine Funktion $t:U\to \\{\text{wahr, falsch}\\}.$ Eine __Klausel__ ist ein Boole'scher Ausdruck der Form
$$
y\_1 \vee \dots \vee y\_s \text{   mit   } y\_i \in \underbrace{\\{u\_1,\dots,u\_m \\} \cup \\{\overline{u\_1},\dots,\overline{u\_m}\\}}\_{\text{Literalmenge}}\cup\\{\text{wahr, falsch}\\}
$$

#### Dann ist SAT wie folgt definiert:

+ Gegeben: Menge $U$ von Variablen. Menge $C$ von Klauseln über $U$

+ Frage: Existiert eine Wahrheitsbelegung von $U$, so dass $C$ erfüllt wird, d.h. dass alle Klauseln aus $C$ den Wahrheitsbelegung $t(u\_1)=t(u\_2) = \text{wahr}$ wird $C$ erfüllt.

+ Beispiel: $U=\\{u\_1,u\_2\\}$ mit $C = \\{u\_1\vee\overline{u\_2},\overline{u\_1}\vee u\_2\\}$ ist Ja-Beispiel von SAT. Mit der Wahrheitsbelegung $t(u\_1)=t(u\_2) =\text{wahr}$ wird $C$ erfüllt.

## Satz (von Steven Cook 1971)
$$
\text{SAT ist   } \mathcal{NP}\text{-vollständig.}
$$

#### Beweis:

1. SAT $\in \mathcal{NP}$ ist offensichtlich erfüllt, denn für ein Beispiel $I$ von SAT (mit $n$ Klauseln und $m$ Variablen) und einer Wahrheitsbelegung $t$ kann in $O(m\cdot n)$ überprüft werden, ob $t$ alle Klauseln erfüllt, d.h. ob $I$ ein Ja-Beispiel ist.

2. Wir müssen zeigen, dass für jede Sprache $L\in\mathcal{NP}$