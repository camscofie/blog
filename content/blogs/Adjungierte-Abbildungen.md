---
title: "Adjungierte Abbildungen"
date: 2019-11-13T16:45:11+01:00
draft: false
math: true
tags: ["linear algebra","math"]
---

## Theorie

### Definition

Es seien $(V,\langle,\rangle\_V)$ und $(W,\langle,\rangle\_W)$ zwei Vektorräume mit Skalarprodukt und $\Phi: V \to W$ eine lineare Abbildung. Eine lineare Abbildung $\Phi^\ast:W\to V$ heißt zu $\Phi$ __adjungierte lineare Abbildung__, falls für alle $x\in V$ und alle $y\in W$ gilt:
$$
\langle\Phi(x),y\rangle\_W=\langle x,\Phi^\ast(y)\rangle\_V
$$

#### NOTATION

Für eine Matrix $A=(a\_{ij})\in \Bbb{C}^{m\times n}$ definieren wir
$$
A^\ast=(a^\ast\_{ij}):=\overline{A}^\top=(\overline{a}\_{ji})\in \Bbb{C}^{n\times m}
$$

### Satz (ohne Beweis)

#### Existenz und Matrixform vom $\ \Phi^\ast$

Es seien $V,W$ zwei euklidische bzw. zwei unitäre Vektorräume. Dann gilt:

1. Ist $V$ endlich-dimensional, so existiert zu jeder linearen Abbildung $\Phi:V\to W$ genau eine Adjungierte $\Phi^\ast:W\to V$.

2. Es seien $V$ und $W$ beide endlich-dimensional. Weiter sei $B=\\{e\_1,\ldots,e\_n\\}$ eine Orthonormalbasis von $V$ und $C = \\{c\_1,\ldots,c\_m\\}$ eine Orthonormalbasis von $W$. Ist dann $A$ die Abbildungsmatrix von $\Phi^\ast:W\to V$ bezüglich der Basen $C,B$. Also $A^\ast=A^\top\in\Bbb{R}^{n\times m}$ im euklidischen Fall und $A^\ast = \overline{A}^\top\in\Bbb{C}^{n\times m}$ im unitären Fall.

### Bemerkung

Falls für die linearen Abbildungen $\Phi:U\to V$ und $\Psi:V\to W$ die Adjungierten $\Psi^\ast:V\to U,\Psi^\ast:W\to V$ existieren, so gelten folgende Beziehungen:
$$
\begin{aligned}
(\Phi+\Psi)^\ast & = \Phi^\ast+\Psi^\ast \newline
(\lambda\Psi)^\ast & = \overline{\lambda}\Phi^\ast\ (\lambda\in \Bbb{C}) \newline
(\Psi \circ \Phi)^\ast & = \Phi^\ast \circ \Psi^\ast\newline
\Phi^{\ast\ast} &=(\Phi^\ast)^\ast=\Phi \newline
\ker \Phi^\ast &=(\text{Bild}\Phi)^\bot   
\end{aligned}
$$