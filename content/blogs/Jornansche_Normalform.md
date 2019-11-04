---
title: "若尔当标准型"
date: 2019-11-03T20:21:59+01:00
draft: false
tags: ["linear algebra","math"]
---

把矩阵转化成对角矩阵非常方便我们进行大次方的矩阵运算，但并非所有的矩阵都能对角化。这里我们把不能对角化的矩阵转化为若尔当标准型。

## 例子

已知矩阵 $B \in \mathbb{C}^6$:

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

### 步骤：

----------

#### 第一步

+ 算出 Eigenwerte ， 这里我们用charakteristische Polynom $ p = det(B - X \cdot E)$

得到 $ p = (3 - X)^6$ , 所以得到 $\lambda=3$ 是唯一的Eigenwert。根据Satz(17.8 Enrico Leuzinger) 我们只有一个 Hauptraum $H_\lambda$ ，并且只有一个Jordan-Block $A_3$ 出现


#### 第二步

+ 为了确认$A_3$，先算出 Hauptraum $H_3$ 的 Index $q$

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

#### 第三步

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
K_2 = \left[
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

#### 第四步

+ 找到各个 $K_k$ 的 Kette verschachtelter Untervektorräume $ K_1 \subset K_2 \subset K_3 = H_3$

##### 第一小步

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

##### 第二小步

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

##### 第三小步

+ 从 $(\Phi-3id)(U_1) \subset K_1$确定 $K_1$ 的Basis

因为两个Basis 可以直接从 $(\Phi-3id)^2(b_2^1)$ 和 $(\Phi-3id)(b_1^1)$ 中找到。所以三个维度的 $K_1$ 有一个Basisvector $b_0^1$ 可选：

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
   (\Phi-3id)(b_2) = (\Phi-3id)^2(b_2^1) = b_1 \qquad  \Rightarrow \Phi(b_2) =b_1 + 3 \cdot b_1 \newline
   (\Phi-3id)(b_3) = (\Phi-3id)(b_2^1) = b_2 \qquad \Rightarrow \Phi(b_3) =b_2+ 3 \cdot b_1 \newline
   (\Phi-3id)(b_4) = (\Phi-3id)^2(b_1^1) = 0 \qquad \Rightarrow \Phi(b_4) = 3 \cdot b_1 \newline
   (\Phi-3id)(b_5) = (\Phi-3id)(b_1^1) = b_4 \qquad 
    \Rightarrow \Phi(b_5) =b_4+ 3 \cdot b_5 \newline
   (\Phi-3id)(b_6) = (\Phi-3id)(b_1^1) = 0 \qquad  \Rightarrow \Phi(b_6) = 3 \cdot b_6
\end{matrix}
$$

最后我们按照 Basis $(b_1, \ldots ,b_6 )$ 这样排练，我们就能得到Jordanscher Normalform：

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