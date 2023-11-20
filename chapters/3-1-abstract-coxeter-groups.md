# Coxeter 群

## 抽象 Coxeter 群

设 $S$ 是一个集合，一个基于 $S$ 的 Coxeter 矩阵 $M=(m_{s,t})_{s,t\in S}$ 是一个对称矩阵，其对角线上都是 1，非对角线元素取值范围为 $\{2,3,\ldots,\infty\}$。$|S|$ 叫做 $M$ 的秩 (rank)，在本文中我们只考虑 $|S|<\infty$ 的情形。

任一 Coxeter 矩阵 $M$ 都确定了一个有限表现群 $W$，其生成元为集合 $S$，表现如下：
$$W = \langle s\in S\ |\ (st)^{m_{s,t}}=1\ {\rm if}\ m_{s,t}<\infty\rangle.$$

即 $S$ 作为 $W$ 的生成元，其元素满足的生成关系是：

1. 对任何 $s\in S$ 有 $s^2=1$。
2. 对任何 $s\ne t, m_{s,t}<\infty$ 有**辫关系** (braid relation) $\overbrace{sts\cdots}^{m_{s,t}}=\overbrace{tst\cdots}^{m_{s,t}}$ 成立。（当 $m_{s,t}=\infty$ 时的关系是无用的）

我们称 $(W, S)$ 是一个 **Coxeter 系**，$W$ 是一个**有限生成 Coxeter 群**。

用 Coxeter 矩阵或者群表现的形式来描述一个 Coxeter 群有点不太方便。我们可以用一个有限图 $\Gamma$ 更直观地表示一个 Coxeter 群 $(W,S)$，$\Gamma$ 叫做 $(W,S)$ 的 Coxeter 图：$\Gamma$ 的顶点集就是 $S$，两个顶点 $s,t\in S$ 之间连一条边当且仅当 $m_{s,t}\ne 2$，并且这条边的标号是 $m_{s,t}$。在 $m_{s,t}=3$ 时这个标号通常省略不写。如果 $\Gamma$ 是连通的，就称 $(W,S)$ 是**不可约的**。

::: example
Coxeter 矩阵
$$\begin{pmatrix}1 & 3 & 4\\3&1&\infty\\4&\infty&1\end{pmatrix}$$
对应的 Coxeter 图 $\Gamma$ 是

![](images/3-4-inf.svg){ width=120 }

$\Gamma$ 是连通的，从而 $W$ 是不可约的。
:::

::: example
Coxeter 矩阵
$$\begin{pmatrix}1 & m & 2\\m&1&2\\2&2&1\end{pmatrix}$$
对应的 Coxeter 图 $\Gamma$ 是

![](images/prism.svg){ width=120 }

$\Gamma$ 有两个连通分支，从而 $W$ 是可约的。
:::

我们主要关心的是 $\Gamma$ 不可约的情形。这是因为，如果 $\Gamma$ 包含的连通分支个数大于 1，则 $\Gamma$ 可以写成若干连通分支的并： $\Gamma=\Gamma_1\cup\cdots\cup\Gamma_k$，其中任何 $\Gamma_i$ 和 $\Gamma_j$ 之间互相没有边相连，即对任何 $s\in\Gamma_i$ 和 $t\in\Gamma_j$ 有 $m_{s,t}=2$，从而 $st=ts$，于是 $\Gamma_i$ 中的生成元与 $\Gamma_j$ 中的生成元两两交换，这时 $W$ 有直积分解 $W=W_1\times\cdots\times W_k$，其中 $W_1,\ldots,W_k$ 分别是 $\Gamma_1,\ldots,\Gamma_k$ 对应的 Coxeter 群。所以我们只要研究 $\Gamma$ 不可约的情形即可。

:::note
还有一种给 $\Gamma$ 的边标号的方式，叫做 Vinberg 记号，允许给 $m_{s,t}=\infty$ 的那些边用 $\leq-1$ 的实数作为标号。比如像下面这样：

![](images/level2.svg)

作为抽象 Coxeter 群，它和

![](images/3-4-inf.svg)

是同一个群，但是 $\infty$ 的边的标号是 $-1.1$，这样做相当于指定了这条边的两个顶点在几何实现中的镜面夹角。在后文中我们也会采用这种记号。
:::

对 $W$ 中的任一元素 $w$，它可能有许多种不同的方式表示为 $S$ 中生成元的乘积。在 $w$ 的所有表示中，长度最短的表示叫做 $w$ 的**既约表示**：即若 $w=s_1s_2\cdots s_k$ 是一个长度为 $k$ 的乘积，且 $w$ 不存在任何长度小于 $k$ 的表示，就称 $s_1s_2\cdots s_k$ 是 $w$ 的既约表示。$w$ 的既约表示可能不唯一，但它们都具有相同的长度。$w$ 的长度 $l(w)$ 就定义为 $w$ 的任意一个既约表示的长度。

$l(w)$ 具有如下的性质：

1. $l(xy)\leq l(x) + l(y)$。
2. $l(w) = l(w^{-1})$。
3. $l(w)=0$ 当且仅当 $w=1$。
4. $l(ws)=l(w)\pm 1$，其中 $w\in W, s\in S$。

前三点都是显然的，只有 4 需要证明。显然 $|l(ws)-l(w)|\leq 1$，所以只要说明 $l(ws)$ 和 $l(s)$ 不相等即可。这一步需要用到自由群的泛性质：

设 $F$ 是由集合 $S$ 生成的 [自由群](https://en.wikipedia.org/wiki/Free_group)，定义群同态 ${\rm sgn}: F\to{\pm1}$ 如下：对自由群 $F$ 的每个生成元 $s\in S$ 定义映射 ${\rm sgn}(s)=-1$，然后将此映射扩充为 $F$ 到 ${\pm1}$ 的群同态。容易验证 $(W,S)$ 的所有生成关系都属于这个同态的核，因此根据 [自由群的泛性质](https://en.wikipedia.org/wiki/Free_group#Universal_property)，${\rm sgn}$ 诱导了一个从 $(W,S)$ 到 ${\pm1}$ 的群同态。在此同态下，若 $w=s_1s_2\cdots s_k$ 是 $w$ 的任一既约表示，则 $${\rm sgn}(w)={\rm sgn}(s_1){\rm sgn}(s_2)\cdots{\rm sgn}(s_k)=(-1)^k=(-1)^{l(w)}.$$ 从而 ${\rm sgn}(ws)={\rm sgn}(w){\rm sgn}(s)=-{\rm sgn}(w)$ 说明 $l(ws)\ne l(w)$。
