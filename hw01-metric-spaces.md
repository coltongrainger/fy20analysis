---
title: Metrics, Algebras, and Measures
author: Colton Grainger (MATH 6130 Analysis)
date: 2018-09-01
bibliography: /home/colton/pro/19/prelims.bib
---

## Assignment due 2018-09-12

\newcommand{\ball}[2]{B_{#1}\left( #2 \right)}
\newcommand{\card}[1]{\mathrm{card}\left( #1 \right)}
\newcommand{\eps}{\varepsilon}
\newcommand{\RR}{\mathbf{R}}
\newcommand{\NN}{\mathbf{N}}
\newcommand{\sA}{\mathscr{A}}
\newcommand{\sB}{\mathscr{B}}
\newcommand{\sE}{\mathscr{E}}
\newcommand{\sM}{\mathscr{M}}
\newcommand{\sP}{\mathscr{P}}
\newcommand{\sR}{\mathscr{R}}

### Open balls in metric spaces

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

(b) Further, if $G$ is an $(X,d)$-open set, then $G$ is also $(X,\rho)$-open. That is, $G$ is open in $(X,d)$ iff there's some ball of radius (in the $d$ metric) $\eps$ around each point nested in $G$ iff there's some ball of radius $\frac{\eps}{1+\eps}$ (in the $\rho$ metric) around the same point, also nested in $G$ iff $G$ is open in $(X, \rho)$.

### An algebra of sets

Let $X$ be an uncountable set. Consider the union $$\sA = \{U \subset X : U \text{ is finite}\} \cup \{V \subset X : X\setminus V \text{ is finite}\}.$$

(a) $\sA$ is an algebra of sets of $X$. Closure under complements is apparent. We have closure under finite unions noting that either 
  
  - a union of the $E_i$ is infinite with a finite complement when one of the $E_i$ is infinite, or 
  - a finite union of the $E_i$ is finite when all of the $E_i$ are finite.

    We have closure under intersections by noting that either

  - a finite intersection of the $E_i$ has with a finite complement when all of the $E_i$ are infinite, or 
  - a finite intersection of the $E_i$ is finite when one of the $E_i$ are finite.

(b) Indeed $\sA$ is *not* a $\sigma$-algebra of subsets of $X$, for consider that the infinite intersection of sets with a finite complement may no longer have a finite complement. The smallest $\sigma$-algebra containing $\sA$ is the algebra where countable unions and countable intersections are allowed, and this is given by relaxing the requirements in the set builder notation to "$U$ is countable" or $X\setminus V$ is countable".

### Rings and $\sigma$-rings [@Fo99, number 1.1]

A family of sets $\sR \subset \sP(X)$ is called a ring if it is closed under finite unions and differences; a ring that is closed under countable unions is called a $\sigma$-ring.

a. A ring $\sR$ is closed under finite intersections, for each pair of sets $E,F$ in $\sR$, write $$E \cap F = (E\cup F) \setminus ((E\setminus F) \cup (F\setminus E)).$$ Now a point $x$ is in both $E$ and $F$ if and only if $x$ is in either $E$ or $F$ but not in *only* $F$ or *only*  $F$. Respectively, a $\sigma$-ring $\sR$ is closed under countable intersections, for each countable family of sets $E_j$ write for the $$\bigcap E_j = \bigcup_{\forall j} E_j \setminus \left[\bigcup_{\forall j} \left(E_j \setminus \cup_{k\neq j} E_k\right)\right]$$ where the unions on the left hand side are countable.

b. A ring (respectively $\sigma$-ring) $\sR$ on $X$ is an algebra (respectively $\sigma$-algebra) iff $X \in \xR$. ($\Rightarrow$) Suppose that $\sR$ is an ($\sigma$) algebra. Then $X \in \sR$ and so too $A\setminus B = A \cap B^c \in \sR$, whence $\sR$ is closed under differences, and so $\sR$ is a ($\sigma$) ring. ($\Leftarrow$) Suppose that $\sR$ is an ($\sigma$) ring and $X \in \sR$. Then $E^c = X \setminus E \in \sR$. So $\sR$ is closed under complements, and therefore an ($\sigma$) algebra.

c. Let $\sR$ be a $\sigma$-ring on $X$, and take $$\sA = \{E \subset X : E\in \sR \text{ or } E^c \in \sR\}.$$ 

    - We assume $\sR$ is nonempty. 
    - We have that $\sA$ is closed under countable unions as $\sR$ is.
    - We have that $E \in \sA$ implies $E^c \in \sA$; as when $E \in \sA$ either $E$ or $E^c$ are in the ring $\sR$, whence, by *definition* of $\sA$, we conclude $E^c \in \sA$.

d. Let $\sR$ be a $\sigma$-ring. Take $\sA= \{E \subset X : E \cap F \in \sR \text{ for all } F \in \sR\}$. Note $\sA$ contains $\sR$ (we think of $\sA$ as extending $\sR$) and is therefore closed under countable unions. Further note that $X \in \sA$, whence by previous argument can write complements as set differences with the ambient space $X$, so $\sA$ is closed under complements. We conclude $\sA$ is a $\sigma$-algebra.

### The Borel $\sigma$-algebra on $\RR$ [@Fo99, number 1.2]

To demonstrate the Borel $\sigma$-algebra $\sB_\RR$ is generated by the following collections of intervals in $\RR$, note that we need only obtain an expression (in terms of countable unions, countable intersections, and complements) for the open balls as a basis for the standard topology on the real line. From there, we rely on the fact that every open set in the standard topology is a countable union of open balls.

- That the open intervals generate $\sB_\RR$ follows from the argument above.
- A countable union of closed intervals of the form $[a+\frac1n, b-\frac1n]$ is an open ball.
- A countable union of half-open intervals of the form $[a+\frac1n,b)$ or $(a,b-\frac1n]$ is an open ball.
- The union of an open ray with the complement of a open ray is either empty or an open ball.
- The union of an closed ray with the complement of a closed ray either empty or a closed ball, an infinite union of which form an open ball.

### Infinite $\sigma$-algebras [@Fo99, number 1.3]

Let $\sM$ be an infinite $\sigma$-algebra. Then $\sM$ contains an infinite sequence of disjoint nonempty sets, and  $\card{\sM} \geq \mathfrak{c}$.

*Proof.*

We'll show the existence of a set $\{E_i\}_{i=1}^{\infty}$ of nonempty disjoint events in the $\sigma$ algebra. We proceed by induction on the number of such disjoint sets, indexed by some function $f\colon \NN \to \sM$.

As a base for induction,  consider two distinct nonempty events $E_1$ and $E_2$ in $\sM$, which exist since $\sM$ is infinite.

- Case: $E_2 \setminus E_1$ is empty. Then $E_2 \subsetneq E_1$ (since $E_2 \neq E_1$). 

  - So let $f(1) = E_1 \setminus E_2$ (nonempty because $E_2$ is a proper subset) and 
  - $f(2) = E_2$ (nonempty by construction).

- Case: $E_2 \setminus E_1$ is nonempty. 

  - Then let $f(1) = E_1$ (nonempty by construction) and 
  - $f(2) = E_2 \setminus E_1$ (nonempty in this case).

For the inductive step, suppose that we have a set of $n$ disjoint nonempty events $\{E_i\}_{i=1}^n$. Since $\sM$ is infinite, $\sM$ contains an $E_{n+1}$ distinct from the finite set of all possible unions of the $E_i$ for $1 \leq i \leq n$ (there are $2^n$ of such possible unions, given that $\sP(\{\{E_i\}_{i=1}^n)$ has a natural one-to-one correspondence with the set of such possible unions).

- Case: $E_{n+1} \setminus \left(\cup_{i=1}^n E_i\right)$ is empty. Then $E_{n+1} \subsetneq \cup_{i=1}^nE_i$ (since $E_{n+1}$ was chosen distinct from unions of the $E_i$). 

  - So let $f(i) = E_i \setminus E_{n+1}$ for all $1 \leq i \leq n$ (nonempty because $E_{n+1}$ is distinct from the $E_i$, and contained in their union) and 
  - $f(n+1) = E_{n+1}$ (nonempty by construction).

- Case: $E_{n+1} \setminus \left(\cup_{i=1}^n E_i\right)$ is nonempty. 

  - Then let $f(i) = E_i$ for all $1\leq i\leq n$ (nonempty by construction) and 
  - $f(n+1) = E_{n+1} \setminus \left(\cup_{i=1}^n E_i\right)$ (nonempty in this case).

In either case, the set $\{f(i)\}_{i=1}^{n+1}$ is a nonempty collection of disjoint events in the $\sigma$-algebra, which concludes our induction on $n$.

Now suppose we've parameterized the sequence of disjoint events in the $\sigma$ algebra as $\{E_j\}_{j=1}^\infty$. There's a natural injection from $2^\NN$ into $\sM$, namely a bijection between $2^\NN$ and unions of families in $\sP(\{E_j\}_{j=1}^\infty)$ (consider the possible values of the indicator function which indicates whether some set $E_j$ *is or is not* included in the union). Whence $\card{\sM} \geq 2^{\aleph_0} = \mathfrak{c}$.

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

## References
