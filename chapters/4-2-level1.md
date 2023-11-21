## Level 1 是双曲的

本节来证明 level 1 的群都是双曲的。

首先是一个定义：

::: definition
+ 如果 $v\in V$ 满足 $(v, v)>0$，我们就称 $v$ 是**实的**。
+ 如果 $u,v\in V$ 满足 $(u,v)\leq 0$ 且 $u,v$ 张成的二维子空间 $\span\{u,v\}$ **不是正定**的，就称 $u,v$ 是**分离**的 (disjoint)。
:::

:::note
在 $\inn$ 是 Lorentzian 内积时，$v$ 是实的等价于 $v$ 是 space-like 的。
:::

::: {.lemma #lemma-uv}
如果 $\Gamma$ 的 level 大于等于 1，并且不是双曲的，则 $V$ 中存在两个互相正交的向量 $u,v$ 满足 $(u,u)<0$ 和 $(v,v)=0$。
:::

**证明**：由于 $\Gamma$ 的 level 大于等于 1，所以 $\inn$ 不可能是正定或者半正定的，显然也不可能是负定/半负定的（因为所有根 $\alpha$ 的范数都是 1），所以 $\inn$ 的正负惯性指数都非 0。如果 $W$ 不是双曲的，那么有两种可能：

1. $\inn$ 的负惯性指数是 1 且 $\rad(V)\ne\{0\}$。
2. $\inn$ 的负惯性指数至少是 2。

情形 1 可以取 $V$ 的一组正交基包含两个向量 $u,v$ 满足 $(u, u)=-1$ 和 $(v,v)=0$。情形 2 可以取 $V$ 的一组正交基包含三个向量 $x,y,z$ 满足 $(x,x)=1$ 和 $(y, y)=(z,z)=-1$，然后取 $u=z$ 和 $v=x+y$，则 $u,v$ 正交且 $(u,u)=-1,\,(v,v)=0$。$\blacksquare$

::: {.theorem #level-1}
@Maxwell82

如果 $\Gamma$ 的 level 是 1，则 $\Gamma$ 是双曲的。所有的基本权都不是实的并且两两分离。
:::

**证明**：首先注意到 $\Gamma$ 的 level 是 1 蕴含了 $\Gamma$ 是连通的，若不然，设 $\Gamma=\Gamma_1\cup\cdots\cup\Gamma_k$ 是多于一个连通分支的并，则每个分支 $\Gamma_i$ 作为删去其它分支后剩下的子图必须都是有限或者仿射的，但这导致 $\Gamma$ 的 level 是 0，矛盾。

我们需要证明三件事情：

1. 内积 $\inn$ 的符号是 $(n-1, 1, 0)$；
2. 任何基本权 $\omega_s$ 满足 $(\omega_s,\omega_s)\leq0$；
3. 任何两个基本权 $\omega_s,\omega_t\in\Delta^\ast$ 满足 $(\omega_s,\omega_t)\leq0$ 并且它们生成的二维子空间 $\span\{\omega_i,\omega_j\}$ 不是正定的。

先证明 1。用反证法，如果 $\Gamma$ 的 level 是 1 但不是双曲的，则根据 @Pre:lemma-uv 我们可以取两个正交的非零向量 $u,v$ 满足 $(u,u)<0,\, (v,v)=0$。

我们有如下两个断言：

1. 任何满足 $(u,u)<0$ 的向量 $u=\sum_{s\in S}u_s\alpha_s$ 其系数 $u_s$ 都非零且同号。
2. 任何满足 $(v,v)=0$ 的向量 $v=\sum_{s\in S}v_s\alpha_s$ 其系数 $v_s$ 至多只有一个为 0，其余都同号。

我们把这两个断言的证明放在后面，先承认它们是正确的，用它们来导出矛盾：

取 $s\in S$ 使得 $v_s\ne 0$，则 $u'=v_su-u_sv$ 满足 $(u',u')=v_s^2(u,u)<0$ 且 $u'$ 的 $\alpha_s$ 项的系数 $u'_s=0$。但根据断言 1，$u'$ 的系数必须非零且同号，这就导致了矛盾，所以 $\Gamma$ 必然是双曲的，从而结论 1 成立。

再来证明结论 2。

注意到对任何 $s\in S$，由于子图 $\minus{\Gamma}{s}$ 的 level 等于 0，所以 ${\rm span}\{\alpha_t,t\ne s\}$ 是有限或者仿射的 $n-1$ 维子空间。它的正交补显然是 $\omega_s$ 张成的一维子空间 $\R\omega_s$，再结合 $\inn$ 是双曲的我们有 $(\omega_s,\omega_s)\leq 0$，所以 $\{\omega_s\}_{s\in S}$ 都不是实的。

再来证明结论 3。

设 $\omega_s=\sum_{t\in S}c_t\alpha_t$，两边用 $\omega_t$ 作内积不难看出 $c_t=(\omega_s,\omega_t)$，所以

$$\omega_s = (\omega_s,\omega_s)\alpha_s + \sum_{t\ne s} (\omega_s,\omega_t)\alpha_t.$$

结论 2 中已经证明了必然有 $(\omega_s,\omega_s)\leq0$。根据断言我们有：

1. 如果 $(\omega_s,\omega_s)<0$，则后面所有的系数 $(\omega_s,\omega_t)$ 都小于 0。
2. 如果 $(\omega_s,\omega_s)=0$，则后面所有的系数 $\{(\omega_s,\omega_t)\}_{t\ne s}$ 都不为 0 且同号。我们来确定它们的符号：根据
$$1=(\omega_s,\alpha_s) = (\omega_s,\omega_s) + \sum_{t\ne s} (\omega_s,\omega_t)(\alpha_t,\alpha_s)=\sum_{t\ne s} (\omega_s,\omega_t)(\alpha_t,\alpha_s),$$
由于对所有的 $t\ne s$ 有 $(\alpha_s,\alpha_t)\leq 0$，所以只能是 $(\omega_s,\omega_t)<0$。

总之我们说明了对任何 $s\ne t$ 都有 $(\omega_s,\omega_t)<0$。此外二维子空间 $U={\rm span}\{\omega_s,\omega_t\}$ 的正交补是 $U^\bot={\rm span}\{\alpha_{k},\,k\ne s,t\}$，根据 @Pre:level-l $U^\bot$ 是正定的，所以 $U$ 必然是双曲的，从而 $\{\omega_s,\omega_t\}$ 是分离的。

最后我们来给出断言 1 和 2 的证明。这两个断言的证明并不困难，但是比较琐碎。

首先是断言 1 的证明。记

$$I_+=\{s\in S\mid u_s>0\},\quad I_-=\{s\in S\mid u_s<0\},\quad I_0=\{s\in S\mid u_s=0\}.$$
并记 $u_+=\sum_{s\in I_+}u_s\alpha_s$，$u_-=\sum_{t\in I_-}u_t\alpha_t$，则 $u=u_++u_-$ 且
$$(u,u)=(u_+,u_+) + (u_-,u_-) + 2(u_+,u_-)<0.$$
但是注意到
$$(u_+, u_-)=\sum_{s\in I_+}\sum_{t\in I_-}\underbrace{u_s}_{>0}\underbrace{u_t}_{<0}\underbrace{(\alpha_s,\alpha_t)}_{\leq0}\geq 0.$$
所以 $(u_+, u_+) < 0$ 和 $(u_-, u_-)<0$ 中至少有一个成立，不妨设 $(u_+, u_+)<0$。如果 $I_-\cup I_0$ 不是空集，那么 $I_+$ 作为从 $\Gamma$ 中删去 $I_-\cup I_0$ 后得到的真子图包含 time-like 的向量 $u_+$，这与 $\Gamma$ 的 level 等于 1 矛盾。所以 $I=I_+$，即所有系数 $u_s$ 都大于 0。相应地如果是 $(u_-,u_-)<0$ 的话则所有 $u_s$ 都小于 0。

对断言 2 我们仍然采用类似的记号，记
$$I_+=\{s\in S\mid v_s>0\},\quad I_-=\{s\in S\mid v_s<0\},\quad I_0=\{s\in S\mid v_s=0\}.$$
并记 $v_+=\sum_{s\in I_+}v_s\alpha_s$，$v_-=\sum_{t\in I_-}v_t\alpha_t$，则同样有 $(v_+,v_-)\geq0$。

我们想证明 $|I_0|\leq1$，并且 $I_+$ 和 $I_-$ 中必有一个是空集。

如果 $|I_0|\geq2$，那么 $(v, v)=0$ 说明删除 $I_0$ 以后得到的子图不是有限的，这与 $\Gamma$ 的 level 是 1 和 @Pre:level-l 矛盾。所以 $|I_0|\leq 1$。

如果 $I_+,\,I_-$ 都不是空集的话，则 $v_+,v_-$ 都非零，并且必然有 $(v_+, v_+)\geq0$ 且 $(v_-, v_-)\geq0$，否则删掉 $I_+$ 或者 $I_-$ 以后剩下的子图不是有限或者仿射的，与 $\Gamma$ 的 level 是 1 矛盾。然而
$$0=(v, v) = (v_+,v_+) + (v_-,v_-) + 2(v_+,v_-).$$
三个非负数的和等于 0，只能是 $(v_+,v_+) = (v_-,v_-) =(v_+, v_-)=0$。现在分情况讨论：

1. 如果 $|I_0|=1$，那么删掉 $I_-\cup I_0$ 会至少删掉两个顶点，但 $(v_+,v_+)=0$ 说明剩下的子图不是有限的，与 $\Gamma$ 的 level 是 1 和 @Pre:level-l 矛盾。
2. 如果 $I_0=\emptyset$，则 $S=I_+\cup I_-$。然而 $(v_+,v_-)=\sum_{s\in I_+,\,t\in I_-}v_sv_t(\alpha_s,\alpha_t)=0$ 说明对任何 $s\in I_+,\,t\in I_-$ 有 $(\alpha_s,\alpha_t)=0$，从而 $I_+$ 和 $I_-$ 将 $\Gamma$ 分成互不连通的两个集合，这与 $\Gamma$ 连通矛盾。

总之 $I_+$ 和 $I_-$ 必有一个是空集，断言 2 得证。

至此定理得证。$\blacksquare$

::: {.corollary #level-1-tits}
若 $W$ 的 level 为 1，则 Tits 锥的闭包 $\cl{\tc}$ 等于 $\Q_+$ 或者 $\Q_-$ 之一（加上原点）。
:::

**证明**：由于 level 1 的群是双曲的，根据 @Pre:tits-closure，$\cl{\tc}$ 包含 $\Q$ 的一个连通分支，不妨设为 $\cl{\tc}\supset\Q_+$。还要再证明反向的包含关系。为此只要证明 $\cl{\tc}\subset\Q$ 和 $\cl{\tc}\cap\Q_-=\emptyset$。

根据 @Pre:level-1，所有的基本权 $\{\omega_s\}$ 都不是实的且两两分离，所以它们都属于 $\Q$。对任意 $x\in\barfd$，设 $x=\sum_{s\in S}c_s\omega_s$，其中每个 $c_s\geq0$，则
$$(x,x)=\sum_{s,t\in S}c_sc_t\underbrace{(\omega_s,\omega_t)}_{\leq0}\leq0.$$
即 $\barfd\subset\Q$。$W$ 作为正交变换群保持 $\Q$ 不变，所以 $\tc=\bigcup\limits_{w\in W}w\barfd\subset\Q$，从而 $\cl{\tc}\subset\Q$。

还需要说明 $\cl{\tc}\cap\Q_-=\emptyset$。首先注意到 $\tc^\ast$ 必然包含某个 time-like 的向量 $(z,z)<0$。否则根据 @Pre:dual-cone-nonspace $\tc^\ast$ 中的非零向量都是 light-like 的。由于 $\inn$ 是双曲的，$\tc^\ast$ 不能包含两个线性无关的 light-like 的向量（否则它们的正线性组合会得到 time-like 的向量），所以 $\tc^\ast$ 由一个 light-like 的向量 $\delta$ 生成。取对偶得到 $\cl{\tc}=\{v\in V\mid (v,\delta)\geq0\}$，这是一个半空间，显然包含 space-like 的向量，这与 $\cl{\tc}\subset\Q$ 矛盾。所以我们确实可以取 $z\in\tc^\ast$ 满足 $(z,z)<0$。显然 $z\in\Q_-$，于是对任何 $x\in\Q_-$ 有 $(z,x)<0$，而 $(z,\cl{\tc})\geq0$，从而 $\cl{\tc}\cap\Q_-=\emptyset$。$\blacksquare$

下面的结论来自 @Maxwell89。

:::{.proposition #ideal-vertex}
设 $s\in S$ 使得如下条件成立：

1. $(\omega_s,\omega_s)=0$。
2. 子图 $\minus{\Gamma}{s}$ 是不可约、仿射的。
3. 对任何 $t\ne s$ 有 $(\omega_s,\omega_t)<0$。

记 $I=\minus{S}{s}$，则对任意的 $p\in\barfd$ 都有 $\omega_s\in\cl{\cone{\bigcup_{w\in W_I}wp}}$。
:::

:::note
注意这里没有要求 $W$ 必须是双曲的，也没有限制 $W$ 的 level。

此外 $\bigcup_{w\in W_I}wp$ 是一个无限集，$\cone{\bigcup_{w\in W_I}}$ 未必是闭的，因此闭包记号不可少。

当 $W$ 的 level 是 1 时，若 $\omega_s$ 是一个位于双曲空间边界上的理想顶点，则命题的条件都满足。这时经过 $\omega_s$ 的那些镜面生成的椭圆子群会把基本区域无限压缩到 $\omega_s$ 附近，如下图所示：
![](images/ideal-vertex.jpg){width=300}
:::

**证明**：由已知子空间 $V_I=\span\{\alpha_t,\,t\ne s\}$ 是仿射的，并且 $\rad(V_I)$ 是一维的。由
$$\omega_s = \underbrace{(\omega_s,\omega_s)}_{=0}\alpha_s +  \sum_{t\ne s}(\omega_s, \omega_t)\alpha_t = \sum_{t\ne s}(\omega_s, \omega_t)\alpha_t\in V_I,$$
所以 $\R\omega_s=\rad(V_I)$。于是 $W_I$ 保持 $\omega_s$ 不动，即
$$\R\omega_s\xrightarrow{\ W_I - 1\ } = 0.$$
从而 $W_I$ 同样作用在商空间 $V_I/\R\omega_s$ 上，此作用给出了一个同态 $W_I\to\gl(V_I/\R\omega_s)$。令 $K$ 为此同态的核，则对任何 $w\in K$，
$$w(v + \R\omega_s) = v + \R\omega_s,\quad v\in V_I.$$
即
$$V_I\xrightarrow{\ K - 1\ }\R\omega_s\xrightarrow{\ W_I - 1\ } = 0.$$
由于 $K\leqslant W_I$，所以
$$V_I\xrightarrow{\ K - 1\ }\R\omega_s\xrightarrow{\ K-1\ }0.$$
即 $(K-1)^2$ 在整个 $V_I$ 上恒为 0。

更进一步，对任何 $w\in K$，$w\alpha_s$ 形如 $w\alpha_s=\alpha_s+\sum\limits_{t\ne s}c_t\alpha_t$，所以 $(w-1)\alpha_s\in V_I$，从而
$$V\xrightarrow{\ K-1\ } V_I\xrightarrow{\ K - 1\ }\R\omega_s\xrightarrow{\ K-1\ }0.$$
即 $(K-1)^2V\subset\R\omega_s$，$(K-1)^3V\equiv0$。

如果 $p$ 是 $\omega_s$ 的正倍数，则结论是平凡的。否则取 $w\in K$ 且 $w\ne 1$，由于 $w$ 在 $V_I$ 上不是恒等变换，所以存在 $t\in I$ 使得 $w\alpha_t\ne\alpha_t$。设 $w\alpha_t=\alpha_t+a\omega_s,\,a\ne 0$，并构造换位子 $w_1=twtw^{-1}\in K$，则由 $(K-1)^2V\subset\R\omega_s$ 有 $(w_1-1)^2p=b\omega_s,\,b\in\R$。我们来计算 $b$。

记 $\beta = w\alpha_t=\alpha_t+a\omega_s$，则 $wtw^{-1}=s_\beta$，所以
$$\begin{align*}
s_\beta(p)&=p - 2(p,\beta)\beta\\
&=p-2(p,\beta)(\alpha_t+a\omega_s)\\
&=p-2(p,\beta)\alpha_t-c\omega_s\\
&=p-2(p,\alpha_t+a\omega_s)\alpha_t-c\omega_s\\
&=p-2(p,\alpha_t)\alpha_t- 2a(p, \omega_s)\alpha_t - c\omega_s\\
&=t(p) - 2a(p, \omega_s)\alpha_t - c\omega_s.
\end{align*}$$
其中 $c=2(p,\alpha_t+a\omega_s)a$ 是实数。于是
$$(w_1-1)p=ts_\beta(p)-p=-2a(p, \omega_s)t(\alpha_t) - ct(\omega_s)=2a(p,\omega_s)\alpha_t - c\omega_s.\label{eq:wp1}\tag{1}$$
其中我们利用了 $t(\alpha_t)=-\alpha_t$ 和 $t(\omega_s)=\omega_s$。继续由于 $(w_1-1)\omega_s=0$，所以
$$(w_1-1)^2p = 2a(p,\omega_s)(w_1-1)\alpha_t.\label{eq:wp2}\tag{2}$$
对于 $(w_1-1)\alpha_t$，我们可以在 $(\ref{eq:wp1})$ 式中取 $p=\alpha_t$，得到
$$(w_1-1)\alpha_t=2a\underbrace{(\alpha_t,\omega_s)}_{=0}\alpha_t -c\omega_s=-c\omega_s= -2(\alpha_t,\alpha_t+a\omega_s)a\omega_s=-2a\omega_s.$$
将其代入 $(\ref{eq:wp2})$ 中我们得到 $(w_1-1)^2p=-4a^2(p,\omega_s)\omega_s$，即 $b=-4a^2(\omega_s,p)$。由于 $p\in\barfd=\cone{\Delta^\ast}$ 是 $\Delta^\ast$ 的非负线性组合，设 $p=\sum c_t\omega_t,\,c_t\geq0$，则 $(p,\omega_s)=\sum_{t\ne s}c_t(\omega_s,\omega_t)$。又由于 $p$ 与 $\omega_s$ 不共线，所以至少有一个 $t\ne s$ 满足 $c_t>0$。而已知对任何 $t\ne s$ 有 $(\omega_s,\omega_t)<0$，所以 $(\omega_s, p)<0$，从而 $b>0$。

最后利用 $(w_1-1)^3=0$ 和 $(w_1-1)^2p=b\omega_s$ 我们得到对任何 $N\geq 1$ 有
$$w_1^N(p)=(1 + w_1-1)^N(p)= p + \binom{N}{1}(w_1-1)(p) + \binom{N}{2}b\omega_s,$$
可见 $\lim\limits_{N\to\infty}\dfrac{w_1^Np}{\binom{N}{2}b} = \omega_s$，即得所证。$\blacksquare$