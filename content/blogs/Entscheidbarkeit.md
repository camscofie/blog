---
title: "Entscheidbarkeit"
date: 2020-06-19T19:07:55+02:00
math: true
tags: ["TGI"]
---

## 图灵机

一个deterministische Turing-Maschine ((D)TM) besteht aus:

+ $Q$, einer endlicher Zustandsmenge

+ $\Sigma$, einem endlichen Eingabealphabet,

+ $\sqcup$, einem Blanksymbol mit $\sqcup \notin\Sigma$

+ $\Gamma$, einem endlichen Bandalphabet mit $\Sigma\cup\\{\sqcup\\}\subseteq\Gamma$

+ $s\in Q$, einem Startzustand

+ $\delta: Q \times \Gamma \rightarrow Q \times \Gamma \times \\{L,R,N\\}$, einer Übergangsfunktion

+ $F \subseteq Q$, einer Menge von Endzuständen.(Die Menge der Endzustände kann auch entfallen)

## Entscheidbarkeit

+ 一个图灵机 __akzeptiert__ 一个 Eingabe $w \in \Sigma^*$, 当TM $M$ 读取$w$ 后停在一个 $z \in F$ 的位置。
  
+ 一个图灵机刚好 __akzeptiert__ 一个Sprache $L$， 当每个$w\in L$ 被该图灵机akzeptieren.

### 需要背诵

1. 一个语言 $L \subseteq \Sigma^*$ 叫做 __rekursiv__ 或者 __entscheidbar, 当存在一个为Sprache $L$ 设计的图灵机，该图灵机读取任何一个input 的时候都会停机，且会停在一个$z\in F$位置，当input $w\in L$.

2. 一个语言 $L \subseteq \Sigma^*$ 叫做 __rekursiv-aufzählbar__ 或者 __semi-entscheidbar__， 这个图灵机和上面一样会akzeptiert 任何 $w\in L$ 的input。但是当$w\notin L$时会不会停，会停在哪儿却都是未知的。

Gödelnummer 什么就是把整个TM 用二进制表示出来，细节就不说了，wiki 哪里都有。

### 需要背诵的Sprache

#### Das Post'sche Korrespondezproblem

这家伙不entscheidbar

#### DiagonalSprache

$$
L_d \rightleftharpoons \\{w_i \| M\_i \text{  akzeptiert  }w\_i\text{  nicht}\\}
$$

Diagonalsprache 是不entscheidbar 的。 证明别看了，全是抽象废话。


#### Haltproblem 和 universelle Sprache

我也不知道两个是不是一个问题，我觉得是一个问题。
$$
H \leftrightharpoons \\{wv\| T\_w\text{hält auf der Eingabe  } v\\}
$$
$$
L\_u \leftrightharpoons \\{wv\| v\in L(T\_w)\\}
$$

显而易见都不是entscheidbar，又都是semi-entscheidbar.

#### “xxx-Sprache 是不是entscheidbar”

证是entscheidbar 就靠智商了，证不是entscheidbar 全靠套路。套路很简单，把上面的一个不entscheidbar 的语言套进去，让xxx-Sprache 去entscheiden 一个由为不entsccheidbar 语言构成的图灵机伪装成的一个wort。一顿抽象废话操作，到最后绕出来就成了。

##### 问题一

Zeige: $L= \\{(u,v)\\}\|w\in L(T\_u) \Leftrightarrow w^R\in L(T\_v)\\}$ nicht entscheidbar.

__思路__: 这种定义看着都烦，啥都别管，这语言不是说能分辨$w\in L(T\_U)$ 吗。这就够了，直接把Haltproblem 的图灵机的Instance 藏进去。

1. 设$L$ 是entscheidbar，那就存在一个图灵机 $M\_L$ 可以akzeptiert $L$.

2. 把$M\_L$ 拿来entscheiden Haltproblem.
   1. 给一个Haltproblem 的Instance $\langle w,v\rangle$
   2. 把这个instance 伪装一下做成一个$M\_{WV}$:
      1. $M\_{WV}$ 给啥input 都不管，直接模拟$\langle w,v\rangle$ 时的Haltproblem
      2. $M\_{WV}$ akzeptiert 这个input，当里面的Haltproblem 停机了
      3. $L(M\_{WV}) = \Sigma^*$ 当$M\_{WV}$ 停机，反之则 $L(M\_{WV}) = \emptyset$ 
   3. 设计一个啥input 都akzeptiert 的 TM $M\_*$
   4. 那么这里$(\langle M\_{WV}\rangle,\langle M\_*\rangle)\in L \Leftrightarrow\langle w,v\rangle\in H$
3. $M\_L$ 来simulate Haltproblem, 一直haltproblem 是不entscheidbar 的，所以不存在这样一个图灵机$M\_L$.

##### 问题二

这里是关于 Postschen Korrespondenzproblem (PKP)，其中的Instance 为$I \subset \Sigma^* \times \Sigma^*$。 $\mathbb{G}$ 是所有kontextfreien Grammatiken 的集合。
$$
L = \\{\langle G\rangle\|G\in \mathbb{G}, \exists w\in L(G): w = w^R\\}
$$
证 $L$ 不是entscheidbar.

__思路__：$w=w^R$ 的模式，套PKP。

设 $I=\\{(x\_1,y\_1),(x\_2,y\_2)...\\}$ 是一个PKP instance。我们建立一个Grammatik $G$ 有
$$
R=\\{S\rightarrow x\_i S y\_i^R \| x\_i\sqcup y\_i^R\| i=1,2,...\\}
$$

这个就很直接了。设$L$ 是entscheidbar ，那么有$M\_L$ entscheidet $L$. 那么我们建立一个$M\_G$，可以entscheidet PKP。。。。各种各种。。哦了