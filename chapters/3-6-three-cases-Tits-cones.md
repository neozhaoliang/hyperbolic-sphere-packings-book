## 三种情形的 Tits 锥

这一节我们来研究当 $W$ 分别是有限、仿射和双曲三种情形时，其几何实现中 Tits 锥 $\tc$ 和对偶锥 $\tc^\ast$ 的结构。本节中我们限定 $W$ 都是不可约的。

### 有限

在有限的情形，一个熟知的结论是，$W$ 是有限群当且仅当内积 $\inn$ 是正定的 [见 @Humphreys90 section 6.4]。我们来证明这还等价于 $\tc=V^\ast$：

:::{.theorem #finite-tits-V}
Tits 锥 $\tc=V^\ast$ 当且仅当 $W$ 是有限群。
:::

![图中红色标注的锥是基本区域，其在 $W$ 作用下密铺整个空间](images/Tits_finite.png){width=350}

**证明**：

$\Rightarrow$: $\tc=V^\ast$ 当然可以推出 $-\fd\in\tc$（$\fd$ 是基本区域），而对任何 $x\in-\fd$ 都有 $\Phi^+\subseteq \negf{x}$，根据 @Pre:tits-neg-finite $|\Phi^+|=|\negf{x}|<\infty$，从而 $\Phi^+$ 是有限集，从而 $\Phi$ 也是有限集。

$\Leftarrow$: $W$ 是有限群说明 $\Phi$ 也是有限的，从而对任何 $x\in V^\ast$ 都有 $|\negf{x}|\leq |\Phi^+|<\infty$，仍然根据 @Pre:tits-neg-finite 有 $x\in\tc$。$\blacksquare$

我们还需要另一种 $W$ 有限的刻画方式，它在后面分析仿射和双曲的情形时会用到。

:::{.proposition #phi-J-finite}
设 $W$ 是不可约 Coxeter 群。如果存在 $J\subsetneqq S$ 使得 $\Minus{\Phi}{\Phi_J}$ 是有限集，则 $W$ 必然是有限群。
:::

**证明**：由于 $J\subsetneqq S$ 所以 $\Minus{\Phi}{\Phi_J}$ 是非空的。我们考虑 $W$ 的 Coxeter 图 $\Gamma$：由于 $W$ 不可约，所以对任何 $s\in S$ 都存在一条连接 $s$ 和 $\Minus{S}{J}$ 的路径：即存在 $s_0,s_1,\ldots,s_m$ 使得
$$s_0=s\sim s_1\sim\cdots\sim s_m\in \Minus{S}{J}.$$
我们称 $m$ 为这条路径的长度。所有这样的路径的最短长度是 $s$ 和 $\Minus{S}{J}$ 之间的图距离，记作 $d(s)$。于是 $d(s)=0$ 当且仅当 $s\in\Minus{S}{J}$。

我们按照 $d(s)$ 的升序对 $S$ 重新排序，得到 $S=\{s_1,s_2,\ldots,s_n\}$，使得对任何 $i<j$ 都有 $d(s_i)\leq d(s_j)$。于是 $\Minus{S}{J}$ 中的顶点都排在最前面，即存在 $1\leq r<n$ 使得 $\Minus{S}{J}=\{s_1,\ldots,s_r\}$。然后把 $\Phi^+$ 拆成 $n$ 个不相交集合的并：记 $\Phi_i^+$ 是所有可以由 $\{\alpha_i,\ldots,\alpha_n\}$ 张成，且 $\alpha_i$ 项系数不为 0 的正根组成的集合：
$$\Phi_i^+=\{\lambda\mid \lambda\in\Phi^+,\ \lambda=\sum_{j=i}^nc_j\alpha_j,\ c_i\ne 0\}.$$
则不难看出有 $\Phi^+=\Phi_1^+\cup\cdots\cup\Phi^+_n$，以及 $\Minus{\Phi^+}{\Phi_J^+}=\Phi_1^+\cup\cdots\cup\Phi^+_r$。由于假设了 $\Minus{\Phi}{\Phi_J}$ 是有限的，所以 $\Phi_1^+,\ldots,\Phi^+_r$ 都是有限的。

我们用归纳法依次论证 $\Phi^+_{r+1},\ldots,\Phi^+_{n}$ 也都是有限集：设 $r+1\leq i\leq n$ 且已知对所有 $j<i$，$\Phi_1^+,\ldots,\Phi^+_j$ 都是有限集，
现在观察 $\Phi^+_i$，注意必然有 $d(s_i)\geq1$，所以存在 $j<i$ 使得 $d(s_j)<d(s_i)$ 且 $s_j\sim s_i$。集合 $s_j\Phi_i^+$ 仍然都是正根，并且它们的 $\alpha_j$ 项系数都不是 0，从而 $s_j\Phi_i^+\subset\Phi^+_j$，于是 $|\Phi_i^+|\leq |\Phi^+_j|$ 从而也是有限集。

于是所有 $\Phi^+_1,\ldots,\Phi^+_n$ 都是有限集，从而 $\Phi$ 也是有限的，根据 @Pre:w-phi-both-finite-infinite $W$ 是有限群，命题得证。$\blacksquare$

这个命题有如下的推论：

:::{.corollary #tits-cone-pointed}
如果 $W$ 不可约且是无限群，则 Tits 锥 $\tc$ 满足 $\tc\cap-\tc=\{0\}$，从而 $\tc$ 是一个点锥 (pointed cone)。
:::

**证明**：由于
$$\tc\cap-\tc=\bigcup_{w_1,w_2\in W}w_1\barfd\cap w_2(-\barfd),$$
所以若 $\tc\cap-\tc\ne\{0\}$ 则存在非零向量 $x\in\barfd$ 和 $w\in W$ 满足 $-wx\in\barfd$。令
$$J=\{s\in S\mid \lfun{\alpha_s}{x}=0\},$$
则 $x\ne 0$ 说明 $J\subsetneqq S$ 是真子集，且对任何 $\lambda\in\Minus{\Phi^+}{\Phi^+_J}$ 都有 $\lfun{\lambda}{x}>0$，并且对这样的 $\lambda$ 有
$$\lfun{w\lambda}{-wx} = \lfun{\lambda}{-x}<0.$$
而 $-wx\in\barfd$，所以 $w\lambda$ 是负根，从而 $\Minus{\Phi^+}{\Phi^+_J}\subset\negf{w}$，从而 $|\Minus{\Phi^+}{\Phi^+_J}|\leq |\negf{w}|=l(w)<\infty$，由 @Pre:phi-J-finite $W$ 是有限群，这与已知矛盾。

:::{.corollary #dual-cone-non-trivial}
如果 $W$ 不可约且是无限群，则对偶锥 $\tc^\ast\ne\{0\}$。
:::

**证明**：用反证法，若不然，则 $\bartc=\tc^{\ast\ast}=V^\ast$ 是全空间。由于一个凸集的内点和它的闭包的内点集相同，所以 $\tc=V$，这与 @Pre:tits-cone-pointed 的结论 $\tc$ 是点锥矛盾。

### 仿射

在本节中，我们需要如下关于不可约仿射 Coxeter 群的事实 [见 @Humphreys90 section 2.6, 6.5]。

::: {.blockquote #affine-facts}
设 $W$ 是不可约、仿射 Coxeter 群，则：

1. $\rad(V)$ 的维数是 1，它由一个向量 $\delta=\sum_{s\in S}z_s\alpha_s$ 生成，其中每个 $z_s>0$。
2. $\delta$ 的坐标 $z=(z_1,\ldots,z_s)^T$ 满足 $Az=z^TAz=0$，其中 $A=((\alpha_s, \alpha_t))_{s,t\in S}$ 是内积 $\inn$ 的 Gram 矩阵。
3. $w\delta=\delta$ 对所有 $w\in W$ 成立。
4. $A$ 的任何 $\leq n-1$ 阶主子式都是正定的。
:::

我们花点笔墨解释一下这几个事实的含义。回忆 $W$ 称作仿射是指内积 $\inn$ 是半正定但不是正定的。这个定义中没有要求 $\inn$ 的符号中有几个 0，但是上面的结论 1, 2 告诉我们，在 $W$ 不可约的前提下，$\inn$ 的符号中有且只有一个 0，并且 $\rad(V)$ 由一个向量 $\delta$ 生成。$\delta$ 的所有系数都非零并且同号，并且 $W$ 保持 $\delta$ 不动。

我们来快速验证一下 3。由 $z^TA=0$ 可得对任何 $t\in S$ 有 $\sum z_s(\alpha_s,\alpha_t)=(\delta,\alpha_t)=0$，从而 $t(\delta)=\delta-2(\delta,\alpha_t)\alpha_t=\delta$，即任何单反射保持 $\delta$ 不动，从而 $W$ 保持 $\delta$ 不动。

4 说的是对任何 $I\subsetneqq S$，标准椭圆子群 $W_I$ 都是有限群；或者等价地，从 $W$ 的 Coxeter 图 $\Gamma$ 中删去至少一个顶点以后，剩下的子图是有限的。

:::{.theorem #tits-cone-affine}
在仿射的情形 $\tc^\ast$ 是一条射线：$\tc^\ast=\{c\delta\mid c\geq0\}$，Tits 锥是以 $\delta$ 为法向量的半空间加上原点：$\tc=\{0\}\cup\{\delta > 0\}$。
:::

![图中红色标注的是基本区域，其在 $W$ 作用下密铺了整个上半空间](images/Tits_affine.png){width=350}

**证明**：我们已经知道 $\rad(V)=\R\delta$。根据 @Pre:dual-cone-non-trivial，$\tc^\ast$ 包含非零向量，且对任何这样的非零向量 $v$，根据 @Pre:dual-cone-nonspace 有 $(v,v)\leq0$，再结合 $\inn$ 半正定可得 $(v,v)=0$，即 $v\in\rad(V)$，从而 $v$ 与 $\delta$ 共线，从而 $\{0\}\ne\tc^\ast\subseteq\mathbb{R}\delta$。

再结合 $\tc^\ast\cap-\tc^\ast=\{0\}$，以及 $\delta$ 是 $\{\alpha_s\}$ 的正线性组合，即得 $\tc^\ast=\{c\delta\mid c\geq0\}$。这就给出了对偶锥 $\tc^\ast$ 的刻画。

再来分析 Tits 锥 $\tc$。取对偶我们得到 $\overline{\tc}=\tc^{\ast\ast}=\{\delta\geq0\}$。我们将证明 $\tc$ 不包含超平面 $\{\delta=0\}$ 的除去 0 以外的任何点，但是包含超平面 $\{\delta>0\}$ 的所有点，这就证明了 $\tc=\{0\}\cup\{\delta > 0\}$。

首先对任何 $x\in\{\delta=0\}$，若 $x\in\tc=\bigcup\limits_{w\in W}w\barfd$，则存在 $w\in W$ 和 $y\in\barfd$ 使得 $x=wy$。于是
$$0 = \lfun{\delta}{x}=\lfun{\delta}{wy}=\lfun{w^{-1}\delta}{y}=\lfun{\delta}{y}=\sum_{s\in S}z_s\lfun{\alpha_s}{y}.$$
即 $0=\sum_{s\in S}z_s\lfun{\alpha_s}{y}$。然而每个 $z_s>0$，并且由于 $y\in\barfd$ 所以每个 $\lfun{\alpha_s}{y}\geq0$，这只能是 $\lfun{\alpha_s}{y}=0$ 对所有 $s\in S$ 成立。结合 $\{\alpha_s\}$ 是 $V$ 的一组基，这导致 $y=0$，从而 $x=0$，所以超平面 $\{\delta=0\}$ 中属于 $\tc$ 的只有 0。

由于一个凸集的内点和它的闭包的内点集相同，所以 $\tc^\circ=\{\delta>0\}$，于是 $\{\delta>0\}\subset\tc$，这就证明了 $\tc=\{0\}\cup\{\delta>0\}$。

### 双曲

我们已经给出了有限和仿射的情形 Tits 锥和对偶锥的完整刻画，但对双曲的情形，Tits 锥的结构要复杂许多，一般来说没有完整的刻画。

为了简化记号，我们记 $\Q_+$ 和 $\Q_-$ 的内点分别为 $\N_+$ 和 $\N_-$，即 $\N_+$ 和 $\N_-$ 分别是 $\N=\{v\in V\mid (v,v)<0\}$ 的两个连通分支。

在双曲的情形，由于内积 $\inn$ 非退化，所以我们可以把 $V$ 和 $V^\ast$ 等同起来，从而根系 $\Phi$ 和 Tits 锥 $\tc$ 都在 $V$ 中。

我们将证明在双曲的情形，Tits 锥的闭包 $\cl{\tc}$ 必然包含 $\Q_+,\,\Q_-$ 中的一个，同时与另一个的交为空。由于 $\tc$ 的内点和 $\cl{\tc}$ 的内点相同，这意味着 $\tc$ 也恰好包含 $\N_+$ 和 $\N_-$ 中的一个。

::: {.proposition #dual-cone-trivial-intersection}
在 $W$ 不可约且双曲的情形，$\tc^\ast\cap \Q_+,\,\tc^\ast\cap\Q_-$ 中必有一个是空集。
:::

**证明**：若 $u\in\tc^\ast\cap\Q_+,\,u'\in \tc^\ast\cap\Q_-$，设 $u=x+cz,\,u'=y+dz$ 是 [如前面讨论的分解](#lorentzinian-decomposition)，则 $c>0,\,d<0$。考察 $v=cu'-du=cy-dx\in(\R z)^\bot$，由于 $(\R z)^\bot$ 是 space-like 的子空间，所以 $(v,v)\geq0$。但是 $v$ 是 $u$ 和 $u'$ 的非负线性组合，所以 $v\in\tc^\ast$，根据 @Pre:dual-cone-nonspace 必须有 $(v,v)\leq0$，从而由正定性得到 $v=0$，于是 $cu'=du$。再结合 $c,d$ 异号可得 $u$ 和 $-u$ 同时属于 $\tc^\ast$，从而同时属于 $\cone{\Delta}$。这只能导致 $u=0$，矛盾。所以 $\tc^\ast\cap\Q_+$ 和 $\tc^\ast\cap\Q_-$ 中必有一个是空集。

::: {.corollary #dual-cone-belongs-branch}
在双曲的情形，必有 $\tc^\ast\subset\Q_+$ 和 $\tc^\ast\subset\Q_-$（加上原点）之一成立。
:::

**证明**：根据上面的推论和 @Pre:dual-cone-nonspace 即得。

::: {.corollary #tits-closure}
在双曲的情形，Tits 锥 $\tc$ 包含 $\N_+$ 或者 $\N_-$ 之一。
:::

![图中红色的锥是基本区域 $\fd$，在 $W$ 作用下 $\tc$ 密铺了 $\N_+$](images/Tits_hyperbolic.png){width=350}

**证明**：首先注意到对任何 $x\in\Q_+$ 和 $y\in\Q_-$ 有 $(x,y)\geq0$，所以 $\Q_+$ 和 $\Q_-$ 互相包含在对方的对偶锥中。

由 @Pre:dual-cone-belongs-branch，不妨设 $\tc^\ast\subseteq\Q_+$（加上原点），利用 @Pre:dual-dual-cone 取对偶以后有 $\overline{\tc}=\tc^{\ast\ast}\supseteq \Q_+^\ast\supseteq\Q_-$，即 $\overline{\tc}\supset\Q_-$。由于凸集的内点等于其闭包的内点，即得 $\tc\supset\Q_-^\circ=\N_-$。

$\blacksquare$

:::note
注意 $\tc$ 未必包含 $\Q_+$ 或者 $\Q_-$ 的边界。例如对 $(3,3,7)$ 类型的双曲密铺，圆盘边界上的点无法经过有限次反射变换到基本区域中，所以边界不属于 $\tc$。
![](images/compact.png){width=400}
:::

在下一章中，我们将看到，对 level 1 的群，$\overline{\tc}$ 是包含在 $\Q$ 中的，从而恰好等于 $\Q_+,\Q_-$ 之一。而对 level 大于等于 2 的群，$\overline{\tc}$ 一定有一部分落在 $\Q$ 的外面。