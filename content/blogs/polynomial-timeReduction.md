---
title: "Polynomial-time Reduction"
date: 2020-06-19T13:45:23+02:00
math: true
tags: ["TGI"]
---

给出一个问题，问这个问题是不是$NP-vollständig$ 的？


### 证明思路

#### 1. 证这个问题是属于$NP$ 的：

1. eine potentielle Lösung der BBB-Problem können wir in einem polynomialen Algorithm prüfen.

2. Das BBB liegt in $NP$.

#### 2. 建立一个Reduktion: Ruduktion von AAA auf BBB-Problem:

1. Gegeben sei eine AAA-Instanz, wir konstruieren eine BBB-Instanz

2. Die Reduktion ist polynomiell
   
3. sodass die beiden Instanzen lösbarkeitsäquivalent sind.

#### 3. 证明 AAA $\Rightarrow$ BBB

给出一个AAA  的正确答案，那么正确答案被Reduktion 后也就是一个BBB 的正确答案

#### 4. 证明 BBB $\Rightarrow$ AAA

如上

#### 5. 总结一下废话

Da es außerdem in $NP$ liegt, folgt, dass das BBB Problem $NP-vollständig$ ist.
