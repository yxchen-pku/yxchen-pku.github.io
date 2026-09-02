---
title: 'The van der Waerden Theorem, Multiple Recurrence, and Pointwise Limits of Sequences of Continuous Functions'
date: 2026-09-02
permalink: /posts/20260902
tags:
  - van der Waerden Theorem
  - Multiple Recurrence
  - Continuity Point
---

**Disclaimer.** The proof of the van der Waerden theorem presented here is due to Hillel Furstenberg and Benjamin Weiss [1]; its foundation is the correspondence between Ramsey-theoretic problems and multiple recurrence in dynamical systems established by Furstenberg in [2] (later known as the Furstenberg correspondence). I learned this proof from Manfred Einsiedler's course *Dynamical Systems and Ergodic Theory* at ETH Zurich. Since I was already familiar with the idea of the Furstenberg correspondence, the part of the proof that surprised me was the use of the existence of continuity points.

**Prerequisites.** Metric spaces, continuous maps, compactness.

---

In mathematical analysis, when considering continuity of derivatives, one naturally encounters the following result:

**Lemma 1.**  
Let $X$ be a complete metric space. If a sequence of continuous functions $f_n\colon X\to \mathbb{R}$ converges pointwise to $f\colon X\to \mathbb{R}$, then the set of continuity points of $f$ is a dense $G_\delta$ set. Here a $G_\delta$ set means a countable intersection of open sets.

In particular, $f$ has at least one continuity point, and in fact the set of continuity points is dense. From this one can show that if $\varphi\colon (a,b)\to \mathbb{R}$ is differentiable at every point, then $\varphi'$ cannot be nowhere continuous. It also shows that the Dirichlet function

$$
\mathbf{1}_{\mathbb{Q}}(x):=\begin{cases}
1,&x\in \mathbb{Q},\\
0,&x\in \mathbb{R}\setminus \mathbb{Q},
\end{cases}
$$

is not the pointwise limit of a sequence of continuous functions. From the form of the conclusion, the proof of Lemma 1 is of course based on the Baire category theorem; the details can be found in standard texts on real analysis, but they are irrelevant to the present paper.

Apart from these simple applications, it is hard to imagine what problems Lemma 1 can solve. This paper gives an application in topological dynamics and explains how multiple recurrence implies the classical van der Waerden theorem in combinatorics:

**Theorem 2 (van der Waerden, 1927).**  
For any partition of the positive integers $\mathbb{N}$ into finitely many disjoint subsets

$$
\mathbb{N}=C_1\sqcup \cdots \sqcup C_r,\quad r\in \mathbb{N},
$$

there exists some $C_i$ containing arbitrarily long (nonconstant) arithmetic progressions.

Equivalently, if each positive integer is colored with one of $r$ given colors, then there exist arbitrarily long monochromatic arithmetic progressions. The following proof can be found in Furstenberg–Weiss [1]; its idea comes from the correspondence introduced by Furstenberg in [2] to prove Szemerédi's theorem (which may be viewed as a strengthening of van der Waerden's theorem and will not be discussed here): a certain class of Ramsey-theoretic problems is translated into multiple recurrence properties in dynamical systems. The role of Lemma 1 in establishing multiple recurrence is that continuity at a single point guarantees that a certain property holds on an open neighborhood; combined with topological transitivity (and minimality), this yields a global statement. Thus the existence of continuity points is crucial.

---

## 1. Reduction to the existence of multiply recurrent points

Based on the idea of the Furstenberg correspondence, the problem can be reduced to the following multiple recurrence theorem (a relatively easy version in topological dynamics). We first admit this result and use it to prove the van der Waerden theorem.

**Theorem 3 (Multiple recurrence).**  
Let $X$ be a compact metric space, and let $T_1,\dots,T_k$ be homeomorphisms of $X$ that commute pairwise (i.e. $T_iT_j=T_jT_i$, where products denote composition). Then there exist $x\in X$ and a sequence of positive integers $n_j\to\infty$ such that

$$
T_i^{n_j}x\to x,\quad \forall i=1,\dots, k.
$$

*Proof of Theorem 2.*  
It is easy to see that the problem can be simplified as follows; the details of the principle are left to the reader. First, it suffices to consider the $\mathbb{Z}$-version of the van der Waerden theorem, i.e. replace the partition of $\mathbb{N}$ by a partition of $\mathbb{Z}$. Second, it suffices to show that for every fixed $k\ge 2$ ($k\in \mathbb{N}$), some $C_i$ contains an arithmetic progression of length $k$ (nonconstant). Hence assume

$$
\mathbb{Z} = C_1 \sqcup \cdots \sqcup C_r,\quad r\in \mathbb{N},
$$

and the problem is reduced to showing that for every $k\ge 2$, some subset $C_i$ contains an arithmetic progression of length $k$ (nonconstant).

Endow $\Lambda:=\{1,\dots,r\}$ with the discrete topology and consider the left shift on the product space $\Lambda^{\mathbb{Z}}$:

$$
T\colon \Lambda^{\mathbb{Z}}\to \Lambda^{\mathbb{Z}},\quad (Tx)(n)=x(n+1).
$$

Clearly $\Lambda^{\mathbb{Z}}$ is a compact metric space and $T$ is a homeomorphism of $\Lambda^{\mathbb{Z}}$. Define the coloring vector (the name comes from thinking of $n\in C_i$ as $n$ being colored with the $i$-th color) $\xi\in \Lambda^{\mathbb{Z}}$ by

$$
\xi(n)=i \iff n\in C_i.
$$

Let an overline denote closure and set

$$
X = \overline{\{ T^m \xi : m\in \mathbb{Z} \}} \subset \Lambda^{\mathbb{Z}}.
$$

Then $X$ is compact and $T$-invariant (that is, $TX=X$). In what follows we regard $T$ as the restriction $T|_X\colon X\to X$.

Consider the $k-1$ pairwise commuting homeomorphisms of $X$

$$
T,T^2,\dots ,T^{k-1}.
$$

By Theorem 3, there exist $x\in X$ and $n_j\to\infty$ such that

$$
T^{in_j}x\to x,\quad \forall i=1,\dots ,k-1.
$$

It is easy to see that convergence in $\Lambda^\mathbb{Z}$ is equivalent to eventual stabilization at every coordinate. Hence for sufficiently large $j$,

$$
(T^{in_j}x)(0)=x(0),\quad \forall i=1,\dots ,k-1.
$$

Let $d=n_j>0$; the above becomes

$$
x(0)=x(d)=x(2d)=\cdots =x((k-1)d).
$$

By the definition of $X$, there exists $a\in\mathbb{Z}$ such that $T^a \xi$ agrees with $x$ at the finitely many coordinates $0,d,2d,\dots,(k-1)d$. Therefore

$$
\xi(a + id) = x(id) = x(0),\quad \forall i=0,1,\dots ,k-1.
$$

This means that the arithmetic progression of length $k$

$$
a,\ a+d,\ a+2d,\ \dots,\ a+(k-1)d
$$

is monochromatic (contained in $C_{x(0)}$), which completes the proof of the van der Waerden theorem. $\square$

---

## 2. Proof of multiple recurrence

We prove Theorem 3 in five steps; the last step will use Lemma 1.

*Proof of Theorem 3.*  
We proceed by induction on the number $k$ of homeomorphisms. For $k=1$ the conclusion is well known: if $T$ is a homeomorphism of a compact metric space $X$, then there exist $x\in X$ and $n_j\to\infty$ such that

$$
T^{n_j}x\to x.
$$

Such a point $x$ is called a (forward) recurrent point. A proof can be based on Step 1 below: first show that there exists a nonempty minimal closed invariant subset $X_0\subset X$, and then observe that the (forward) limit set

$$
\omega(x):=\{y\in X\mid \text{there exists a sequence of positive integers }n_j\to\infty\text{ such that }T^{n_j}x\to y\}
$$

is closed and invariant. Compactness guarantees that $\omega(x)$ is nonempty, and minimality then implies that for every $x\in X_0$, $\omega(x)=X_0$; in particular, every $x\in X_0$ is recurrent. Now assume the conclusion holds for $k-1$ ($k\ge 2$) and consider the case of $k$ homeomorphisms.

### Step 1: Reduction to a minimal system
Call a nonempty closed subset $Y\subset X$ invariant under the family $\{T_1,\dots,T_k\}$ if $T_i(Y)=Y$ for every $i=1,\dots,k$. Consider the family $\mathcal{C}$ of all nonempty closed invariant subsets. By a standard Zorn's lemma argument (using the finite intersection property of compact sets), one shows that $\mathcal{C}$ contains a minimal element $X_0$. Restricting the $T_i$ to $X_0$, we may assume that $X$ is minimal under the family $\{T_1,\dots,T_k\}$, i.e. the only nonempty closed invariant subset is $X$ itself.

### Step 2: $\Delta\cap \omega(\Delta)\not =\varnothing$
On the product space $X^k$ define the homeomorphism

$$
\widehat{T}=T_1\times \cdots \times T_k\colon X^k\to X^k.
$$

For $x\in X$, write the corresponding diagonal element as $\delta(x)=(x,\dots, x)\in \Delta$, where

$$
\Delta = \{ (x,\dots,x) \in X^k:x\in X \}.
$$

For any subset $A\subset X^k$, define its (forward) limit set by

$$
\omega(A) = \left\{ y\in X^k \mid \text{there exist }a_j\in A\text{ and positive integers }n_j\to\infty\text{ such that } \widehat{T}^{n_j} a_j \to y \right\}.
$$

It is easy to see that $\omega(A)$ is closed. We now prove that $\omega(\Delta)\cap \Delta \neq \varnothing$. (In fact, this is the only place where the induction hypothesis is needed.)

Consider the $k-1$ homeomorphisms

$$
S_i = T_iT_k^{-1}, \quad i=1,\dots,k-1.
$$

They commute pairwise. By the induction hypothesis, there exist $x\in X$ and positive integers $n_j\to\infty$ such that

$$
S_i^{n_j}x \to x,\quad \forall i=1,\dots ,k-1.
$$

Set $a_j = T_k^{-n_j}x\in X$. A direct computation gives

$$
\widehat{T}^{n_j}\delta(a_j)=(T_1^{n_j}T_k^{-n_j}x,\dots,T_k^{n_j}T_k^{-n_j}x)=(S_1^{n_j}x,\dots,S_{k-1}^{n_j}x,x).
$$

By construction, the first $k-1$ coordinates converge to $x$, while the last coordinate is always $x$; hence

$$
\widehat{T}^{n_j}\delta(a_j) \to (x,x,\dots,x) = \delta(x).
$$

Thus $\delta(x)\in\omega(\Delta)\cap\Delta$, so the latter is nonempty.

### Step 3: $\Delta \subset \omega(\Delta)$
Using the diagonal map $\delta\colon X\to \Delta$, pull $\Delta$ back to $X$. Since the $T_i$ commute pairwise, one easily checks that $\delta^{-1}(\Delta \cap \omega(\Delta))$ is closed and invariant (left to the reader). Minimality then gives

$$
\delta^{-1}(\Delta \cap \omega(\Delta))=X.
$$

Applying $\delta$ to both sides yields $\Delta \cap \omega(\Delta)=\Delta$, that is, $\Delta \subset \omega(\Delta)$.

### Step 4: Existence of approximately recurrent points
We claim that for every $\varepsilon>0$, there exist $x\in X$ and $n\in \mathbb{N}$ such that

$$
d_{X^k}(\widehat{T}^n \delta(x),\delta(x))\le \varepsilon.
$$

To prove this, choose any $z_0\in X$ and set $\varepsilon_0=\varepsilon/2$. Recursively define sequences $z_m\in X$, $n_m\in \mathbb{N}$, and $\varepsilon_m\in (0,\varepsilon/2]$ ($m\in \mathbb{N}$) as follows. Suppose $z_{m-1},\varepsilon_{m-1}$ have been chosen. Since $\Delta=\omega(\Delta)$, there exist $z_m\in X$ and $n_m\in \mathbb{N}$ such that

$$
d_{X^k}(\widehat{T}^{n_m}\delta(z_m),\delta(z_{m-1}))\le \varepsilon_{m-1}/2.
$$

Using continuity of $\widehat{T}^{n_m}$, choose $\varepsilon_m>0$ such that whenever $\vec{y}\in X^k$ satisfies $d_{X^k}(\vec{y},\delta(z_m))\le \varepsilon_m$,

$$
d_{X^k}(\widehat{T}^{n_m}\vec{y},\widehat{T}^{n_m}\delta(z_m))\le \varepsilon_{m-1}/2.
$$

Since $\varepsilon_m$ may be made arbitrarily small, we can require $\varepsilon_m\in (0,\varepsilon/2]$.

Because $X$ is compact, the sequence $\{z_m\}$ has a convergent subsequence. In particular, there exist $p<q$ such that

$$
d_{X^k} (\delta(z_p),\delta(z_q))<\varepsilon/2.
$$

If $q=p+1$, then the construction and the triangle inequality give

$$
\begin{aligned}
d_{X^k}(\widehat{T}^{n_{p+1}}\delta(z_{p+1}),\delta(z_{p+1}))
&\le d_{X^k}(\widehat{T}^{n_{p+1}}\delta(z_{p+1}),\delta(z_p))+d_{X^k}(\delta(z_p),\delta(z_{p+1}))\\
&\le \varepsilon_p/2+\varepsilon/2\le \varepsilon.
\end{aligned}
$$

Thus the claim holds with $x=z_{p+1}$ and $n=n_{p+1}$. If $q\ge p+2$, inspired by the above argument, we try to take $x=z_q$ and

$$
n=n_q+n_{q-1}+\cdots +n_{p+1}.
$$

Then it is easy to prove by backward induction from the construction (left to the reader) that for every $\ell=q,q-1,\dots ,p+1$,

$$
d_{X^k}(\widehat{T}^{n_\ell}\widehat{T}^{n_{\ell+1}}\cdots \widehat{T}^{n_q} \delta(z_q),\delta(z_{\ell-1}))\le \varepsilon_{\ell-1}.
$$

In particular, taking $\ell=p+1$ yields

$$
d_{X^k}(\widehat{T}^n \delta(z_q),\delta(z_p))\le \varepsilon_p.
$$

Combining this with the triangle inequality and $\varepsilon_p\le \varepsilon/2$ proves the claim.

### Step 5: Completion via Lemma 1
Define the auxiliary function $F\colon X\to \mathbb{R}$ by

$$
F(x)=\inf_{n\ge 1} d_{X^k}(\widehat{T}^{n}\delta(x), \delta(x))\in [0,\infty).
$$

The desired multiple recurrence is equivalent to the existence of $x\in X$ with $F(x)=0$. Note that the claim in Step 4 can be translated as

$$
\inf_{x\in X} F(x)=0.
$$

(Since $F$ need not be lower semicontinuous, this alone does not directly imply that $F$ has a zero.) Rewriting $\inf_{n\ge 1}$ as $\lim_{N\to \infty} \inf_{1\le n\le N}$, we see that $F$ is the pointwise limit of a sequence of continuous functions; Lemma 1 therefore guarantees that $F$ has a point of continuity. The key trick is the following:

> If $x_0\in X$ is a continuity point of $F$, then $F(x_0)=0$.

Indeed, suppose for contradiction that $F(x_0)>0$. Then there exist $\eta>0$ and an open neighborhood $U$ of $x_0$ such that

$$
F(u)>\eta,\quad \forall u\in U.
$$

Since $X$ is minimal, the family of open sets $\{T_1^{n_1}\cdots T_k^{n_k}(U):n_1,\dots ,n_k\in \mathbb{Z}\}$ covers $X$: the complement of its union is a closed invariant proper subset of $X$, hence must be empty. By compactness, there exist finitely many $R_1,\dots ,R_M$, each a finite composition of the $T_1,\dots, T_k$, such that

$$
X=\bigcup_{j=1}^M R_j(U).
$$

Lift each $R_j$ to a homeomorphism of $X^k$ by

$$
\widehat{R}_j=R_j\times \cdots \times R_j\colon X^k\to X^k.
$$

Since the $T_i$ commute pairwise, each $\widehat{R}_j$ commutes with $\widehat{T}$. The finitely many homeomorphisms $\widehat{R}_j^{-1}$ are uniformly continuous on the compact space $X^k$, so there exists $\varepsilon>0$ such that for every $j=1,\dots,M$ and all $\vec{y},\vec{z}\in X^k$,

$$
d_{X^k}(\widehat{R}_j \vec{y}, \widehat{R}_j \vec{z})\le \varepsilon \Longrightarrow d_{X^k}(\vec{y},\vec{z}) \le \eta.
$$

By the claim in Step 4, there exist $x\in X$ and $n\in \mathbb{N}$ such that

$$
d_{X^k}(\widehat{T}^{n}\delta(x), \delta(x))\le \varepsilon.
$$

There exist $j\in \{1,\dots, M\}$ and $u\in U$ with $x=R_j(u)$. Substituting this into the previous inequality and using the fact that $\widehat{R}_j$ commutes with $\widehat{T}$, we obtain

$$
d_{X^k}\big(\widehat{R}_j \widehat{T}^{n}\delta(u), \widehat{R}_j \delta(u)\big)\le \varepsilon.
$$

The choice of $\varepsilon$ then guarantees

$$
d_{X^k}\big(\widehat{T}^{n}\delta(u), \delta(u)\big)\le \eta.
$$

But this contradicts $F(u)>\eta$ for $u\in U$! Therefore the value of $F$ at any continuity point must be $0$, and Theorem 3 follows. $\square$

**Remark.**  
One can also show directly in Step 4 (using the method of Step 5) that the points $x$ in the claim are dense; then in Step 5 the infimum of $F$ over any open set is $0$, so at a continuity point $F$ must be $0$.

---

## References

[1] H. Furstenberg and B. Weiss. *Topological dynamics and combinatorial number theory.* Journal d'Analyse Mathématique, 34:61–85, 1978.

[2] H. Furstenberg. *Ergodic behavior of diagonal measures and a theorem of Szemerédi on arithmetic progressions.* Journal d'Analyse Mathématique, 31:204–256, 1977.
