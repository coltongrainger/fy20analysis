---
title: Midterm 1 review 
author: Colton Grainger
date: 2018-10-01
revised:
bibliography: /home/colton/Downloads/coltongrainger.bib
macros: yes
---

## Revisions

### [@Fo99, number 1.10]

If $(X, \sM, \mu)$ is a measure space and $E \in \sM$, define $\mu_E(A) = \mu(A \cap E) \text{ for all } A \in \sM.$ Then $\mu_E$ is a measure.

### [@Fo99, number 1.18]

Let $\sA \subset \sP(X)$ be an algebra, $\sA_\sigma$ the collection of countable unions of sets in $\sA$, and $\sA_{\sigma\delta}$ the collection of countable intersections of sets in $\sA_\sigma$. Let $\mu$ be a premeasure on $\sA$ and $\mu^*$ the induced outer measure.

(a) For any $E \subset X$ and $\epsilon > 0$ there exists $A \in \sA_\sigma$ with $E \subset A$ and $\mu^*(A) \le \mu^*(E) + \epsilon$.
(b) If $\mu^*(E) < \infty$, then $E$ is $\mu^*$ measurable iff there exists $B \in \sA_{ \sigma\delta }$ with $E \subset B$ and $\mu^*(B\setminus E) = 0$.
(c) If $\mu$ is $\sigma$-finite, the restriction $\mu^*(E) <\infty$ in (b) is superfluous.

### [@Fo99, number 1.19]

Let $\mu^*$ be an outer measure on $X$ induced from a premeasure, such that $\mu^*(X) < \infty$. If $E \subset X$, define the inner measure of $E$ to be $\mu_*(E) = \mu^*(X) - \mu^*(E^c)$. Then $E$ is $\mu^*$-measurable iff $\mu^*(E) = \mu_*(E)$.

### [@Fo99, number 1.22]

Let $(X, \sM, \mu)$ be a measure space, $\mu^*$ the outer measure induced by $\mu$ according to $$\mu^*(E) = \inf\left\{\sum_1^\infty\mu(A_j): A_j \in \sA, E \subset \bigcup_1^\infty A_j\right\},$$ and $\sM^*$ the $\sigma$-algebra of $\mu^*$-measurable sets, and $\tilde{\mu} = \mu^* | \sM^*$. If $\mu$ is $\sigma$-finite, then $\tilde{\mu}$ is the completion of $\mu$.

## Practice midterm 1

### Problems to prove

- Let $A$ and $B$ be subsets of $\mathbf{R}$ with $A \subset B$. Using the definition of Lebesgue outer measure, prove the monotonicity property of outer measure, i.e., show $m^*(A) \le m^*(B)$.
- Let $A \subset \mathbf{R}$ have finite outer measure, and suppose there exist an $F_\sigma$-set $F$ and a $G_\delta$-set $G$ with $F \subset A \subset G$ with $m(F) = m(G)$. Prove that $A$ is Lebesgue measurable.
- Let $E$ be measurable with $m(E) < \infty$. Prove that for every $\epsilon > 0$ there exists a finite collection of open intervals $\{I_i\}_{i=1}^n$ such that $m(E \Delta (\cup_{i=1}^n I_i)) < \epsilon.$
- Let $(X, \mathscr{M}, \mu)$ be a measure space, let $\mathscr{M}^*$ be the collection of all $E \subset X$ for which there exist sets $A$ and $B$ in $\mathscr{M}$ such that $A \subset E \subset B$ and $\mu(B \setminus A) = 0$, and define $\mu(E) = \mu(A)$ in this situation. Prove $\mathscr{M}^*$ is a $\sigma$-algebra. 

### Problems to prove or give a counter example

- Let $X$ be an uncountable set, let $\mathscr{M}$ be the collection of all sets $E \subset X$ such that either $E$ or $E^c$ is at most countable. Then $\mathscr{M}$ is a $\sigma$-algebra in $X$.
- Suppose $F$ is a right-continuous increasing function on $[a,b]$. There is a positive Borel measure $\mu$ on $[a,b]$ for which $F(x) - F(a) = \mu((a,x))$.

## Midterm 1

### Problems to prove or give a counter example

- If $F \colon \RR \to \RR$ is a monotone, increasing, right continuous function, and $\mu_F$ is the associated Borel measures on the Borel subsets of $\RR$, then for any bounded Borel subset $B \subset \RR$, $\mu_F(B) < \infty$.
- If $E$ is a subset of $\RR$, and has outer Lebesgue measure equal to $0$, then $E$ is countable.

### Problems to prove

- Let $(X, \sM, \mu)$ be a measure space, and let $\{E_n\}_{n=1}^\infty \subset \sM$ be an increasing sequence of measurable subsets of $X$. Prove continuity from below of the measure $\mu$, i.e., prove that $\lim_{k\to \infty} \mu(E_k) = \mu(\cup_{n=1}^\infty E_n)$.
