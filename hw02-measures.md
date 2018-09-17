---
title: Measure Spaces
author: Colton Grainger (MATH 6130 Analysis)
date: 2018-09-16
bibliography: /home/colton/Downloads/coltongrainger.bib
macros: true
---


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

## Assignment due 2018-09-26

### Finite coverings of a measure space

Let $\{E_i\}_{i=1}^n$ be a finite sequence of measurable subsets of the measure space $(X, \sM, \mu)$, where $\mu(X) = 1$. If each point of $X$ belongs to at least three of these sets, prove that at least one of the $E_i$ has measure $z$



Let $(X, \rho)$ be a metric space. We will show that balls in the metric space are open.

Take an arbitrary point in the space $x \in X$ and a radius $\eps > 0$. I claim $$\ball{\rho}{\eps,x} := \left\{ a \in X : \rho(a,x) < \eps \right\}$$ is open in $X$. 

Indeed, take a point $a \in \ball{\rho}{\eps,x}$ (note that $\rho(a,x) < \eps$). Now consider the radius $\delta = \eps - \rho(x,a) > 0$. We need to show the open ball $\ball{\rho}{\delta, a}$ containing the point $a$, is nested in within a radius $\eps$ of $x$, i.e., we need to show^[We denote "$X$ is a subset of $Y$" by $X \subset Y$ and "$Y$ is a proper subset of $Y$" by $X\subsetneq Y$.] $\ball{\rho}{\delta, a} \subset \ball{\rho}{\eps, x}$. Well, if $b \in \ball{\rho}{\delta, a}$, then $\rho(a,b) < \delta = \eps - \rho(x,a)$, with the triangle inequality we have $\rho(b,x) \leq \rho(a,b) + \rho(x,a) < \eps$, hence $b \in \ball{\rho}{\eps, x}$. 

So for every point $a$ in the open ball $\ball{\rho}{\eps,x}$ there's a nested open ball $\ball{\rho}{\delta, a}$ such that $a \in \ball{\rho}{\delta,a} \subset \ball{\rho}{\eps,x}$. By definition, $\ball{\rho}{\eps,x}$ is open.

### New metric spaces from old

Let $(X, d)$ be a metric space. Define $\rho \colon X \times X \to [0,\infty)$ by $$\rho(x,y) = \frac{d(x,y)}{1+d(x,y)}.$$ We'll show that $\rho$ is a metric on $X$.

*Key idea.* We have some transformation $f: [0,\infty) \to  [0,\infty)$ of the metric $d$ given by $f(d) = \frac{d}{1+d}$. Now $f$ is strictly monotone, so order preserving, and concave, so subadditive. We'll make repeated use of the property that $$\text{ if } c, k \in [0,\infty) \text{ and } c \leq k, \text{ we have } c(1+k) = c+ck \leq k +ck = k(1+c) \text{ whence } \frac{c}{1+c} \leq \frac{k}{1+k}.$$ We have equality iff $c=k$.

Now to show that $\rho$ is a metric, take three arbitrary points $x,y,z \in X$.

- We have $y=x$ iff $d(x,y) = 0$ iff $\rho(x,y) = 0$, since for the metric transformation defined above $f(d(x,y)) = \rho(x,y)$ and $f(0) = 0$ and $f^{-1}(0) = 0$.
- Symmetry of $\rho$ is clear from the symmetry of $d$; consider $\frac{d(x,y)}{1+d(x,y)} = \frac{d(y,x)}{1+d(y,x)}$.
- To verify the triangle inequality holds in the metric space $(X, \rho)$, let $a = d(y,x)$, $b = d(z,y)$ and $c = d(z,x)$. We need to show
  $$\frac{c}{1+c} \leq \frac{a}{1+a} + \frac{b}{1+b}.$$
  Note $a,b,c \in [0,\infty)$. Since the triangle inequality holds in the space $(X,d)$,  we have $c \leq a + b$. Consider $k = a+b$. It follows that $c \leq k$ and thus $\frac{c}{1+c} \leq \frac{k}{1+k}$. That is, $\frac{c}{1+c} \leq \frac{a+b}{1+a+b}$ hence, with $a,b \geq 0$,  $$\frac{c}{1+c} \leq \frac{a+b}{1+a+b} = \frac{a}{1+a+b} + \frac{b}{1+a+b} \leq \frac{a}{1+a} + \frac{b}{1+b},$$
  as desired.

We conclude that $\rho$ is a metric on $X$ because we've demonstrated

- $\rho$ is nonnegative in general and zero only between identical points,
- $\rho$ is symmetric between points, and 
- $\rho$ has the triangle inequality for distances between any three points.

(a) Now, for any point $x \in X$ and radius $r > 0$, $$\ball{d}{r,x} = \ball{\rho}{\frac{r}{1+r}, x}.$$ We have set equality for points within a radius $r$ of $x$ in $(X,d)$ and points within radius $f(r) = \frac{r}{1+r}$ of $x$ in $(X,\rho)$ where $f$ is the above defended metric transformation.

### [@Fo99, number 2.19]

Let $\mu^*$ be an outer measure on $X$ induced from a premeasure, such that $\mu^*(X) < \infty$. If $E \subset X$, define the inner measure of $E$ to be $\mu_*(E) = \mu^*(X) - \mu^*(E^c)$. Then $E$ is $\mu^*$-measurable iff $\mu^*(E) = \mu_*(E)$.

### [@Fo99, number 2.22]

Let $(X, \sM, \mu)$ be a measure space, $\mu^*$ the outer measure induced by $\mu$ according to $$\mu^*(E) = \inf\left\{\sum_1^\infty\mu(A_j): A_j \in \sA, E \subset \bigcup_1^\infty A_j\right\},$$ and $\sM^*$ the $\sigma$-algebra of $\mu^*$-measurable sets, and $\tilde{\mu} = \mu^* | \sM^*$.

(a) If $\mu$ is $\sigma$-finite, then $\tilde{\mu}$ is the completion of $\mu$.

### [@Fo99, number 2.23]

Let $\sA$ be the collection of finite unions of sets of the form $(a,b] \cap \QQ$ with $-\infty \le a\le b \le \infty$. 

(a) Knowing "if $\sE$ is an elementary family, the collection $\sA$ of finite disjoint unions of members of $\sE$ is an algebra" we have that $\sA$ is an algebra of $\QQ$.

## References
