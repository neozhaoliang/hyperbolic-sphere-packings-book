# 双曲球堆

::: definition
如果一个非空集合 $\P\subset V$ 满足下列条件，我们就称 $\P$ 是一个**球堆**：

1. 对任何 $k\in\P$ 有 $(k,k)=1$。
2. 对 $\P$ 中任何 $k\ne k'$ 有 $(k,k')\leq -1$。
:::

类似 $\P=\{k,-k\}$ 这样的球堆是平凡的，它对应单个球的内部和外部。反之则称为非平凡的。非平凡的球堆中的点必然两两互不共线。对一个非平凡的球堆 $\P$，$-\P=\{-k\mid k\in\P\}$ 也是非平凡的球堆，而且它翻转 $\P$ 中每个球的内部和外部。

记 $\H$ 是超平面 $\{v_{n+2}=1\}$ 与 $\Q_+$ 的截面，对任何满足 $(k,k)=1$ 的点 $k$，定义球帽
$$C_k = \{v\in\H\mid (v,k)\geq0\}.$$


::: {.lemma #disjoint-pair}
设 $\P$ 是球堆且 $k_1\ne k_2\in\P$，则 $C_{k_1}\cap C_{k_2}$ 和 $C_{-k_1}\cap C_{-k_2}$ 中必有一个至多只包含一个点。并且当恰好包含一个点时，此点与 $k_1+k_2$ 共线，并且 $(k_1,k_2)=-1$。
:::

**证明**：设 $u\in \ck1\cap \ck2$，$v\in \nck1\cap\nck2$，则有

1. $(u, k_1+k_2)\geq0$，$(v,k_1+k_2)\leq0$。
2. $(k_1+k_2,k_1+k_2)=2+2(k_1,k_2)\leq 0$。

如果 $(k_1+k_2,k_1+k_2)<0$，即 $k_1+k_2$ 是 time-like 的，则 $v\sim k_1+k_2$。但是 $u\sim v$，所以 $u\sim k_1+k_2$，从而 $(u,k_1+k_2)<0$，矛盾。所以 $k_1+k_2$ 是 light-like 的。

进一步如果 $(u,k_1+k_2)>0$ 且 $(v,k_1+k_2)<0$，则 $v\sim k_1+k_2$ 但是 $u\not\sim k_1+k_2$，这与 $u\sim v$ 矛盾。所以 $(u,k_1+k_2)$ 和 $(v,k_1+k_2)$ 中必然有一个是 0，即 $u$ 和 $v$ 中必有一个是 $k_1+k_2$ 的倍数，然而 $\H$ 中与 $k_1+k_2$ 共线的点是唯一确定的，所以 $\ck1\cap\ck2$ 和 $\nck1\cap\nck2$ 中必有一个至多包含一个点，且此点与 $k_1+k_2$ 共线。

:::{.lemma #intersect-pair}
设 $\P$ 是球堆且 $k_1\ne k_2\in\P$。如果 $v\in\H$ 满足 $(v,k_1)\geq0,\,(v,k_2)>0$，则 $|\ck1\cap\ck2|>1$。
:::

**证明**：记 $a=(v,k_2)>0$，考虑向量 $u=v-tk_2,\,t\in(0, a)$。

由于 $(u,u)=(v,v)+t^2-2at< 0$ 和 $(u,v)=(v,v)-at< 0$ 所以 $u\sim v$。从而 $u$ 的某个正倍数 $u'=cu\,(c>0)$ 属于 $\H$。

此外 $(u,k_1)=(v,k_1) - t(k_1,k_2)>0$，$(u,k_2)=a-t>0$，所以 $(u',k_1)>0,\, (u',k_2)>0$，从而 $u'\in\ck1\cap\ck2$。由于 $t\in(0,a)$ 有无穷多个取值，且它们对应的 $u'$ 互不相同，所以 $|\ck1\cap\ck2|>1$。

:::{.lemma #intersect-triple}
设 $\P$ 是球堆，$\ck1,\ck2,\ck3$ 是 $\P$ 中三个互不相同的球。如果 $\ck1\cap\ck2$ 只包含一个点 $v$，则 $v\notin\ck3$。
:::

**证明**：由于 $\ck1\cap\ck2$ 只包含 $v$，我们有 $(k_1,k_2)=-1$ 且 $v$ 与 $k_1+k_2$ 共线。特别地 $(v,k_1)=(v, k_2)=0$。

用反证法，若 $v\in\ck3$，则 $(v,k_3)\geq0$，于是 $(v,k_1+k_2+k_3)\geq0$。但是 $k_1+k_2+k_3$ 是一个 time-like 的向量：
$$(k_1+k_2+k_3,k_1+k_2+k_3)=3 + 2\sum_{i<j}(k_i,k_j)\leq -3 < 0.$$
所以只能是 $(v,k_1+k_2+k_3)=(v,k_3)>0$。记 $a=(v,k_3)>0$。

考察 $u=v-tk_3,\,t\in(0,a)$，仿照 @Pre:intersect-pair 中的证明，我们可以得到 $(u,u)<0,\,(u,v)<0$ 从而 $u\sim v$，从而 $u$ 的一个正倍数 $u'\in\H$，以及 $(u,k_1)>0,\, (u,k_2)>0$，从而 $u'\in\ck1\cap\ck2$。由于这样的 $t$ 有无穷多个，这与 $\ck1\cap\ck2$ 只包含一个点 $v$ 矛盾。


::: {.theorem #thm-sphere-packing}
设 $\P$ 是 $V$ 的一个非空子集，则下面两点是等价的：

1. $\P$ 是一个非平凡的球堆。
2. 对 $\P$ 或者 $-\P$ 之一，其包含的任何两个球帽 $C_k$ 和 $C_{k'}$ 至多有一个公共点。
:::
**证明**：

1 $\Rightarrow$ 2：根据 @Pre:disjoint-pair，我们可以不妨设 $k_1,k_2\in\P$ 使得 $C_{k_1}\cap C_{k_2}$ 至多包含一个点。我们来证明 $\P$ 中的所有球冠两两之间至多有一个公共点。为此设 $k\ne k'\in\P$ 且 $\{k,k'\}\ne\{k_1,k_2\}$，并设 $v\in C_k\cap C_{k'}$ 是一个公共点。记 $u=v-(v, k_2)k_2$，则我们有 $(u,k_2)=0$ 和
$$(u,u)=(u,v)=(v,v)-(v,k_2)^2 \leq0.$$
我们想说明 $u\sim v$，于是 $u$ 的某个正倍数 $u'=cu$ 属于 $\H$。结合 $(u,k_2)=0$ 可以得出 $u'$ 落在 $C_{k_2}$ 的边界上。注意到若上式中严格的不等号成立，那么 $(u,u)=(u,v)<0$ 自然可以推出 $u\sim v$；若等号成立则 $(v,v)=(v,k_2)=0$，从而 $u=v$，也有 $u\sim v$ 成立。于是 $u'$ 确实落在 $C_{k_2}$ 的边界上。

由于 $C_{k_1}\cap C_{k_2}$ 至多只有一个点，所以 $u'$ 落在 $C_{k_1}$ 的外部或者边界上，即
$$(u',k_1)=c(v-(v,k_2)k_2, k_1)=c(v, k_1-(k_1,k_2)k_2)\leq0.$$
记 $w=k_1-(k_1,k_2)k_2$，则 $w$ 满足 $(w,w)\leq0$ 和 $(v,w)\leq 0$。如果 $(w,v)<0$ 自然有 $w\sim v$；若 $(w,v)=0$ 但是 $w\not\sim v$，则必有 $(w,w)=(v,v)=0$，且 $v=cw\,(c<0)$，即 $w,v$ 是反向共线的 light-like 的向量。由 $(w,w)=0$ 可得 $(k_1,k_2)=-1$，即 $w=k_1+k_2$，从而 $v=c(k_1+k_2)$。$v$ 满足 $(v,k_1)=(v,k_2)=0$，从而 $v$ 就是 $\ck1$ 和 $\ck2$ 的唯一交点。$v$ 还满足 $(v,k)\geq0$ 和 $(v,k')\geq0$，并且由于 $\{k,k'\}\ne \{k_1,k_2\}$ 这俩不等式至少有一个严格成立，这与 @Pre:intersect-triple 矛盾。

总之 $w\sim v$，从而 $w$ 的某个正倍数 $w'$ 属于 $\H$。我们有 $(w',k)\leq 0$ 和 $(w',k')\leq0$，这两个不等式至少有一个是严格成立的，于是由 @Pre:intersect-pair $C_{-k}\cap C_{-k'}$ 包含多于 1 个点。于是由 @Pre:disjoint-pair $C_k\cap C_{k'}$ 恰好包含 $v$。

2 $\Rightarrow$ 1: 不妨设 $\P$ 中任何两个球帽至多只有一个交点。则对任何 $k_1,k_2\in\P$，内积 $\inn$ 限制在二维子空间 $U=\span\{k_1,k_2\}$ 上肯定不是正定的，否则的话 $U^\bot=k_1^\bot\cap k_2^\bot$ 是 time-like 的，从而 $\ck1$ 和 $\ck2$ 会在 $\H$ 的内部有交点，所以 $|(k_1,k_2)|\geq1$。如果是 $(k_1,k_2)\geq1$ 的话，则 $\ck1\cap\nck2$ 和 $\nck1\cap\ck2$ 二者中必有一个至多只包含一个点，不妨设为 $|\ck1\cap\nck2|\leq1$。但是根据已知 $\ck1\cap\ck2$ 也至多只包含一个点，从而 $\ck1$ 作为二者的并至多只有一个点，矛盾。

::: definition
记 $\Omega_r=\{\omega\in\Omega\mid (\omega,\omega)>0\}$ 是所有实权组成的集合，$\tc_r=\cone{\Omega_r}$ 是由所有实权生成的凸锥，以及
$$\myhat{\Omega_r}=\{\myhat{\omega}\mid \omega\in\Omega_r\}.$$
其中 $\myhat{\omega}=\omega/\sqrt{(\omega,\omega)}$ 是将 $\omega$ 归一化得到的单位向量。
:::

::: {.theorem #real-cone-closure}
如果 $W$ 是不可约、双曲的，且 level 大于等于 2，则 $\tcr = \cl{\tc}$。
:::

**证明**：只要证明 $\tcr$ 包含那些非实的基本权 $(\omega_s, \omega_s)\leq 0$ 即可。若如此则 $\tcr$ 包含所有的基本权 $\Delta^\ast$，从而包含 $\cone{\Delta}^\ast=\barfd$，再结合 $\tcr$ 是 $W-$ 不变的，即得 $\tcr$ 包含 $\tc$，从而包含 $\cl{\tc}$。

以下记 $I=S-\{s\}$，$W_I$ 为标准椭圆子群。

$(\omega_s,\omega_s)<0$ 的情形比较容易，这时 $\omega_s$ 是 time-like 的，其正交补 $V_I=\span\{\alpha_t,t\ne s\}$ 是 space-like 的，从而 $W_I$ 是有限群。任取一个实的基本权 $(\omega_t,\omega_t)>0$ 并考虑
$$v = \sum_{w\in W_I}w(\omega_t),$$
显然 $v\in\tcr$，并且 $W_I$ 保持 $v$ 不动。特别地对任何 $i\ne s$ 都有 $s_i(v)=v$。这是 $n-1$ 个独立的线性约束，其解空间是一维的，所以 $v$ 和 $\omega_s$ 共线：存在 $a\in\R$ 使得 $v=a\omega_k$。两边同时与 $\alpha_s$ 作内积得到
$$a = (\alpha_s,v)=\sum_{w\in W_I}(\alpha_s,w(\omega_t))=\sum_{w\in W_I}(w^{-1}(\alpha_s), \omega_t)=\sum_{w\in W_I}(w(\alpha_s), \omega_t).$$
对任何 $w\in W_I$，$w\alpha_s$ 形如 $w\alpha_s=\alpha_s+\sum_{t\in I}c_t\alpha_t$，所以 $w\alpha_s$ 仍然是正根，所有的系数 $c_t$ 都非负。由于 $\Gamma$ 是连通的，所以 $\Gamma$ 中存在一条从 $s$ 到 $t$ 的路径 $s=s_0\sim s_1\sim\cdots\sim s_m=t$，其中每个 $s_i,\,i\geq1$ 都属于 $I$ 且互不相同。不难验证对 $w=s_m\cdots s_1\in W_I$，在 $w\alpha_s$ 的表达式中 $\alpha_t$ 的系数大于 0，所以 $a$ 必然严格大于 0，所以 $\omega_s=v/a\in\tcr$。

如果 $(\omega_s, \omega_s)=0$，则其正交补 $\omega_s^\bot$ 是 light-like 的，于是子图 $\Gamma-\{s\}$ 是仿射的。特别地，$\Gamma-\{s\}$ 由一些仿射或者有限的连通成分组成，并且有且恰有一个连通成分是仿射的（注意 $\dim\omega_s^\bot=n-1$ 并且符号是 $(n-2,0)$，所以不能包含两个正交的 light-like 的向量）。任取一个实的基本权 $(\omega_t,\omega_t)>0$，我们需要讨论两种情况：

1. 如果 $\omega_t$ 属于某个有限型的连通成分 $Y$，类似上面的讨论，$v = \sum_{w\in W_Y}w(\omega_t)\in\tcr$ 满足对任何 $t\ne s$ 都有 $t(v)=v$，从而 $v$ 等于 $\omega_s$ 乘以一个正实数，从而 $\omega_s\in\tcr$。

2. 如果 $\omega_t$ 属于某个仿射型的连通成分 $X$，设 $Y=\Gamma - (X\cup\{s\})$ 是 $\Gamma-\{s\}$ 的除 $X$ 以外其它连通成分的并，则 $X$ 和 $Y$ 互不连通，从而
$$\omega_s = \underbrace{(\omega_s, \omega_s)}_{=0}\alpha_s + \sum_{t\ne s} (\omega_s, \omega_t)\alpha_t=\sum_{t\in X} (\omega_s,\omega_t)\alpha_t + \sum_{t\in Y} (\omega_s,\omega_t)\alpha_t=v_1+v_2.$$
这里 $v_1$ 和 $v_2$ 是正交的。于是
$$(\omega_s, \omega_s)=0\Rightarrow (v_1+v_2,v_1+v_2)=0\Rightarrow (v_1,v_1) + (v_2,v_2) = 0.$$
由于 $v_1\in V_X$ 来自不可约仿射型，$v_2\in V_Y$ 来自有限型，所以 $\R v_1=\rad(V_X)$ 并且 $v_2=0$，从而 $\omega_s=v_1$。于是 $\R \omega_s=\rad(V_X)$。从而 $\omega_s$ 表示为 $\{\alpha_i,i\in X\}$ 的线性组合时，所有的系数 $(\omega_s,\omega_i)$ 系数都是非零且同号的。我们断言它们都小于 0。实际上在
$$\omega_s=\sum_{i\in X} (\omega_s,\omega_i)\alpha_i$$
两边同时用 $\alpha_s$ 作内积有
$$1=(\omega_s,\alpha_s)=\sum_{i\in X} (\omega_s, \omega_i)\underbrace{(\alpha_s,\alpha_i)}_{\leq0}.$$
所以必须所有 $(\omega_s, \omega_i)<0$。所以 $X\cup \{s\}$ 构成的子图满足 @Pre:ideal-vertex 的条件，于是我们得到
$$\omega_s\in\cl{\cone{\bigcup_{w\in W_I}w(\omega_t)}}\subset\tcr.$$

::: {.theorem #max-packing}
若 $W$ 是双曲的，则 $\myhat{\Omega_r}$ 是非平凡的球堆当且仅当 $\Gamma$ 的 level 是 2，这时 $\myhat{\Omega_r}$ 还是极大球堆。
:::

**证明**：若 $\Gamma$ 的 level 是 2，根据 @Pre:level-2，$\Omega_r$ 中的元素两两分离，将其单位化后得到的 $\myhat{\Omega_r}$ 仍然两两分离，所以 $\myhat{\Omega_r}$ 的元素两两之间的内积 $\leq -1$，从而 $\myhat{\Omega_r}$ 确实给出一个球堆。如果存在某个球与任何 $\myhat{\Omega_r}$ 中的球都不相交或者相切的话，设这个球对应的单位向量是 $k\in\S$，则根据 @Pre:suff-for-disjoint，有 $(k,\myhat{\omega})\leq -1$ 对任何 $\myhat{\omega}\in\myhat{\Omega_r}$ 成立，从而 $(k,\omega)<0$ 对任何 $\omega\in\Omega_r$ 成立，从而 $(k,y)\leq0$ 对任何 $y\in\tcr=\cone{\Omega_r}$ 成立。根据 @Pre:real-cone-closure，$\tcr=\cl{\tc}$，这意味着 $(k,y)\leq0$ 对任何 $y\in\tc$ 成立，即 $-k\in\tc^\ast$。根据 @Pre:dual-cone-nonspace $(k,k)=(-k,-k)\leq0$，矛盾。这就证明了 level 2 时 $\Omega_r$ 是极大堆积。

反之若 $W$ 是双曲的并且 $\myhat{\Omega_r}$ 是一个非平凡球堆，$W$ 的 level 大于 1，所有的实权之间两两分离。然而任何非实权和其它任何权张成的子空间当然不可能是正定的，所以对任何两个基本权生成的二维子空间 $\span\{\omega_i,\omega_j\}$ 是 time-like 或者 light-like 的，从而 $\minus{\Gamma}{i,j}$ 是正定或者仿射的，所以 $\Gamma$ 的 level 只能是 2。$\blacksquare$