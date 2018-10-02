---
title: Midterm 1 review 
author: Colton Grainger
date: 2018-10-01
revised:
bibliography: /home/colton/Downloads/coltongrainger.bib
macros: yes
---


## Revisions

### Closure under countable increasing unions [@Fo99, number 1.4]

An algebra $\sA$ is an $\sigma$-algebra iff $\sA$ is closed under countable increasing unions.
That is, $$\text{if } \{E_j\}_1^\infty \subset \sA \text{ and } E_1 \subset E_2 \subset \cdots, \text{ then } \cup_1^\infty \in \sA.$$

### Linear combinations of measures [@Fo99, number 1.7]

If $\mu_1,\ldots,\mu_n$ are measures on $(X, \sM)$ and $a_1, \ldots,a_n \in [0,\infty)$, then $\sum_1^n a_j \mu_j$ is a measure on $(X,\mu)$.

### Summing sets by union and intersection [@Fo99, number 1.9]

If $(X, \sM, \mu)$ is a measure space and $E, F \in \sM$, then $$\mu(E) + \mu(F) = \mu(E\cup F) + \mu(E\cap F).$$

### A measure relative to set intersection [@Fo99, number 1.10]

If $(X, \sM, \mu)$ is a measure space and $E \in \sM$, define $$\mu_E(A) = \mu(A \cap E) \text{ for all } A \in \sM.$$
Then $\mu_E$ is a measure.

### [@Fo99, number 1.18]

Let $\sA \subset \sP(X)$ be an algebra, $\sA_\sigma$ the collection of countable unions of sets in $\sA$, and $\sA_{\sigma\delta}$ the collection of countable intersections of sets in $\sA_\sigma$. Let $\mu$ be a premeasure on $\sA$ and $\mu^*$ the induced outer measure.

(a) For any $E \subset X$ and $\epsilon > 0$ there exists $A \in \sA_\sigma$ with $E \subset A$ and $\mu^*(A) \le \mu^*(E) + \epsilon$.
(b) If $\mu^*(E) < \infty$, then $E$ is $\mu^*$ measurable iff there exists $B \in \sA_{ \sigma\delta }$ with $E \subset B$ and $\mu^*(B\setminus E) = 0$.
(c) If $\mu$ is $\sigma$-finite, the restriction $\mu^*(E) <\infty$ in (b) is superfluous.

### [@Fo99, number 1.19]

Let $\mu^*$ be an outer measure on $X$ induced from a premeasure, such that $\mu^*(X) < \infty$. If $E \subset X$, define the inner measure of $E$ to be $\mu_*(E) = \mu^*(X) - \mu^*(E^c)$. Then $E$ is $\mu^*$-measurable iff $\mu^*(E) = \mu_*(E)$.

### [@Fo99, number 1.22]

Let $(X, \sM, \mu)$ be a measure space, $\mu^*$ the outer measure induced by $\mu$ according to $$\mu^*(E) = \inf\left\{\sum_1^\infty\mu(A_j): A_j \in \sA, E \subset \bigcup_1^\infty A_j\right\},$$ and $\sM^*$ the $\sigma$-algebra of $\mu^*$-measurable sets, and $\tilde{\mu} = \mu^* | \sM^*$.

(a) If $\mu$ is $\sigma$-finite, then $\tilde{\mu}$ is the completion of $\mu$.

### [@Fo99, number 1.23]

Let $\sA$ be the collection of finite unions of sets of the form $(a,b] \cap \QQ$ with $-\infty \le a\le b \le \infty$. 

(a) Knowing "if $\sE$ is an elementary family, the collection $\sA$ of finite disjoint unions of members of $\sE$ is an algebra" we have that $\sA$ is an algebra of $\QQ$.

## Example sheet

\section{Problems to prove}

\begin{description}

\item[Packer] Let $A$ and $B$ be subsets of $\mathbf{R}$ with $A \subset B$. Using the definition of Lebesgue outer measure, prove the monotonicity property of outer measure, i.e., show $m^*(A) \le m^*(B)$.
\item[Packer] Let $A \subset \mathbf{R}$ have finite outer measure, and suppose there exist an $F_\sigma$-set $F$ and a $G_\delta$-set $G$ with $F \subset A \subset G$ with $m(F) = m(G)$. Prove that $A$ is Lebesgue measurable.
\item[Packer] Let $E$ be measurable with $m(E) < \infty$. Prove that for every $\epsilon > 0$ there exists a finite collection of open intervals $\{I_i\}_{i=1}^n$ such that $m(E \Delta (\cup_{i=1}^n I_i)) < \epsilon.$
\item[Rudin] Let $(X, \mathscr{M}, \mu)$ be a measure space, let $\mathscr{M}^*$ be the collection of all $E \subset X$ for which there exist sets $A$ and $B$ in $\mathscr{M}$ such that $A \subset E \subset B$ and $\mu(B \setminus A) = 0$, and define $\mu(E) = \mu(A)$ in this situation. Prove $\mathscr{M}^*$ is a $\sigma$-algebra.
\end{description}

\section{Problems to find a counter example or prove}

For each of the following statements, determine whether it is true or false. 

If it is true, prove it. If it is false, give a counterexample (\emph{ein gegenbeispiel}).

\begin{description}
\item[Packer] If $F \subset [0,1]$ is Lebesgue measurable and $m(F) > 0$, then $F$ contains an open interval.
\item[Packer] Let $E$ be a subset of $\mathbf{R}$, and let $\chi_E \colon \mathbf{R} \to \{0,1\}$ denote the characteristic function of $E$. If $\chi_E$ is a Lebesgue measurable function, then $E$ is a Lebesgue measurable set.
\item[Rudin] Let $X$ be an uncountable set, let $\mathscr{M}$ be the collection of all sets $E \subset X$ such that either $E$ or $E^c$ is at most countable. Then $\mathscr{M}$ is a $\sigma$-algebra in $X$.
\item[Rudin] Suppose $F$ is a right-continuous increasing function on $[a,b]$. There is a positive Borel measure $\mu$ on $[a,b]$ for which $F(x) - F(a) = \mu((a,x))$.
\end{description}
