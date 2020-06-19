---
title: "Pseudopolynomiale Algorithmen"
date: 2020-05-25T15:59:05+02:00
math: true
tags: ["TGI"]
---

## Definiton

In der Komplexitätstheorie wird ein Algorithmus pseudopolynomiell genannt, wenn seine Laufzeit ein Polynom im numerischen Wert der Eingabe ist.


### 解释

一个Algo 时间复杂度，一般是指给一个input，然后运算时间是这个input 的几倍/平方或者怎么怎么样。

然而这种说法是不严谨的，准确的形容一个algo的时间复杂度，应该是以input 的length 为单位来说明与runtime 的关系的。想一想，比较两个数，$5$ 是不是等于 $8$，计算机并不会去比较这两个数是不是相等，而是会去比较这两个数的二进制的每个bit 是不是相等。

#### Pseudopolynomiale Algorithmus

Algo: 给出一个数 $n$, 请找随便这个数的两个因数，这眨眼一看时间复杂度好像是$O(n)$，因为从$2$开始遍历被$n$ 除就好。实际上这个algo 的时间复杂度并不是polynomial 的。

这个algo 的runtime 先看成是 $O(n)$。数$n$ 被计算机表示所需长度是 $O(\log n)$ bits. 用$x$ 来表示所需的bits 的位数即: $x = \log n \Rightarrow n = 2^x$。那我们algo 的runtime 也就上升到了$O(2^n)$，显而易见是一个exponential 已经不是polynomial 了，所以该algo 是一个Pseudopolynomiale Algorithmus!