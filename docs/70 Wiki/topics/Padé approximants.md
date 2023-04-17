---
type:  topics
status: open
priority: p4
creationtag: 2022-05-09 12:12
infotags: LMU 
---
## [[Padé approximants]] #p2 #topics 
 - [37] Aaron R. Voelker. Dynamical Systems in Spiking Neuromorphic Hardware. Phd thesis, University of Waterloo, 2019. URL http://hdl.handle.net/10012/14625.
		- Added to zotero


## [Padé Approximants - YouTube](https://www.youtube.com/watch?v=szMaPkJEMrw)
Taylor series eventually diverge from original function they are meant to approximate.
Pade approx often follow closer for longer



## [Padé approximant - Scholarpedia](http://www.scholarpedia.org/article/Pad%C3%A9_approximant)
-   [Dr. George A. Baker Jr, Los Alamos National Laboratory, Group T-11, Theoretical Division, University of California, Los Alamos, NM 87545, USA](http://www.scholarpedia.org/article/User:George_A._Baker_Jr "User:George A. Baker Jr")
    

The **Padé approximants** are a particular type of rational approximation of functions.

-   [1 Introduction](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Introduction)
-   [2 **Sample Padé Approximant Uses**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Sample_Pad.C3.A9_Approximant_Uses)
-   [3 Cramer's rule solution of the Padé approximant equations](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Cramer.27s_rule_solution_of_the_Pad.C3.A9_approximant_equations)
-   [4 **Padé approximant table**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Pad.C3.A9_approximant_table)
-   [5 **Convergence of the Padé approximants**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Convergence_of_the_Pad.C3.A9_approximants)
    -   [5.1 **Convergence of horizontal and vertical sequences of Padé Approximants**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Convergence_of_horizontal_and_vertical_sequences_of_Pad.C3.A9_Approximants)
    -   [5.2 **Convergence of general sequences**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Convergence_of_general_sequences)
-   [6 **Padé approximants and continued fractions**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Pad.C3.A9_approximants_and_continued_fractions)
-   [7 **Multi-series Padé approximants**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Multi-series_Pad.C3.A9_approximants)
-   [8 **Additional remarks**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Additional_remarks)
-   [9 **References**](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#References)
-   [10 See also](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#See_also)

## Introduction

The relation between the Taylor series expansion and the function is given classically by the statement that if the series converges absolutely to an infinitely differentiable function, then the series defines the function uniquely and the function uniquely defines the series.

The Padé approximants are a particular type of rational approximation. The $L, M$ Padé approximant is denoted by

$$
\tag{1}
[L/M] = P_L(x)/Q_M(x)
$$

  
where $P_L(x)$ is a polynomial of degree less than or equal to $L\ ,$ and $Q_M(x)$ is a polynomial of degree less than or equal to $M\ .$ Sometimes, when the function $f$ being approximated is not clear from the context, the function name is appended as a subscript $[L/M]_f\ .$ The formal power series

$$
\tag{2}
f(x) = \sum _{j=0}^\infty f_jx^j
$$

  
determines the coefficients by the equation

$$
\tag{3}
f(x) -P_L(x)/Q_M(x)=O(x^{L+M+1}).
$$

  
This is the classical definition. The Baker definition adds the condition

$$
\tag{4}
Q_M(0)= 1\,.
$$

  
As a simple illustration, the Padé approximant $[2,4]$ to $e^x$ is

$$
\tag{5}
[2/4]=\frac{360+120x+12x^2}{360-240x+72x^2-12x^3+x^4}.
$$

When it exists, the $[L/M]$ Padé approximant is unique (Frobenius, 1881).

An encyclopedic discussion of the Padé Approximant is to be found in Baker and Graves-Morris (1996). Some of the material in this article is drawn directly from that source.

## **Sample Padé Approximant Uses**

One use is to compute the value of a function at a regular point. A sample case might be $a(x)=[(1+2x)/(1+x)]^{1/2}\ .$ Another, more difficult, case would be an asymptotic series at an irregular point

$$
\tag{6}
b(x)=\int_0^\infty \frac {e^{-t}dt}{1+xt}=1-1! x +2! x^2-3! x^3 + \dots
$$

  
The results of the use of the $[M/M]$ at the point at infinity are:

| \[M/M\] evaluated at infinity |
| --- |
| $M$ | $[(1+2x)/(1+x)]^{1/2}$ | $\int_0^\infty \frac {e^{-t}dt}{1+xt}$ |
| 1 | 7/5 | 1/2 |
| 2 | 41/29 | 1/3 |
| 3 | 239/169 | 1/4 |
| 4 | 1393/985 | 1/5 |
| 5 | 1.414213552 | 1/6 |
| ... | ... | ... |
| Limit | 1.414213552 | 0 |

The function $a(x)$ is double valued, as the square root can be either plus or minus. The function $b(x)$ is only unique in $-i\pi < \mathrm{arg}\, x < i\pi \ .$ The Padé approximant is single valued. The solution to this difference is to cut the complex plane in such a way that there is a single valued function. For $a(x)$ the cut is on the negative real axis from $-1$ to $-1/2\ .$ For $b(x)$ the cut is the whole negative real axis. The Padé approximant simulates a branch cut in the complex plane by a line of poles and zeros.

Padé approximants can also be used to analyze the nature of singular points. As a sample, consider

$$
\tag{7}
f(x) = (1-x)^{-1.5}(1-\frac 12x)^{1.5}+ e^{-x}
$$

  
The dominant singularity is at $x=1$ and shows a divergence like the $1.5$ power of $1/(1-x)\ .$ Then in the neighborhood of $x=1$ one would expect

$$
\tag{8}
\frac d{dx} \ln f(x) \approx \frac{-1.5}{x-1}
$$

  
A sample of the Padé approximant results for this function is

<table><caption><sup>a</sup> close pole and zero nearer to the origin.</caption><tbody><tr><th colspan="3">Poles and residues of the [M/M] approximant</th></tr><tr><th>M</th><th>Poles</th><th>Residues</th></tr><tr><td>2</td><td>0.96604</td><td>-1.25063</td></tr><tr><td>3</td><td>0.96526<sup>a</sup></td><td>-1.24779<sup>a</sup></td></tr><tr><td>4</td><td>1.00471</td><td>-1.60153</td></tr><tr><td>5</td><td>1.00170</td><td>-1.54827</td></tr><tr><td>6</td><td>1.00034</td><td>-1.51563</td></tr><tr><td>7</td><td>1.00035<sup>a</sup></td><td>-151605<sup>a</sup></td></tr><tr><td>8</td><td>1.00009</td><td>-1.50651</td></tr><tr><td>9</td><td>1.00005</td><td>-1.50443</td></tr><tr><td>...</td><td>...</td><td>...</td></tr><tr><td>Limit</td><td>1.00000</td><td>-1.50000</td></tr></tbody></table>

These results show, that aside from the occasional interruption due to close poles and zeros, the procedure shows steady convergence and that the accuracy of the location is noticeably higher than that in determining the nature.

The occurrence of a close pole and zero as seen in this case is called a "defect". The defects only affect the behavior of the Padé approximant in the neighborhood where they occur and not elsewhere in the complex plane. However, they do slow the rate of convergence. As a note of history, when researchers first encountered this problem, it was supposed that there was a numerical error and the pole and zero should have canceled exactly. However, further study with higher precision arithmetic showed that the phenomenon was real. There will be a more detailed discussion later in this article.

As a consequence, the calculation of Padé approximants by the recursion relations or the determinantal method, which will be mentioned later, requires some special care and, occasionally, it may even be useful to calculate an approximant independently. An appropriate method would be the solution of linear equations by the Gauss-Jordan elimination. The use of multiple precision arithmetic may sometimes be required as the defining equation can be ill-conditioned. Note that, as discussed in the Padé table section, the equation can be inconsistent.

## Cramer's rule solution of the Padé approximant equations

This result is due to Jacobi (1846) in his paper on a simplification of Cauchy's solution to the problem of rational interpolation:

$$
\tag{9}
Q_M(x)=\mathrm{det}\,\begin{vmatrix} f_{L-M+1} & f_{L-M+2} & \cdots & f_{L+1}\\ \vdots & \vdots & \ddots & \vdots\\f_L & f_{L+1} & \cdots &f_{L+M} \\ x^M & x^{M-1} & \cdots & 1 \end{vmatrix}\
$$

$$
\tag{10}
P_L(x)=\mathrm{det}\,\begin{vmatrix} f_{L-M+1} & f_{L-M+2} & \cdots & f_{L+1}\\ \vdots & \vdots & \ddots & \vdots \\f_L & f_{L+1} & \cdots &f_{L+M} \\ \sum_{j=M}^L f_{j-M}x^j & \sum_{j=M-1}^L f_{j-M+1}x^j & \cdots & \sum_{j=0}^L f_jx^j \end{vmatrix}\
$$

## **Padé approximant table**

By the Padé table is meant

$$
\tag{11}
\begin{matrix}
\, [0/0]  & [1/0] & [2/0] & [3/0] & [4/0] & \cdots \\
\, [0/1]  & [1/1] & [2/1] & [3/1] & [4/1] & \cdots \\
\, [0/2]  & [1/2] & [2/2] & [3/2] & [4/2] & \cdots \\
\, [0/3]  & [1/3] & [2/3] & [3/3] & [4/3] & \cdots \\
\, [0/4]  & [1/4] & [2/4] & [3/4] & [4/4] & \cdots \\
\vdots &\vdots &\vdots &\vdots &\vdots & \ddots 
\end{matrix}
$$

  
Although Frobenius (1881) organized the Padé approximants in a doubly indexed array, Padé (1892) was the first to emphasize the importance of displaying them in tabular form and so to study the structure of such a table. While the equation

$$
\tag{12}
Q_M(z)f(z)-P_L(z) =O(z^{M+L+1})
$$

always has a solution, the same is not true of ([3](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Eq-3)). It can happen that the coefficient $Q_M(0)$ as computed in the previous section is zero. This implies that $P_L(0)=0$ as well. Therefore, there is a common factor of $z$ which cancels out in the Padé approximant. Since it is a sufficient condition for a unique Padé approximant to exist that $Q_M(0)\neq 0\ ,$ it is convenient to introduce the $C$ table which consists of the values of $Q_M(0)$ in the Padé table. Padé (1892) has shown that zeros in the $C$ table only occur in square blocks of zero entries which is completely bounded by non-zero entries. The upper left triangular portion of a block of $C=0$ is composed of consistent equations and hence the Padé approximants exist. The sub-diagonal portion of the block consists of inconsistent equations and hence the Padé approximants do not exist. Baker (1973) has shown that for horizontal, vertical and diagonal ($L_j=M_j+J/M_j$) sequences with $f_0\neq 0$ that there exists an infinite sequence.

The adjacent entries in the Padé table obey a large number of identities, see Brezinski (1980). They are either for the Padé approximants themselves or for the numerators and denominators. It is an interesting feature that the numerators and denominators obey the same identities. Only a sample of them will be presented here. The numerator and denominator polynomials will be denoted by $\tag{13}
Q^{(J)}_M(x)$ and $P^{(J)}_L(x)$ where $J=L-M\ .$ We define

$$
\tag{14}
C(r/s)=\det\begin{vmatrix} f_{r-s+1} & f_{r-s+2} & \cdots & f_r\\ \vdots & \vdots & \ddots & \vdots\\f_r & f_{r+1} & \cdots & f_{r+s-1} \end{vmatrix}\ .
$$

  
Two term identities:

$$
\tag{15}
\frac {P^{(J)}_{L+1}(x)}{Q^{(J)}_{M+1}(x)}-\frac {P^{(J)}_L(x)}{Q^{(J)}_M(x)}
=\frac{[C(L+1/M+1)]^2x^{L+M+1}}{Q_{M+1}^{(J)}(x)Q_M^{(J)}(x)}.
$$

  
Cross ratios:

$$
\tag{16}
\frac{ \{[L/M]-[L/M+1]\} \{L+1/M]-[L+1/M+1]\} }
{ \{[L/M]-[L+1/M]\} \{[L/M+1]-[L+1/M+1] \} } 
=\frac{C(L/M+1)C(L+2/M+1)}{C(L+1/M)C(L+1)C(L+1/M+2)},
$$

which is a constant.

Three term identities: let

$$
S(L/M)=G(x)P^{(J)}_L((x)+H(x)Q^{(J)}_M(x),
$$

where $G$ and $H$ are arbitrary. Then

$$
\tag{17}
C(L+1/M)S(L-1/M)-C(L/M+1)S(L/M-1)=C(L/M)S(L/M).
$$

This equation can be used to construct a recursion relation which gives a Padé approximant of denominator degree $M$ from ones of degree $M-1\ .$

Five term identities: notice that the following identities have the advantage that they do not depend on the series coefficients. Here is the Frobenius (1881) star identity:

$$
\tag{18}
S(L+1/M)S(L-1/M)-S(L/M+1)S(L/M-1)=S(L/M)^2.
$$

  
In addition there is Wynn's (1966) identity,

$$
\tag{19}
\frac{1}{[L+1/M]-[L/M]}+\frac {1}{[L-1/M]-[L/M]} =\frac {1}{[L/M+1]-[L/M]}
+\frac{1}{[L/M-1]-[L/M]},
$$

  
which directly relates the values of the Padé approximants without reference to the series coefficients from which they were formed. This feature is of substantial practical advantage since the calculation of the determinants is rather tedious.

## **Convergence of the Padé approximants**

The point of using Padé approximants is to have a rapidly convergent way of evaluating the value of a function of interest at a particular point or to create a curve showing the behavior of the function over a region of interest. There follows a discussion of various sequences of Padé approximants for various classes of functions.

The discussion of the convergence of Padé approximants is complicated by the occurrence of "defects". By this is meant a zero and a pole which are very close to each other. The value of the Padé approximant is disrupted over a very small region. Much of the effort on the convergence of Padé approximants relates to whether this problem occurs in a specific case and if it does how to limit the size of the disruption. Thus there is pointwise convergence, convergence in measure, convergence in Hausdorf measure, convergence in capacity, and convergence in the mean. *In many cases, the diagonal Padé approximants are the most effective sequences*.

### **Convergence of horizontal and vertical sequences of Padé Approximants**

By the duality theorem, if $P_L/Q_M$ is the $[L/M]$ Padé approximant to $f(z)\ ,$ then $Q_M/P_L$ is the $[M/L]$ Padé approximant to $1/f(z)$ (of course, the series for $1/f(z)$ exists only if $f(0)\ne0$). It is therefore the case that the analysis of vertical sequences of Padé approximants is very much the same as the analysis of the horizontal sequences. Thus the discussion of horizontal sequences (rows) will suffice.

Of course, by Taylor's theorem, the row sequence $[L/0]$ converges as *L → ∞*. By Beardon's (1968), let $f(z)$ be analytic in $|z|\leq R$ then an infinite subsequence of $[L/1]$ Padé approximants converges to $f(z)$ uniformly in $|z|\leq R\ .$ Baker and Graves-Morris (1977) have proved that a subsequence of row sequence type $[L/2]$ converges, provided $f(z)$ is analytic in the whole complex plane. Analyticity in $|z|\leq R$ is an insufficient assumption (Buslaev, Gončar, and Suetin, 1983).

The theorem of de Montessus de Ballore (1902) is:

Let $f(z)$ be a function which is meromorphic in the disk $|z| \leq R\ ,$ with poles at distinct points $z_1, z_2,\dots , z_m$ with

$$
\tag{20}
0 < |z_1|\leq |z_2|\leq \cdots \leq |z_m| < R.
$$

  
Let the pole at $z_k$ have multiplicity $\mu _k$ and let the total multiplicity be $\sum _{k=1}^m \mu_k= M$ precisely. Then

$$
\tag{21}
f(z) = \lim _{L\rightarrow \infty} [L/M]
$$

uniformly on any compact subset of

$$
\tag{22}
{\mathcal D}_m = \{ z, |z|\leq R, z\neq z_k, k=1,2,\dots ,m\}.
$$

### **Convergence of general sequences**

It is useful to consider convergence on the Riemann sphere. The mapping from the complex plane to the Riemann sphere is the following. Consider a sphere whose equatorial plane is just the unit circle of the complex plane. Draw a line from the north pole (top) of the sphere to any point in the complex plane. Then the origin is mapped to the south pole of the sphere and the point at infinity is mapped to the north pole. The advantage is, among other things, that any meromorphic function is continuous on the sphere. The metric used is just the cord between the two points under consideration. Any rotation of the Riemann sphere is equivalent to a unitary, linear fractional transformation of the complex plane.

In the previous subsection we note some invariance of the Padé approximants under value transformations. There is also some invariance of the Padé approximants under argument transformations. To summarize, the invariance theorem is: if $P_M(x)/Q_M(x)$ is the $[M/M]$ Padé approximant to $f(x)\ ,$ and $C+D f(0)\neq0\ ,$ then

$$
\tag{23}
\frac{A+B\left [ P_M\left (\frac {\alpha y}{1+\beta y}\right )\left / 
Q_M\left (\frac {\alpha y}{1+\beta y}\right )\right .\right ]}
{C + D\left [ P_M\left (\frac {\alpha y}{1+\beta y}\right )
\left / Q_M\left (\frac {\alpha y}{1+\beta y}\right )\right .
\right ] }
$$

is the $[M/M]$ Padé approximant to

$$
\tag{24}
\{ A + Bf[\alpha y/(1+\beta y)]\}/\{ C+Df[\alpha y/(1+\beta y )]\}.
$$

The most precise convergence theorems for Padé approximants are obtained for Stieltjes series and Polya frequency series because the location of the poles of the denominators can then be determined, Baker and Graves-Morris (1996).

The uniqueness of the convergence of a sequence of Padé approximants is given by the theorem -

*Let $P_k(z)=[L_k/M_k]$ be a sequence of Padé approximants of a function which is regular at the origin, such that $L_k+M_k \rightarrow \infty$ as $k\rightarrow \infty\ .$ If $\{ P_k(z)\}$ is equicontinuous on the sphere in a simply connected and compact region ${\mathcal R}$ of which the origin is an interior point, the domain of definition of $f(z)$ may be extended so that $f(z)$ is meromorphic in the interior of ${\mathcal R}$ and $[L_k/M_k]$ converges to $f(z)$ on the sphere for all $z \in {\mathcal R}\ .$*

There is a similar theorem for ordinary convergence.

As remarked previously, the Padé approximant can have "defects". To deal with this problem there are several approaches. One is to consider convergence in measure. Nuttall (1970) and Zinn-Justin (1971a): *Let $f(z)$ be a meromorphic function. Suppose that $\epsilon \ ,$ $\delta$ are given positive numbers. Then $M_0$ exists such that any $[M/M]$ Padé approximant satisfies*

$$
\tag{25}
|f(z)-[M/M]|  < \epsilon
$$

for all $M>M_0$ on any compact set of the $z$\-plane except for a set ${\mathcal  E}_M$ of measure less than $\delta \ .$

Pommerenke (1973) gives an extension of this theorem to include poles and essential singularities. He also includes ray sequences.

Baker, Gammel and Wills (1961) made the conjecture, called the **Padé conjecture**:

*If $P(z)$ is a power series representing a function which is regular for $|z|\leq 1\ ,$ except for $m$ poles within this circle and except for $z=+1\ ,$ at which point the function is assumed continuous when only points $|z|\leq 1$ are considered, then at least a subsequence of the $[N/N]$ Padé approximants converge uniformly to the function (as $N$ tends to infinity) in the domain formed by removing the interior of small circles with centers at the poles.*

This conjecture was quite good and is usually correct as it took forty years for a counter-example to be found. The first counter-example was found by Lubinsky (2003). Shortly thereafter, Buslaev (2002) found a simpler counter-example. It is

$$
\tag{26}
f(z) =\frac {-27+6z^2+3(9+\omega) z^3+\sqrt{81+[3-(3+\omega )z^3]^2+4z^6}}
{2z[9+9z+(9+\omega)z^2]},
$$

  
where $\omega = -\frac{1}{2}+\sqrt{3}\,i/2$ is a cube root of unity.

In its place, Baker (2005) has made the "patchwork conjecture" -

**Patchwork conjecture:**

*Let the function $f(z)$ be regular in ${\mathcal D} = \{ z \,|\, |z| \leq 1\}$ except for a finite number of poles (counting multiplicity) in the interior. Then there exists a finite number of infinite subsequences $N\in {\mathcal N}_k$ such that these subsequences can be patched together in such a manner that for any $z\in {\mathcal D}\ ,$ for at least one of these subsequences,*

$$
\tag{27}
\lim _{N \rightarrow \infty}[N/N] =f(z),\quad N\in {\mathcal N}_k,
$$

on the sphere.

**Gončar's theorem (1983):**

*Let ${\mathcal D}$ be a domain which satisfies the condition $\delta {\mathcal D} \subset \tilde{\mathcal D}$ where $\tilde{\mathcal D}$ is the complement in the extended complex plane of the complex hull of ${\mathcal D}\ ,$ and $\delta$ denotes the boundary. Further let ${\mathcal E}$ be a relatively closed subset of ${\mathcal D}$ of capacity $0\ .$ Let $\Omega ={\mathcal D}\backslash {\mathcal E}$ be a domain containing the origin as an element, and suppose that the number of poles of the $[n/n]$ Padé approximant in any compact subset ${\mathcal K}\subset  \Omega$ is uniformly bounded in $n$ by $\kappa$ ($\kappa < \infty$). Further, if the $[n/n]$ Padé approximants converge to a holomorphic function in the neighborhood of the origin, then the diagonal Padé approximants converge uniformly on compact subsets to a function which is meromorphic in $\Omega$ and holomorphic at the origin, except for a possible set of Hausdorf measure $0\ .$ If $\kappa ({\mathcal K})=0\ ,$ then the convergence is uniform on compact subsets of $\Omega \ .$*

**Baker's theorem (1976):**

*Let there be given a function $f(z)\ ,$ with $l$ zeros and $m$ poles (counting multiplicities) meromorphic in an open, simply connected region $\mathcal R$ of the extended complex plane bounded by a simple closed curve, and containing the origin. Let $\{ P_k(z)\}$ be a sequence of $[L/M]$ Padé approximants (assumed to exist) with $L+M$ going to infinity with $k$ such that the sum of the number of poles and zeros $n_k(d)$ of $P_k(z)$ in ${\mathcal R}\ ,$ more distant on the sphere than any $d>0$ from the boundary of $\mathcal R\ ,$ satisfies*

$$
\tag{28}
\lim_{k\rightarrow \infty}[n_k(d)/(L_k+M_k)]=0
$$

  
Further, let ${\mathcal T}$ be an arbitrary, closed (on the sphere) set in the interior of ${\mathcal R}\ .$ $d$ is chosen so that none of ${\mathcal T}$ is closer on the sphere to the boundary of ${\mathcal R}$ than $d\ .$ Let there be exactly $l_1$ zeros and $m_1$ poles (counting multiplicity) of $f(z)$ in the interior of ${\mathcal T}$ and an equal number of poles and zeros of $\{ P_k(z)\}$ in ${\mathcal T}$ and no other limit point of poles or zeros in $\mathcal T\ .$ Then the sequence $\{ P_l(z)\}$ converges on the sphere uniformly in ${\mathcal  T}$ to $f(z)\ .$ The conditions on $\{ P_k(z)\}$ are also necessary, provided ${\mathcal T}$ contain the origin as an interior point and contains no limit point of external poles or zeros.

Some of the most significant work on the convergence of general sequences of Padé approximants is due to H. Stahl (1987). Here are some of his results -

**Stahl's extremal domain theorem:**

*Let $f(z)$be a given function, analytic at the origin. There exists a unique compact set ${\mathcal K}_0\subset {\mathcal C}\ ,$ in the $\omega$ plane ($\omega = 1/z$) such that (i) ${\mathcal D}_0 = \hat{\mathcal H}_0$ is the domain in which $f(1/\omega)$ has a single-valued, analytic continuation from $\omega =\infty\ ,$ (ii) $\mathrm{cap} ({\mathcal H}_0)=\inf_{\mathcal H}\mathrm{cap} {\mathcal H})\ ,$ where the infimum extends over all compact sets ${\mathcal H}\subseteq {\mathcal C}$ satisfying (i), and (iii) ${\mathcal H}_0\subseteq {\mathcal H}$ for all compact sets ${\mathcal H}\subseteq {\mathcal C}$ satisfying (i) and (ii).*The set ${\mathcal H}_0$ is called the minimal set of $f(\omega ^{-1})$ and the domain ${\mathcal D}_0$ is called the extremal domain. The \`natural' place for the cuts to go is on the minimal set.

**Stahl's Padé convergence theorem:**

*Let $f(z)$ be a given function, analytic at $z=0\ ,$ and let the set ${\mathcal E}\subset \hat{\mathcal C} \ ,$ in the $\omega$ plane, of all the singularities of $f(\omega ^{-1})$ be of capacity cap $({\mathcal E})=0\ .$* *Then any near-diagonal sequence of Padé approximants to the function $f(z)$ converges in capacity to $f(z)$ in the extremal domain ${\mathcal D}_0\ .$ More precisely: for any compact set ${\mathcal W} \subseteq {\mathcal D}$ in the $\omega$\-plane and $\epsilon > 0\ ,$ with $z= 1/\omega$ we have*

$$
\tag{29}
\lim _{M\rightarrow \infty} \mathrm{cap}\, \{ \omega \in {\mathcal W}, |f(z)-[L/M(z)| > F_j(z)+\epsilon ]^{L+M} \} =0
\ ,
$$

and

$$
\tag{30}
\lim _{M\rightarrow \infty} \mathrm{cap}\, \{ \epsilon \in {\mathcal W},[f(z)-[L/M](z)|<|F_f(z)-\epsilon ]^{L+M} \}=0,
\ ,
$$

where

$$
\tag{31}
F_f(z) = \exp \{-g_{{\mathcal D}_0}(z,0), z^{-1} \in {\mathcal D}_0
$$

and $g$ is the Green function with a logarithmic singularity at $z=0$ for the extremal domain.

## **Padé approximants and continued fractions**

By a continued fraction is meant the limit of successive truncations (also called convergents) of

$$
\tag{32}
G = b_0+\frac {a_1}{b_1+\frac {a_2}{b_2+\frac {a_3}{b_3+\dots }}},
$$

that is, $a_j$ is replaced by 0 for $j>n\ .$ A thorough coverage of continued fractions is given in Jones and Thron (1980). See also Lorentzen and Waadeland (1992). In this article, the interest is in the relation of continued fraction to Taylor series, and thus to Padé approximants. Consider the continued fraction

$$
\tag{33}
G(z)=b_0+\frac {a_1 z}{1+\frac {a_2 z}{1+\frac {a_3 z}{1+ \ddots }}}
$$

  
The expansion of this continued fraction is,

$$
\tag{34}
G(z)=b_0+a_1z-a_1a_2z^2+O(z^3)
$$

  
Hence $a_2$ only effects the coefficient of $z^2$ and perhaps higher order terms. By induction, we conclude that $G(z)$ has a Taylor series expansion of the form

$$
\tag{35}
G(z)= \sum _{n=0}^\infty g_nz^n.
$$

  
The truncations of $G(z)$ are

$$
\tag{36}
\frac {A_0(z)}{B_0(z)}=\frac {b_0}1,\quad \frac {A_1(z)}{B_1(z)}=\frac{b_0+a_1z}1\quad \frac{A_2(z)}{B_2(z)}=\frac{b_0+a_1z+b_0a_2z}{1+a_2z}
$$

  
These truncations are just $[0/0], [1/0], [1/1], [2/1], [2/2] \dots$ Padé approximants. These continued fractions are called corresponding to the series (or of Stieltjes-type). If the $n$th truncation is $A_n/B_n\ ,$ then fundamental recurrence formulas are

$$
\tag{37}
A_{k+2}= A_{k+1}+a_{k+2}zA_k,\quad B_{k+2}=B_{k+1}+a_{k+2}z B_k\ .
$$

  
The other type of interest is the continued fractions associated to the series (or of Jacobi-type). It is obtained by performing an equivalence transformation and has the form $\tag{38}
G(z) =b_0+\frac {a_1z}{1+a_2z-\frac{a_2a_3z^2}{1+(a_3+a_4)z-\frac {a_4a_5z^2}{1+(a_5+a_6)z-\dots}}} .$

  
The successive truncations here are given by the diagonal sequence $[0/0], [1/1], [2/2] \dots$ of the Padé table.

A nice historical background can be found in Brezinski (1991).

Changing notation, let us write the general form of an associated continued fraction as

$$
\tag{39}
F(z)=b_0+c_0z\left (\frac 1{1+b_1 z}\,{{}\atop-}\,\frac{c_1^2z^2}{1+b_2z}\,{{}\atop-}\, \frac {c_2^2z^2}{1+b_3z} \,{{}\atop-}\, \dots \right )
$$

Wall (1948) was the first to notice that if he defined the $J$\-matrix as

$$
\tag{40}
J = \left ( \begin{array}{cccccc}
b_1&-c_1& 0& 0& 0& \dots \\
-c_1&b_2&-c_2&0&0&\dots \\ 
0 & -c_2 & b_3 &-c_3 &0 &\dots \\ 
0&0&-c_3&b_4&a_4&\dots \\
\vdots &\vdots & \vdots & \vdots &\vdots &\ddots \\
\end{array} \right ),
$$

  
he could find a way to study continued fractions and Padé approximants from a functional analysis point of view. First, introduce a set of orthonormal elements $e_j\ .$ Notice that since $c_i$ and $b_i$ can be complex in the case of interest, by its structure $J=J_1+iJ_2$ where $J_1$ and $J_2$ are real and self-adjoint. Wall found that if

$$
\tag{41}
f=e_1-zJf,
$$

then

$$
\tag{42}
F(z)= b_0+c_0z(e_1,f)
$$

  
Since $J$ is tri-diagonal, as long as $c_i\neq 0\ ,$ it is easy to show that the space spanned by $J^je_1$ for $j=0,\dots , N-1$ is just $\alpha _1e_1+\cdots + \alpha _Ne_N\ .$ It is convenient to define the orthogonal projection operators $P_N$ for this space. Furthermore, Wall found that if the element $f_N$ satisfies the functional equation

$$
\tag{43}
f_N= e_1-zP_NJP_Nf_N
$$

then

$$
\tag{44}
[N/N]_F(z)=b_0+c_0(e_1,f_N)
$$

  
Hence the $N$th truncation of the associated continued fraction is obtained from $P_NJP_N$ since it provides the $[N/N]$ Padé approximant. Note that if $J$ is a compact operator, then the entire sequence converges, provide $z$ is not a singular point ($z\in$ the resolvent set). If the $J$\-matrix is bounded in the sense that

$$
\tag{45}
\max _i\sum _j|J_{i,j}|\leq B<\infty,\quad \max _j\sum _i|J_{i,j}|\leq B<\infty.
$$

  
then Wall has shown that the continued fraction converges uniformly for $|z|\leq \beta <1/B$ to the function defined by the power series. This means, of course, that the whole sequence of $[N/N]$ Padé approximants converges uniformly in that disk.

Let

$$
\tag{46}
u_n(z)=\frac{Q_n^{(0)}(z)}{Q_{n+1}^{(0)}(z)}=\frac {\det(I+zP_nJP_n)}{\det(I+zP_{n+1}JP_{n+1})} =(e_{n+1},(I+zP_{n+1}JP_{n+1})^{-1}e_{n+1}).
$$

  
Beckermann (2001) using a spectral analysis approach has shown that in the disk $|z|\leq \beta , |u_n(z)|$ is uniformly bounded. On the other hand, if $|u_n(z)|$ is uniformly bounded on the disk $|z|\leq \beta$ then the $J$\-matrix is bounded and so the $[N/N]$ Padé approximants converge in a disk centered at the origin. He has gone further and shown that the $u_n(z)$ are equicontinuous on the sphere in compact subsets of the resolvent set of $I+zJ\ .$ However, since the counter-examples to the Padé conjecture have bounded $J$\-matrices it is clear that the solution to the problem of the location of the resolvent set is not simple!

## **Multi-series Padé approximants**

Matrix Padé approximants are illustrated by consideration of the series

$$
\tag{47}
\mathcal F(z)= \mathcal F_0  + \mathcal F_1 z\ \dots
$$

where the $\mathcal F_i$ and thus $\mathcal F(z)$ are $p\times p$ matrices. If the right handed truncations of the continued fraction are written as $\mathcal A_n\mathcal B_n^{-1}\ ,$ then the standard method of computation of the Padé approximants to ([33](http://www.scholarpedia.org/article/Pad%C3%A9_approximant#Eq-33)) is

$$
\tag{48}
\mathcal A_0(z)=b_0\,, \quad \mathcal B_0(z) =I\,, \quad \mathcal A_1(z) = b_0+a_1z\,,\quad\mathcal B_1= I
$$

$$
\tag{49}
\mathcal A_{k+2}(z)=\mathcal A_{k+1}+\mathcal A_{k}a_{k+2}z\,,\quad \mathcal B_{k+2}(z)=\mathcal B_{k+1}+\mathcal B_{k}a_{k+2}z\,,
$$

where $\mathcal A_k,\mathcal B_k,  a_k$ are also $p\times p$ matrices. Left handed truncations $\tilde{\mathcal B_n}^{-1}\tilde{\mathcal A}_n\ ,$ can also be defined. The polynomials are different but the approximants are identical. Finally, rectangular matrices can also be considered.

Matrix Padé approximants can be generalized to operator Padé approximants, see Cuyt (1984).

The simultaneous Padé approximants or the German polynomial problem are defined as follows. Suppose one has the set of functions $f_1(z), \dots,
f_d(z)\ .$ One wishes to approximate them with a single denominator as $\vec p(z)/q(z)\ .$ This set of approximations has many properties analogous to regular Padé approximants.

The problem has the following equivalent formulation: a vector valued function is formally defined by

$$
\tag{50}
\vec f(z) =\vec c_0+\vec c_1z+\vec c_2z^2+\cdots
$$

  
with $\vec c_i\in \mathcal C^d\ .$ A vector Padé approximant can be defined as follows. If a vector polynomial $\vec p(z)$ and a real scalar polynomial $q(z)$ exist satisfying the following conditions

$$
\tag{51}
\begin{array}{lc}
(i) & \vec f(z) -\vec p(z)/q(z)=O(z^{n+1})\\
(ii) & q(0)\neq 0\,,\\
(iii) &\forall i\ \mathrm{degree\ of\ }p_i=k\,,\ \mathrm{degree\ of\ }q=(n-k)d\,, \\
\end{array}
$$

then $\tag{52}
\vec r(z) =\vec p(z)/q(z)$

is a vector Padé approximant.

In the limit $d\rightarrow \infty\ ,$ one obtains functional Padé approximants. If

$$
\tag{53}
f(x,\lambda )=c_0(x)+c_1(x)\lambda+c_2(x)\lambda ^2+\cdots
$$

  
where $\lambda \in \mathcal C$ and, for example, $c_i(x)\in L_2(a,b)$ where $(a,b)$ is a real interval which is a natural domain for $c_i(x)\ .$ The formalism is exactly the same as for the vector Padé approximants. A functional approximant of type $[n/2k]$ takes the form

$$
\tag{54}
r(x,\lambda )=p(x,\lambda )/q(\lambda )
$$

  
These approximants find a natural application in linear integral equations in which the Fredholm denominator does not depend on $x\ .$

Following Hermite (1893), one can define Hermite-Padé approximants. Suppose there are $k+2$ formal power series $f_{-1}(z), f_0(z) , \dots 
, f_k(z)\ .$ Without loss of generality, we may assume that at least one of the $f's$ does not vanish at $z=0\ .$ By symmetry it may be chosen to be $f_{-1}(z) \ .$ For a given set of integers $(m_{-1}, m_0, \dots , m_k)\ ,$ by means of the accuracy through order principle, polynomials are defined by

$$
\tag{55}
\sum _{j=-1}^k\mathcal Q_{j,m_j}(z)f_j(z)=O(z^{s+1}),
$$

where $\mathcal Q_{j,m_j}(z)$ is of degree $m_j$ at most, with the definitions

$$
\tag{56}
M=\sum _{j=-1}^k(m_j+1) -1,\quad s=M+m_{-1}.
$$

  
The essential nature of the problem is unchanged if we divide the series by $f_{-1}$ and so we may take $f_{-1}(z)=1\ .$ There has been is a large amount of theory developed for these approximants. See Baker and Graves-Morris (1996).

One feature of the Padé approximant is that it is single valued and always approximates with a meromorphic function. Now the discussion turns to ways to approximate multivalued functions. A very simple function like $\ln z$ has an infinite number of Riemann sheets. Riemann has classified functions by the number of independent coverings of the complex plane. In the case of $\ln z$ this number is just 2, even though there are an infinite number of Riemann sheets. If $f(z)$ is a complex analytic function with $m$ independent coverings and $n\ ,$ $m$ and $n$ finite. Encircling one of the branch points must yield a linear combination of the independent coverings which can be represented a monodromy matrix $M^{(i)}\ .$ It has been shown that there exists an order of the branch points such that $M^{(1)}M^{(2)}\cdots M^{(n)}=I\ .$ The algebraic Padé approximants are a special case of the Hermite Padé approximants and can be defined by

$$
\tag{57}
\sum _{j=-1}^k\mathcal Q_{j,m_j}(z)[f(z)]^{j+1}=O(z^{s+1}),
$$

  
where the polynomials $\mathcal Q_{j,m_j}(z)$ are of degree at most $m_j\ .$ It is convenient to introduce the notation $\vec m= (m_0,\dots ,m_k). \ .$ The algebraic approximant is denoted by $\langle m_{-1}/m_0, \dots ,m_k \rangle = \langle m_{-1}/\vec m\rangle$ and is the solution $y(z)$ of the equation

$$
\tag{58}
\sum _{j=-1}^k \mathcal Q_{j,m_j}(z)[y(z)]^{j+1}=0,\quad  y(0)=f(0).
$$

  
Clearly there are, by Gauss's theorem, $k$ roots to this equation and $k$ possible different solutions. The behavior at $z=0$ of $f(z$) can be used to select the correct solution.

Next there are the integral approximants Guttman and Joyce (1972), Gammel and Gaunt (1973), Fisher and Au-Yang (1979) and Baker and Hunter (1979). These are again special cases of the Padé Hermite approximants. Let the function $f(z)$ be given through its Taylor series expansion, and $f^{(j)}(z)$ its $j$th derivative. Polynomials are defined by the equations

$$
\tag{59}
\mathcal Q_{-1,m_{-1}}(z) +\sum _{j=0}^k\mathcal Q_{j,m_j}(z) f^{(j)}(z)=O(z^{s+1)}).
$$

  
The solution for these polynomials leads to the Padé integral approximant $y(z)$ solution of the differential equation

$$
\tag{60}
\mathcal Q _{-1,m_{-1}}(z)+\sum _{j=0}^k\mathcal Q_{j,m_j}(z)y^{(j)}(z)=0\ ,\quad y^{(j)}(0)=f^{(j)}(0),\ j=0, \dots ,k-1.
$$

  
The integration of this equation must begin at the origin and go over the correct path to come to the relevant point to give the desired solution.

Finally, among the large number of other generalizations of Padé approximants, we can also mention multipoint Padé approximants that generalize to rational functions the Newton interpolation method, or Padé approximants for double series and the quadratic approximants of Shafer. Padé approximants have found many applications in [numerical analysis](http://www.scholarpedia.org/article/Numerical_analysis "Numerical analysis") or in physics, see for example Baker and Graves-Morris (1996), Brezinski and Van Iseghem (1994), Zinn-Justin (1971b).

## **References**

-   Arms, R. J. and Edrei, A. (1970) The Padé table and continued fractions generated by totally positive sequences In *Mathematical Essays dedicated to A. J. Macintyre* Ohio University Press, Athens, Ohio, 1-21.

-   Baker, G. A. Jr.(1967) Convergent, bounding approximation procedures to the ferromagnetic Ising model. Phys. Rev. **161**, 434-445.

-   Baker, G. A. Jr.(1973) The existence and convergence of subsequences of Padé approximants. J. Math. Anal. Appl. **43** 498-528.

-   Baker, G. A. Jr. (1976) A theorem on the convergence of Padé approximants, Studies in Appl. Math. **55**, 107-17.

-   Baker, G. A. Jr. (2005) Counter-examples to the Baker-Gammel-Wills conjecture and patchwork convergence, J. Comp. and Appl. Math.**179** 1-14.

-   Baker, G. A. Jr. and Graves-Morris, P. R. (1977) Convergence of the rows of the Padé table. J. Math.anal. appl. **57** 323-39.

-   Baker, G. A. Jr. and Graves-Morris P. R. (1996) Padé Approximants Second edition, Cambridge University Press

-   Beckermann, B. (2001) Complex Jacobi matrices, J. Comput. Appl. Math. **127** 17-65.

-   Beardon, A. F. (1968) On the location of poles of Padé approximants J. Math. Anal. Appl. **21** 469-74.

-   Brezinski, C. (1980) Padé-Type Approximation and General Orthogonal Polynomials, ISNM vol. 50, Birkhäuser Verlag, Basel.

-   Brezinski, C. (1991) History of Continued Fractions and Padé Approximants. Springer Series in Computational Mathematics **12** Springer-Verlag Heidleberg 1-551.

-   Brezinski, C. and Van Iseghem, J. Padé Approximations in Handbook of Numerical Analysis, P.G. Ciarlet and J.L. Lions eds, Elsevier, Amsterdam, 1994, vol. III, 47-222.

-   Buslaev, V. I., (2002) On the Baker-Gammel-Wills conjecture in the theory of Padé approximants. Sbornik mat.;**193** 811-829.

-   Buslaev, V. I., Gončar and Suetin (1983) On convergence of subsequences of the $m$ row of the Padé table. Mat. Sbornik **120** 162.

-   Common, A. K, (1969) Properties of Generalizations to Padé approximants J. Math. Phys. **10** 1875-80.

-   Cuyt, A. (1984) Padé Approximants for Operators: Theory and Applications, Lecture Notes in Mathematics, **1065**, Springer-Verlag, Berlin.

-   Fisher, M. E. and Au Yang, H. (1979) Inhomogeneous differential approximants for power series. J. Phys. A **12** 1677-92.

-   Frobenius, G. (1881) Ueber Relationen zwischen den Näherungbrüchen von Poteneihen. J. für Math. (Crelle) **90**, 1-17.

-   Gammel, J. L. (and Gaunt, D.) (1973) Review of two recent generalizations of the Padé approximant methhod. In *Padé approximants* P.R. Graves-Morris (ed.), Academic Press London 3-9.

-   Gammel, J. L., Rousseau, C. C. and Saylor, D. P. (1967) A Generalization of the Padé approximant, J. Math. Anal. Appl. **20**, 416-20.

-   Gončar, A. A. (1983) On uniform convergence of diagonal Padé approximants, Math. USSR Sbornik **46**, 539-559.

-   Graves-Morris, P. R. (1981) The convergence of ray sequences of Padé approximants of Stieltjes functions, J. Comp. App. Math. **7** 191-201.

-   Guttman, A. J. and Joyce, G. S. (1972) On a new method of series analysis in lattice statistics, J. Phys. A **5** L81-84.

-   Hermite, C. (1893) Sur la généralisation des fractions continues algébriques. Annali di Mathematica Pura e Applicata, Sér. 2 **21**, 289-308.

-   Hunter, D. L. and Baker, G. A. Jr. (1979) Methods of series analysis III. Integral approximant methods Phys. Rev. **19**, 3808-21.

-   Jacobi, C. G. J. (1846) Uber die Darstellung einer Reihe Gegebner Werthe durch eine Gebrochne Rationale Function. J. Reine Angew. Math. (Crelle) **30**, 127-156.

-   Jones, W. B. and Thron, W. J. (1980) Continued Fractions, Analytic Theory and Applications, Addison-Wesley Pub. Co. Reading Massachetts 1-428.

-   Lorentzen, L. and Waadeland, H. (1992) Continued Fractions with Applications, Elsevier, Amsterdam.

-   Lubinsky, D. (2003) Rodgers-Ramanujan's and the Baker-Gammel-Wills (Padé) conjecture. Ann. Math. **157** 847-889.

-   de Montessus de Ballore, R. (1905) Sur les fractions continues algébriques. Rend. di Palermo **19** 1-73.

-   Nuttall, J. (1970) Convergence of Padé approximants of meromorphic functions. J. Math. Anal. Appl. **31** 147-53.

-   Padé, H. (1892) (Thesis) Sur la représentation approchée d'une fonction pour des fractions rationnelles. Ann. Sci. École Norm. Sup. Suppl.\[3\] **9**, 1-93.

-   Pommerenke, C. (1973) Padé approximants and convergence in capacity. J. Math. Annl. Appl. **41** 775-80.

-   Press, W. W., Teukolsky, S. A., Vetterling, W. T., and Flannery, B. P., (1992) Numerical recipes in Fortran (Cambridge University Press, New York).

-   Stahl, H. (1987) Three different approaches to a proof of convergence for Padé approximants. In *Rational approximation and its applications in mathematics and physics.* J. Gilewitz, M. Pindor, and W. Siemaszko (eds.)

-   Wall, H. S. (1948) Analytic theory of continued fractions Van Nostrand-Reinholt, Princeton New Jersey.

-   Wynn, P. (1966) Upon systems of recursions which obtain among the quotients of the Padé table. Numer. Math.**8** 264-269.

-   Zinn-Justin, J. (1971a) *Convergence of Padé approximants in the general case. Colloquium on advanced computing methods in theoretical physics* A. Visconti (ed.) 88-102 C. N. R. S. Marseille; (1974) "Convergence of Padé approximants in the general case", Rocky Mountain Journal of Mathematics **4** 325-.

-   Zinn-Justin, J. (1971b) Strong interactions [dynamics](http://www.scholarpedia.org/article/Dynamical_Systems "Dynamical Systems") with Padé approximants, Physics Report **1** 55-102.

## See also






