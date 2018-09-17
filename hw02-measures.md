---
title: Measure Spaces
author: Colton Grainger (MATH 6130 Analysis)
date: 2018-09-16
bibliography: /home/colton/Downloads/coltongrainger.bib
macros: true
---

\setcounter{section}{1}

## Assignment due 2018-09-26

### Finite coverings of a measure space

Let $\{E_i\}_{i=1}^n$ be a finite sequence of measurable subsets of the measure space $(X, \sM, \mu)$, where $\mu(X) = 1$. If each point of $X$ belongs to at least three of these sets, then at least one of the $E_i$ has measure $\geq \frac3n$.

### Equivalence relations on a finite space [@Fo99, number 2.12]

Let $(X, \sM, \mu)$ be a finite measure space.

(a) If $E, F \in \sM$ and $\mu(E\Delta F)=0$, then $\mu(E) = \mu(F)$.
(b) Say that $E \sim F$ iff $\mu(E \Delta F) = 0$: then $\sim$ is an equivalence relation on $\sM$.
(c) If $E, F \in \sM$, define $\rho(E,F) = \mu(E \Delta F)$. Then $\rho(E,G)\le \rho(E,F) + \rho(F,G)$ for all $E,F,G \in \sM$, and hence $\rho$ defines a metric on the quotient space $\sM/\sim$.

### Large sets in semifinite measures [@Fo99, number 2.14] 

If $\mu$ is a semifinite measure and $\mu(E) = \infty$, then for any $C > 0$ there exists $F \subset E$ with $C < \mu(F) < \infty$.

### Semifinite parts [@Fo99, number 2.15]

If $\mu$ is a measure on $(X, \sM)$, define $\mu_0$ on $\sM$ for each $E \subset X$ by $$\mu_0(E) = \sup\{\mu(F) : F \subset E \text{ and } \mu(F) \le \infty\}.$$

(a) $\mu_0$ is a semifinite measure.^[It's called the **semifinite part** of $\mu$.]
(b) If $\mu$ is semifinite, then $\mu_0 = \mu$.

### Countable additivity for intersections in outer measures [@Fo99, number 2.17]

If $\mu^*$ is an outer measure and $\{A_j\}_1^\infty$ is a sequence of disjoint $\mu^*$-measurable sets, then $\mu^*(E \cap (\cup_1^\infty A_j)) = \sum_1^\infty \mu^*(E\cap A_j)$ for any $E \subset X$.

### [@Fo99, number 2.18]

Let $\sA \subset \sP(X)$ be an algebra, $\sA_\sigma$ the collection of countable unions of sets in $\sA$, and $\sA_{\sigma\delta}$ the collection of countable intersections of sets in $\sA_\sigma$. Let $\mu$ be a premeasure on $\sA$ and $\mu^*$ the induced outer measure.

(a) For any $E \subset X$ and $\epsilon > 0$ there exists $A \in \sA_\sigma$ with $E \subset A$ and $\mu^*(A) \le \mu^*(E) + \epsilon$.
(b) If $\mu^*(E) < \infty$, then $E$ is $\mu^*$ measurable iff there exists $B \in \sA_{ \sigma\delta }$ with $E \subset B$ and $\mu^*(B\setminus E) = 0$.
(c) If $\mu$ is $\sigma$-finite, the restriction $\mu^*(E) <\infty$ in (b) is superfluous.

### [@Fo99, number 2.19]

Let $\mu^*$ be an outer measure on $X$ induced from a premeasure, such that $\mu^*(X) < \infty$. If $E \subset X$, define the inner measure of $E$ to be $\mu_*(E) = \mu^*(X) - \mu^*(E^c)$. Then $E$ is $\mu^*$-measurable iff $\mu^*(E) = \mu_*(E)$.

### [@Fo99, number 2.22]

Let $(X, \sM, \mu)$ be a measure space, $\mu^*$ the outer measure induced by $\mu$ according to $$\mu^*(E) = \inf\left\{\sum_1^\infty\mu(A_j): A_j \in \sA, E \subset \bigcup_1^\infty A_j\right\},$$ and $\sM^*$ the $\sigma$-algebra of $\mu^*$-measurable sets, and $\tilde{\mu} = \mu^* | \sM^*$.

(a) If $\mu$ is $\sigma$-finite, then $\tilde{\mu}$ is the completion of $\mu$.

### [@Fo99, number 2.23]

Let $\sA$ be the collection of finite unions of sets of the form $(a,b] \cap \QQ$ with $-\infty \le a\le b \le \infty$. 

(a) Knowing "if $\sE$ is an elementary family, the collection $\sA$ of finite disjoint unions of members of $\sE$ is an algebra" we have that $\sA$ is an algebra of $\QQ$.

## References
