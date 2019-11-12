---
title: "Jordan Normalform"
date: 2019-11-03T20:21:59+01:00
draft: false
math: true
tags: ["linear algebra","math"]
---

把矩阵转化成对角矩阵非常方便我们进行大次方的矩阵运算，但并非所有的矩阵都能对角化。这里我们把不能对角化的矩阵转化为若尔当标准型。

In order to calculate Matrix with high power, it would be ideal to have them in diagonalization. But matrix, which doesn't have their geometrische Vielfachheit equals to its algebraische Vielfachheit, can be only transfered to Jordan Normalform.

## Theorie

### Definition

+ Für einen Eigenwert $\lambda$ von $\Phi$ und $j\in \Bbb{N}_0$ ist der $j-te$ __Kern__ $K_j(\lambda)$ definiert durch $$K_j(\lambda):= ker((\Phi-\lambda id_V)^j)$$ 

+ $v \in V\setminus{0}$ heißt  __Hauptvektor__ (oder __verallgemeinerter Eigenwektor__) von $\Phi$ zum Eigenwert $\lambda$, falls $j \in \Bbb{N}$ existiert mit $(\Phi - \lambda id_V)^j(v)$

+ Ist $q \le n$ die kleinste natürliche Zahl mit $K\_q = K\_{q+1}$ heißt $$H_\lambda := K_q = ker((\Phi - \lambda id_V)^q)$$ __Hauptraum__ (oder __verallgemeinerter Eigenraum__) von $\Phi$ zum Eigenwert $\lambda$; $q$ heißt __Index__ von $H_\lambda$.

+ Für den Untervektorraum $H_\lambda$ von $V$ ist der EndomorphismusX $$g : H\_\lambda \to H\_\lambda, v \mapsto (f - \lambda id\_V)(v)$$ __nilpotent__, das heißt es gibt $m \in \Bbb{N}$ mit $g^m = 0$.

+ Ist $H\_\lambda$ ein Hauptraum von $\Phi$ mit Index $q$, so ist $$B\_\lambda := Bild(\Phi - \lambda id\_V)^q$$ ein $\Phi-invariantes$ Komplement von $H\_\lambda$, das heißt $$V = H\_\lambda \oplus B\_\lambda, \Phi(B\_\lambda) \subset B\_\lambda$$
  
+ Sind $\lambda\_1,\lambda\_2,\ldots,\lambda\_k$ die verschiedenen Eigenwerte von $\Phi$ und $q\_1,q\_2,\ldots,q\_k$ die Indizes der Haupträumme $H\_{\lambda\_1},H\_{\lambda\_2},\ldots,H\_{\lambda\_k}$ so heißt das Polynom $$m\_\Phi = (X-\lambda\_1)^{q\_1}(X-\lambda\_1)^{q\_2}\ldots(X-\lambda\_1)^{q\_k}$$ __Minimalpolynom__ von $\Phi$.

### Satz (ohne Beweis)

#### Hauptraumzerlegung

Sind $\lambda\_1, \lambda\_2, \ldots,\lambda_k$ die paarweise verschiedenen Eigenwerte von $\Phi$, und ist $p\_\Phi=(-1)^n(X-\lambda\_1)^{r\_1}(X-\lambda\_2)^{r\_2} \ldots (X-\lambda\_k)^{r\_k}$ das charakteristische Polynom von $\Phi$, so gilt $$V = H\_{\lambda\_1} \oplus H\_{\lambda\_2} \oplus \ldots \oplus H\_{\lambda\_k}$$ und $dim H\_{\lambda\_i} = r\_i$ für $i \in \{1,2,\ldots,k\}$.

#### Jordanbasis

Bestimme eine passende Basis für jeden Hauptraum $H\_\lambda \subset V$. Sei $q \le r := dimH\_\lambda$ der Index von $H\_\lambda$, $g = \Phi - \lambda id\_V \in End(H\_\lambda)$. Es gilt $$H\_\lambda = U^{(q-1)} \oplus \ldots \oplus U^{(1)} \oplus U^{(0)}$$, wobei $U^{(j-1)}$ jeweils ein Komplement von $K\_{j-1}$ in $K\_j$ bezeichnet und aus Vektoren der Stufe $j$ bezüglich des nilpotenten Endomorphismus $g = \Phi - \lambda id\_V$ von $H\_\lambda$ besteht.

#### Folgerung

Wählt man entsprechend der Zerlegung $V = H\_{\lambda\_1} \oplus H\_{\lambda\_2} \oplus \ldots \oplus H\_{\lambda\_k}$ eine geordnete Basis $B$ von $V$, so gilt

$$
D\_{BB}(\Phi) = \begin{pmatrix}
A\_{\lambda\_1} & & && 0 \newline 
& A\_{\lambda\_2} &&& \newline   
&& \ldots && \newline
&&& \ldots & \newline
0 &&&& A\_{\lambda\_k}
\end{pmatrix}, A\_{\lambda\_i} \in \Bbb{C}^{r\_i \times r\_i} 
$$

+ Die Matrix $A\_\lambda$ heißt __Jordanblock__ zum Eigenwert $\lambda$.
+ Die Blockmatrizen innerhalb der Matrix $A\_\lambda$ heißen __Jordankästchen__.
+ Die Abbildungsmatrix von $\Phi$, die man erhält, wenn man in der Blockmatrix für jeden Eigenwert $\lambda\_i$ den entsprechenden Jordanblock $A\_{\lambda\_i}$ einsetzt, heißt __Jordansche Normalform__ von $\Phi$. Die zugehörige Basis von $V$ heißt __Jordanbasis__. 

#### Weitere Eigenschaften der Jordanschen Normalform

+ Die Anzahl der Kästechen in einem zum Eigenwert $\lambda\_j$ gehörigen Jordanblock ist die Dimension des Eigenraums $K\_1^j = Kern(\Phi-\lambda\_jid\_V)$.
+ Die Anzahl $\sigma\_h^j$ der $(h \times h)$-Kästchen in einem zum Eigenwert $\lambda\_j$ gehörigen Jordan-Block ist gegeben durch $$\sigma\_h^j = \tau^j\_{h-1} - 2\tau^j\_h + \tau^j\_{h+1}$$, wobei $j=1,2,\ldots,k$; $h=1,2,\ldots,q\_j$.
+ 
#### Jordansche Normalform

Ist V ein endlich dimensionaler Vektorraums über $\Bbb{C}$, und $\Phi \in End(V)$, so gibt es eine Basis von V bezuuglich der die darstellende Matrix von $\Phi$ die Jordansche Normalform von $\Phi$ ist. _Die Jordansche Normalform ist bis auf die Reihenfolge der Jordanblöcke eindeutig bestiemmt_.

#### Folgerung

Jede Matrix $A \in \Bbb{C}^{n \times n}$ ist ähnlich zu einer Matrix in Jordanscher Normalform. Die Ähnlichkeitsklasse von $A$ ist durch die Jordansche Normalform von $A$ eindeutig festgelegt.

## Praxis

ein Matrix $B \in \mathbb{C}^6$:

$$
B= \begin{pmatrix}
    0 & -1 & 0 & 0 & 0 & 0 \newline
    9 & 6 & 0 & 0 & 0 & 0 \newline
    -5 & -2 & -96 & -88 & -77 & 0 \newline
    10 & 4 & 135 & 123 & 105 & 0 \newline
    -5 & -2 & -27 & -24 & -18 & 0 \newline
    0 & 0 & 0 & 0 & 0 & 3
\end{pmatrix}
$$

### Steps：

----------

#### 1. Eigenwerte bestimmen

+ Eigenwerte bestimmen ， we use charakteristische Polynom $ p = det(B - X \cdot E)$

得到 $ p = (3 - X)^6$ , 所以得到 $\lambda=3$ 是唯一的Eigenwert。根据Satz(17.8 Enrico Leuzinger) 我们只有一个 Hauptraum $H\_3$。

#### 2. bestimmen Index of Hauptraum

+ 先算出 Hauptraum $H_3$ 的 Index $q$

$$
B -3E = \begin{pmatrix}
    -3 & -1 & 0 & 0 & 0 & 0 \newline
    9 & 3 & 0 & 0 & 0 & 0 \newline
    -5 & -2 & -99 & -88 & -77 & 0 \newline
    10 & 4 & 135 & 120 & 105 & 0 \newline
    -5 & -2 & -27 & -24 & -21 & 0 \newline
    0 & 0 & 0 & 0 & 0 & 0
\end{pmatrix}
$$

$$
(B-3E)^2= \begin{pmatrix}
    0 & 0 & 0 & 0 & 0 & 0 \newline
    0 & 0 & 0 & 0 & 0 & 0 \newline
    -3 & -1 & 0 & 0 & 0 & 0 \newline
    6 & 2 & 0 & 0 & 0 & 0 \newline
    -3 & -1 & 0 & 0 & 0 & 0 \newline
    0 & 0 & 0 & 0 & 0 & 0
\end{pmatrix}
$$

$$(B-3E)^3 = (B-3E)^4 = \ldots = 0$$

所以得出 $H_3$ 的 Index 是 $q=3$

#### 3. Untervektorräume $K_k$

+ 现在我们计算 Untervektorräume $K_k = Kern(\Phi -3 id)^k, k = 1,2,3$

因为$(B-3E)^3 = 0$ 所以 $K_3 = H_3 = \mathbb{C}^6$
经过计算：

$$
K_2 = \left[
    \begin{pmatrix}
    -1 \newline
    3 \newline
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    \end{pmatrix},
    \begin{pmatrix}
    0 \newline
    0 \newline
    1 \newline
    0 \newline
    0 \newline
    0 \newline
    \end{pmatrix},
    \begin{pmatrix}
    0 \newline
    0 \newline
    0 \newline
    1 \newline
    0 \newline
    0 \newline
    \end{pmatrix},
    \begin{pmatrix}
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    1 \newline
    0 \newline
    \end{pmatrix},
    \begin{pmatrix}
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    1 \newline
    \end{pmatrix}
    \right]
$$

$$
K_1 = \left[
    \begin{pmatrix}
    0 \newline
    0 \newline
    8 \newline
    -9 \newline
    0 \newline
    0 \newline
    \end{pmatrix},
    \begin{pmatrix}
    0 \newline
    0 \newline
    7 \newline
    0 \newline
    -9 \newline
    0 \newline
    \end{pmatrix},
    \begin{pmatrix}
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    1 \newline
    \end{pmatrix}
    \right]
$$

#### 4. Kette verschachtelter Untervektorräume

+ 找到各个 $K_k$ 的 Kette verschachtelter Untervektorräume $ K_1 \subset K_2 \subset K_3 = H_3$

##### 4.1

+ Hauptraum Zerlegung 

$$ H_3 = K_3 = U_2 \oplus K_2$$

因为 $K_3 = \mathbb{C}^6$，但是 $dim K_2 = 5$，所以 $dim U_2=1$， 我们现在需要选择一个在 $\mathbb{C}^6$ 但是不在 $K_2$ 里的Basis。我们选择
$$
B_2^1 = \begin{pmatrix}
    0 \newline
    1 \newline
    0 \newline
    0 \newline
    0 \newline
    0 \newline
\end{pmatrix},
U_2 = \left[
    \begin{pmatrix}
    0 \newline
    1 \newline
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    \end{pmatrix}
    \right]
$$

##### 4.2

+ 接着在 $K_2$ 下寻找下一个 Zerlegung，因为 $K_2 = U_1 \oplus K_1$
  
已知 $(\Phi - 3id)(b_2^1)\in K_2\setminus K_1$。 又因为 $dim K_2 =5, dim K_1 = 3$，所以 $dimU_1 =2$。所以我在组 $U_1$ 的Basis 时，先从 $(\Phi - 3id)(b_2^1)$取一个Basis，再从 $K_2 \setminus K_1$ (要保证linear unabhängigkeit)选择一个Basis。

$$
(\Phi-3id)(b_2^1) = \begin{pmatrix}
    -1 \newline
    3 \newline
    -2 \newline
    4 \newline
    -2 \newline
    0
\end{pmatrix}, 
b_1^1 = \begin{pmatrix}
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    1 \newline
    0
\end{pmatrix},
U_1 = \left[
  \begin{pmatrix}
    -1 \newline
    3 \newline
    -2 \newline
    4 \newline
    -2 \newline
    0
\end{pmatrix}, 
\begin{pmatrix}
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    1 \newline
    0
\end{pmatrix}
\right]
$$

##### 4.3

+ 从 $(\Phi-3id)(U_1) \subset K_1$确定 $K_1$ 的Basis

因为两个Basis 可以直接从 $(\Phi-3id)^2(b_2^1)$ 和 $(\Phi-3id)(b_1^1)$ 中找到。所以三个维度的 $U_0$ 有一个Basisvector $b_0^1$ 可选：

$$
(\Phi-3id)^2(b_2^1)=\begin{pmatrix}
    0 \newline
    0 \newline
    -1 \newline
    2 \newline
    -1 \newline
    0
\end{pmatrix},
(\Phi-3id)(b_1^1)=\begin{pmatrix}
    0 \newline
    0 \newline
    -77 \newline
    105 \newline
    -21 \newline
    0
\end{pmatrix},
b_0^1=\begin{pmatrix}
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    0 \newline
    1
\end{pmatrix}
$$

我们按以下顺序选择这些 Vector 作为 Jordanbasis:

$$
\begin{matrix}
    b1=(\Phi-3id)^2(b_2^1) & b2=(\Phi-3id)(b_2^1) & b3 = b_2^1 \newline
     & b4 =(\Phi-3id)(b_1^1) & b_5 = b_1^1 \newline
     & & b_6 = b_0^1
\end{matrix}
$$

因为
$$
\begin{matrix}
   (\Phi-3id)(b_1) = (\Phi-3id)^3(b_2^1) = 0 \qquad \Rightarrow \Phi(b_1) = 3 \cdot b_1 \newline
   (\Phi-3id)(b_2) = (\Phi-3id)^2(b_2^1) = b_1 \qquad  \Rightarrow \Phi(b_2) =b_1 + 3 \cdot b_2 \newline
   (\Phi-3id)(b_3) = (\Phi-3id)(b_2^1) = b_2 \qquad \Rightarrow \Phi(b_3) =b_2+ 3 \cdot b_3 \newline
   (\Phi-3id)(b_4) = (\Phi-3id)^2(b_1^1) = 0 \qquad \Rightarrow \Phi(b_4) = 3 \cdot b_4 \newline
   (\Phi-3id)(b_5) = (\Phi-3id)(b_1^1) = b_4 \qquad 
    \Rightarrow \Phi(b_5) =b_4+ 3 \cdot b_5 \newline
   (\Phi-3id)(b_6) = (\Phi-3id)(b_1^1) = 0 \qquad  \Rightarrow \Phi(b_6) = 3 \cdot b_6
\end{matrix}
$$

最后我们按照 Basis $(b_1, \ldots ,b_6 )$ 这样排列，我们就能得到Jordanscher Normalform：

$$
A = \begin{pmatrix}
   3 & 1 & 0 & & & \newline
   0 &3&1&&&0 \newline
   0&0&3&&& \newline
   &&&3&1& \newline
   &&&0&3& \newline
   &0&&&&3
\end{pmatrix}
$$


## Inverse Matrix P bestimmen

待补充