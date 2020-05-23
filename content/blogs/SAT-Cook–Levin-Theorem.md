---
title: "(SAT) Boolean satisfiability problem - Cook Levin theorem"
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

2. Wir müssen zeigen, dass für jede Sprache $L\in\mathcal{NP}$ gilt: $L\propto L\_{\text{SAT}}$, wobei $L\_{SAT} = L\[SAT,s\]$ für ein geeignetes Kodierungsschema $s$ ist. Dazu muss für alle Sprachen $S \in \mathcal{NP}$ eine polynomiale Transformation $f\_{L}$ angegeben werden, für die gilt, dass für alle $x\in \sum^*$ gilt
$$
x\in \Leftrightarrow f\_{L}(x)\in L\_{SAT}
$$

Wir beötigen eine Konstruktion von $f\_{L}$, die zeigt, wie man die Überprüfung, ob eine nichtdeterministische Turing-Maschine $M$ zu $L$ ein Wort $x\in \sum^*$ akzeptiert, durch die Angabe von Klauseln simulieren kann. 

__点评__: 这个其实并不惊喜，可以这么想，现代计算机的底层都是逻辑门，而逻辑门就是用布尔代数来表示。那么所有的NP 问题既然可以用NDTM 表示，那就也可以被用SAT 表示。

__大致__: 如何才能说SAT 可以Polynomiale Transformation 到所有的 NP 问题呢，如果我们看NP 问题的核心，就是一个能被NDTM 在polynomial 时间内被解决的问题。而这里我们用预言机的图灵机模型来看NDTM，既给出Wahrheitsbelegung 的Orakel 模块和一个验证答案的DTM 模块。我们把某个NP 问题A 和能解决该问题的NDTM M只看作是一个给定input w 的图灵机运算，那么这个运算必然满足特定的条件：

1. 每个时间点i，M 都有且仅有一个Zustand。
2. 每个时间点i，图灵机指针有且仅有一个位置。
3. 每个时间i，turing band 有且仅有一个符号。
4. 有一个确定的Anfangskonfiguration。
5. 在p(n)内，M 能到$q\_{J}$
6. 从每个时间点i 到时间点 i+1 他的Konfiguration 都是根据定义的。

每个条件可以看作一个括号内的布尔表达式，称作Klauselgruppe 为了把上面的自然语言用布尔代数来表示，我们定义:

<img src="/postImage/SAT-Cook–Levin-Theorem/SAT-Cook–Levin-Theorem.png" alt="SAT" width="600" class="center" />

现在Klauselgruppe 1 的布尔代数式可以写成: 

+ Zu jedem Zeitpunkt $i$ ist $M$ in mindestens einem Zustand.

$$
Q[i,0]\vee\dots\vee Q[i,r]\text{       for }0\leq i\leq p(n)
$$

+ Zu jedem Zeitpunkt $i$ ist $M$ in nicht mehr als einem Zustand.

$$
\overline{Q[i,j]} \vee\overline{Q[i,j']} \text{    for } 0\leq i \leq p(n), o\leq j\leq j'\leq r
$$

这样就写出了Klauselgruppe 1 的布尔表达式，那之后的Klauselgruppe 也可以被布尔表达式表示出来。

