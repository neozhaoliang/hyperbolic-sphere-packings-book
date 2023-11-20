## Tits 锥

在获得了 $V$ 中关于根系的一些知识后，我们下面将转移到 $V$ 的对偶空间 $V^\ast$ 中，讨论万花筒的结构。

设 $V^\ast$ 是 $V$ 的对偶空间，我们有一个自然的双线性映射
$$V\times V^\ast\to\R: \lfun{v}{f}= f(v).$$
任何 $V$ 上的可逆线性变换 $g\in\gl(V)$ 同样作用在 $V^\ast$ 上：对任何 $f\in V^\ast$，线性泛函 $gf$ 定义为
$$(g f)(v) = f(g^{-1} v).$$
这个定义的好处是它保持上面的双线性映射 $\lfun{\,}{}$ 不变：
$$\lfun{gv}{gf} = \lfun{v}{f}.$$
于是
$$\lfun{gv}{f} = \lfun{v}{g^{-1}f}.$$
特别当 $g=s$ 是一个反射时，由于 $s=s^{-1}$ 所以
$$\lfun{sv}{f} = \lfun{v}{sf}.$$
这种将反射在 $\inn{\,}{}$ 两边跳来跳去的技巧后面会经常用到。

由于 $V$ 和 $V^\ast$ 互为对偶空间，所以 $\Delta=\{\alpha_s\}$ 是 $V^\ast$ 上的一组线性无关的泛函，定义它们的正半空间的交为
$$\fd = \bigcap_{s\in S}\{x\in V^\ast\mid \lfun{\alpha_s}{x} > 0\}.$$
你可以把 $\fd$ 理解为万花筒中原像所在的房间，$\alpha_s=0$ 是房间的墙壁。$\fd$ 总是 $V^\ast$ 中的非空开集，其闭包记作 $\barfd$，$\barfd$ 就是 $\fd$ 加上了房间四周的墙壁。

$W$ 同样作用在 $V^\ast$ 上：
$$\lfun{w\lambda}{v} = \lfun{\lambda}{w^{-1}v}.\quad \lambda\in V^\ast,\, v\in V.$$
不难验证在此定义下，$W$ 也同构地映射为 $V^\ast$ 上的反射群。

::: definition
定义 **Tits 锥**为
$$\tc = \bigcup_{w\in W} w\barfd.$$
Tits 锥 $\tc$ 即为万花筒，它是 $W-$ 不变的。
:::

读者可能有疑问为什么 Tits 锥是位于对偶空间中的。一个看起来更自然的想法是，直接把 $V$ 中所有以 $\Delta$ 为法向量的正半空间之交
$$\bigcap_{s\in S}\{v\in V\mid(\alpha_s, v)>0\}$$
作为基本区域 $\fd$。在内积 $\inn$ 非退化时，这样做是可以的；但是在 $\inn$ 退化的情形，可能会出现 $\fd$ 是空集的问题。以 Coxeter 矩阵
$$\begin{pmatrix}1 & \infty\\\infty&1\end{pmatrix}$$
为例，在 $a_{s,t}=1$ 时它给出的内积的 Gram 矩阵是
$$\begin{pmatrix}(\alpha_s,\alpha_s) & (\alpha_s,\alpha_t)\\(\alpha_t,\alpha_t)& (\alpha_t,\alpha_t)\end{pmatrix} =\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.$$
假设 $v=a\alpha_s+b\alpha_t\in\fd$ 满足 $(v,\alpha_s)>0$ 且 $(v,\alpha_t)>0$，你会发现这要求 $a>b$ 且 $b>a$，不存在这样的 $v$！但是通过区分 $V$ 和 $V^\ast$ 上的作用就可以避免这个问题。因为 $\Delta$ 是一组线性无关的泛函，它们在对偶空间中正半空间的交一定是个非空的拓扑开集。

读者可能注意到了：我们使用了 Tits 锥这个称呼，但 $\tc$ 真的是一个锥吗？这可不显然。要证明 Tits 锥确实是锥，我们需要它的另一种等价刻画。

我们先回顾一下锥的概念：

::: definition
设 $C$ 是某实向量空间的子集。如果对任何 $x\in C$ 和实数 $\alpha\geq0$ 都有 $\alpha x\in C$，就称 $C$ 是一个**锥**。如果 $C$ 还是凸集，就称 $C$ 是**凸锥**。凸锥满足对任何 $x,y\in C$ 和非负实数 $\alpha,\beta\geq0$，$\alpha x + \beta y$ 仍然属于 $C$。
:::

::: definition
设 $\Delta^\ast=\{\omega_t\}\subset V^\ast$ 是 $\Delta$ 的一组对偶基，满足 $\lfun{\alpha_s}{\omega_t}=\delta_{st}$，$\Delta^\ast$ 叫做**基本权**。记
$$\Omega=\bigcup_{w\in W}w\Delta^\ast.$$
$\Omega$ 中的元素叫做**权**。
:::

设 $X=\{x_1,\ldots,x_n\}$ 是一个有限集，我们用记号 $\cone{X}$ 表示 $X$ 中元素的所有非负线性组合：
$$\cone{X} = \left\{\sum_{i=1}^n c_ix_i,\, c_i\geq0\right\}.$$

::: {.proposition #fund-cone}
$\barfd=\cone{\Delta^\ast}$。
:::

证明：对 $x\in V^\ast$，设 $x=\sum_{t\in S}c_t\omega_t$，注意到对任何 $s\in S$ 有 $\lfun{\alpha_s}{x} = c_s$，所以
$$x\in\cone{\Delta^\ast}\Leftrightarrow c_s\geq0 \text{ for all } s \in S  \Leftrightarrow \lfun{\alpha_s}{x}\geq 0 \text{ for all } s\in S \Leftrightarrow x\in\barfd.
$$
$\blacksquare$

对任一 $x\in V^\ast$，定义
$$\negf{x}= \{\lambda\in \Phi^+\mid \lfun{\lambda}{x}<0\}.$$
$\negf{x}$ 是正根 $\Phi^+$ 的子集，表示 $x$ 位于哪些镜子的背面。

一个显然的事实是，$\barfd$ 位于所有镜子的正面，即 $\overline{\mathcal{D}}=\{x\in V^\ast\mid \mathrm{Neg}(x)=\emptyset\}$。

我们来证明：

:::{.theorem #tits-neg-finite}
Tits 锥 $\tc = \{x\in V^\ast \mid |\mathrm{Neg}(x)| < \infty\}$。
:::

::: note
这个定理的几何意义是，每个镜子的正面是包含 $\fd$ 的一侧，另一侧是背面，Tits 锥就是那些只落在有限多个镜子背面的点，它们一定经过有限次单反射后变换到 $\barfd$ 中。换言之，Tits 锥中的点使得下面的 `while` 循环可以在有限次后结束：

```python
while dot(x, alpha_s) < 0 for some s in S:
    x = reflect(x, alpha_s)
```

下面的动画展示了 $\Gamma=\Delta(3,3,7)$ 对应的双曲 Coxeter 群的 Tits 锥中反射次数不超过 10 的点：

![](images/337-anim.gif){width=400}
:::

**证明**：

$\Rightarrow$: 设 $x\in\tc$，则 $x$ 可以表示为 $x=wv$，其中 $w\in W,v\in\barfd$。设 $\lambda\in\Phi^+$，由恒等式
$$\lfun{\lambda}{x}=\lfun{\lambda}{wv}=\lfun{w^{-1}\lambda}{v}$$
有 $\lfun{\lambda}{x}< 0\Rightarrow \lfun{w^{-1}\lambda}{v}<0\Rightarrow w^{-1}\lambda\in\Phi^-$，即 $\negf{x}\subseteq N(w^{-1})$，从而
$$|\negf{x}|\leq |N(w^{-1})|=l(w^{-1})=l(w)<\infty.$$

$\Leftarrow$: 反之若 $|\negf{x}|<\infty$，我们来论证可以选择 $w\in W,v\in\barfd$ 来使得 $x=wv$。这里的想法是，我们每次选择一个单根 $\alpha_s$ 对应的镜面，使得 $x$ 落在这个镜子的背面，然后将 $x$ 关于 $\alpha_s$ 反射过去变到 $\alpha_s$ 的正面，这个操作会将遮挡在 $x$ 和 $\barfd$ 之间的镜子个数严格减少 1。如此这般直到 $x$ 落入 $\barfd$ 为止。

严格的论证如下：

若 $\negf{x}=\emptyset$ 这显然成立，因为这时 $x$ 本身就落在 $\barfd$ 中。当 $\negf{x}\ne\emptyset$ 时，其中一定包含一个单根 $\alpha_s\in\Delta$，于是 $\lfun{\alpha_s}{x}< 0$。考虑 $x$ 关于 $\alpha_s$ 的镜像点 $sx$，我们来分析集合 $\negf{sx}$，即那些遮挡 $sx$ 的镜子。我们断言 $\negf{sx} = s\cdot(\negf{x}-\{\alpha_s\})$，即 $\negf{sx}$ 元素个数比 $\negf{x}$ 严格减少 1。

首先 $sx$ 位于 $\alpha_s$ 的正面，所以 $\alpha_s\notin\negf{sx}$。设 $\lambda\ne\alpha_s$ 是任一正根，则 $s\lambda$ 也是正根。于是
$$\lambda\in\negf{sx}\Leftrightarrow\lfun{sx}{\lambda}<0\Leftrightarrow\lfun{x}{s\lambda}<0\Leftrightarrow s\lambda\in\negf{x}.$$
即 $\lambda\leftrightarrow s\lambda$ 是 $\negf{sx}$ 和 $\negf{x}-\{\alpha_s\}$ 的一一对应，从而 $\negf{sx} = s\cdot(\negf{x}-\{\alpha_s\})$。重复此过程我们最终可以取一组 $s_{i_1},\ldots,s_{i_k}$ 使得 $y=s_{i_1}\cdots s_{i_k}x$ 满足 $\negf{y}=\emptyset$，从而 $y\in\barfd$，这就证明了结论。

:::{.corollary #tits-convex}
Tits 锥 $\tc$ 是凸锥。
:::

**证明**：设 $x, y\in\tc$ 和 $\alpha,\beta\geq0$，我们需要证明 $z=\alpha x+\beta y$ 也属于 $\tc$。但是
$$\negf{z}\subseteq\negf{x}\cup\negf{y},$$
根据 @Pre:tits-neg-finite $\negf{x},\,\negf{y}$ 都是有限集，所以 $\negf{z}$ 也有限，从而 $z\in\tc$，即 $\tc$ 是凸锥。

::: {.corollary}
$\tc=\cone{\Omega}$。
:::

**证明**：由于 $\cone{\Omega}\supset\cone{\Delta^\ast}=\barfd$，以及 $\cone{\Omega}$ 是 $W-$ 不变的，所以它包含 $\bigcup_{w\in W}w\barfd=\tc$。

另一方面根据 @Pre:fund-cone，$\tc\supset\barfd\supset\Delta^\ast$，以及 $\tc$ 是 $W-$ 不变的，所以 $\tc\supset\bigcup_{w\in W}w\Delta^\ast=\Omega$。而 @Pre:tits-convex 证明了 $\tc$ 是凸锥，所以 $\tc\supset\cone{\Omega}$。$\blacksquare$

接下来我们来讨论 $\tc$ 的内点集 $\tc^\circ$。我们将证明 $\tc^\circ$ 由那些稳定化子群有限的点组成：
$$\tc^\circ = \{x\in V^\ast \mid |\stab{x}| < \infty\}.$$

分两步，我们首先来证明标准椭圆子群 $W_J$ 对应的是 $J$ 中镜面交点的稳定化子群：

:::{.theorem #stabilizer-parabolic-subgroup}
对任何 $x\in\barfd$，记 $J=\{s\in S \mid \lfun{\alpha_s}{x}=0\}$，则
$$\{w\in W\mid wx=x\} = W_J = \{w\in W\mid wx\in\barfd\}.$$
:::

::: note
这个定理的含义是，对 $\barfd$ 中的一点 $x$，其稳定化子群 $\stab{x}$ 是一个标准椭圆子群，由那些包含 $x$ 的墙面 $\{\alpha_s\in\Delta \mid \lfun{\alpha_s}{x}=0\}$ 对应的反射生成。
:::

**证明**：

对任何 $s\in J$ 和 $v\in V$ 我们有
$$\lfun{v}{sx} = \lfun{sv}{x}=\lfun{v-2(v,\alpha_s)\alpha_s}{x}=\lfun{v}{x},$$
由 $v$ 的任意性可得 $sx=x$，从而 $W_J\subseteq\{w\in W \mid wx=x\}$。

另一方面显然有
$$\{w\in W\mid wx=x\}\subseteq \{w\in W\mid wx\in\barfd\},$$
所以只要再证明 $\{w\in W\mid wv\in\barfd\}\subseteq W_J$ 即可。我们从 $w$ 最末一个元素开始逐个验证它们属于 $J$。

设 $w\ne1$ 的某个既约表示的结尾是 $s$，则 $l(ws)<l(w)$，于是 $w\alpha_s\in\Phi^-$。如果 $wx\in\barfd$，则我们有
$$0\geq \lfun{w\alpha_s}{wx} = \lfun{\alpha_s}{x}\geq0.$$
其中第一个不等号是因为 $w\alpha_s$ 是负根和 $wx\in\barfd$。所以 $\lfun{\alpha_s}{x}=0$，即 $s\in J$，从而 $sx=x$，于是 $wx=w'sx=w'x\in\barfd$，从而我们可以对 $l(w')<l(w)$ 重复此论证，得到 $w$ 的乘积中所有因子都属于 $J$，从而定理得证。$\blacksquare$

:::{.theorem #tits-int-finite-stabilizer}
$x\in\tc^\circ$ 当且仅当 $x$ 在 $W$ 中的稳定化子群是有限群。
:::

**证明**：由于任何 $y\in\tc$ 可以写成 $y=wx$ 的形式，其中 $w\in W,\,x\in\barfd$，所以 $x$ 和 $y$ 的稳定化子群是共轭的：${\rm Stab}(y)=w{\rm Stab}(x)w^{-1}$，二者同为有限群或者无限群；而且 $x,y$ 同时属于或者同时不属于 $\tc^\circ$。所以我们只要论证 $x\in\barfd$ 的情形即可。

而根据 @Pre:stabilizer-parabolic-subgroup，$\stab{x}=W_J$，其中 $J=\{s\in S\mid\lfun{\alpha_s}{x}=0\}$，所以只要证明如下命题即可：

::: {.proposition #fd-finite-stabilizer .unnumbered}
设 $x\in\barfd$，则 $x\in\tc^\circ$ 当且仅当 $W_J$ 是有限群。
:::

命题的证明：

$\Rightarrow$：我们的思路是，如果 $x$ 是 $\tc$ 的内点，并且经过 $x$ 的镜面有无穷多个，那么可以在 $x$ 的附近取一点 $z$，$z$ 仍然是 $\tc$ 的内点，使得这无穷多个镜子都挡在基本区域和 $z$ 之间，从而 $\negf{z}$ 是无限集，从而 $z\notin\tc$，导致矛盾。

任取 $y\in\fd$。由于 $x\in\tc^\circ$，所以在线段 $\overline{[y, x]}$ 上我们可以朝着 $x$ 的方向延伸一点点，得到点 $z$，使得 $z$ 仍然位于 $\tc^\circ$ 中。$z$ 可以表示为
$$z=(1-t)x+ty\qquad t<0,$$
于是对所有 $s\in J$ 都有 $\lfun{\alpha_s}{z}=t\lfun{\alpha_s}{y} < 0$ 成立。如果 $W_J$ 是无限群那么标准椭圆子群 $W_J$ 的根系 $\Phi_J=W_J\cdot\{\alpha_s\mid s\in J\}$ 也是无限的，从而 $\negf{z}\supseteq \Phi^+_J$ 是无限集，从而 $z\notin\tc^\circ$，矛盾！

$\Leftarrow$：反之若 $W_J$ 是有限群，仍然任取 $y\in\fd$。

对任何镜面 $s\in S\backslash J$，由于 $x$ 不属于此镜面，所以 $\lfun{\alpha_s}{x}>0$。另一方面对任何 $w\in W_J$，根据 @Pre:remain-positive-root $w^{-1}\alpha_s$ 仍然是正根，所以也有 $\lfun{\alpha_s}{wy}=\lfun{w^{-1}\alpha_s}{y}>0$ 成立，于是
$$\delta = \min\left\{\frac{\lfun{\alpha_s}{x}}{\lfun{\alpha_s}{wy}}\,\middle|\, \alpha_s\in S\backslash J,\, w\in W_J\right\}>0$$
是一个正数，将上面的分母乘到左边然后对 $w\in W_J$ 求和，我们有
$$\delta\cdot\lfun{\alpha_s}{\sum_{w\in W_J}wy}\leq \lfun{\alpha_s}{x}\cdot |W_J| < 2\lfun{\alpha_s}{x}\cdot |W_J|.$$

注意到上面这个不等式两边关于 $\alpha_s$ 都是线性的。

对任何 $\lambda\in\Phi^+\backslash\Phi_J^+$，$\lambda$ 可以表示为一些 $\{\alpha_s,\,s\in S\backslash J\}$ 和一些 $\{\alpha_t,\,t\in J\}$ 的非负线性组合。我们已经看到对 $s\in S\backslash J$ 上面的不等式成立，而对任何 $t\in J$，由于 $\sum_{w\in W_J}wy$ 在 $W_J$ 下保持不变，所以根据 @Pre:stabilizer-parabolic-subgroup 可得 $\lfun{\alpha_{t}}{\sum_{w\in W_J}wy}=0$，从而上面的不等式变成了等式（两边都是 0）。把这些 $s\in S\backslash J$ 中的严格不等式和 $t\in J$ 中的等式相加，我们得到将 $\lambda$ 代入 $\alpha_s$ 的位置上述严格不等式仍然成立。

于是对任何 $\lambda\in\Phi^+\backslash\Phi_J^+$ 有
$$\delta\cdot\lfun{\lambda}{\sum_{w\in W_J}wy}< 2\lfun{\lambda}{x}\cdot |W_J|.$$
根据 @Pre:remain-positive-root 上面每一个 $\lfun{\lambda}{wy}$ 都是大于 0 的，我们可以只取 $w=1$ 的一项，其余全扔掉，得到
$$\delta\cdot\lfun{\lambda}{y}< 2\lfun{\lambda}{x}\cdot |W_J|.$$
记 $z = 2|W_J|x - \delta y$，我们得到 $\lfun{\lambda}{z}>0$ 对任何 $\lambda\in\Phi^+\backslash\Phi_J^+$ 成立。

另一方面对任何 $\mu\in\Phi_J^+$，由于 $\lfun{\mu}{x}=0$，所以 $\lfun{\mu}{z}=-\delta\lfun{\mu}{y}<0$，于是 $\negf{z}=\Phi_J^+$ 是有限集，从而 $z\in\tc$。

实际上我们有 $z\in\tc^\circ$，这是因为对任何 $\lambda\in\Phi$，$\lambda$ 必然属于 $\pm\Phi^+_J,\pm(\Phi^+\backslash\Phi^+_J)$ 之一，$\lfun{\lambda}{z}$ 总不是 0，所以 $z$ 不落在任何镜面上。设 $z=wv,\,v\in\barfd$，那么
$$\lfun{\alpha_s}{v}=\lfun{w\alpha_s}{wv}=\lfun{w\alpha_s}{z}\ne0$$
对任何 $\alpha_s\in\Delta$ 成立，所以 $v\in\fd\subset\tc^\circ$，从而 $z=wv\in w\fd\subset\tc^\circ$。

现在 $x$ 是 $z$ 和 $y$ 的线性组合 $x = \frac{1}{2|W_J|}(z + \delta y)$。我们来说明 $x$ 也属于 $\tc^\circ$。由于 $z,y\in\tc^\circ$，所以 $\frac{1}{2|W_J|}z, \frac{\delta}{2|W_J|}y\in\tc^\circ$，即存在开集 $A,B$ 满足 $\frac{1}{2|W_J|}z\in A\subset\tc^\circ$，$\frac{\delta}{2|W_J|}y\in B\subset \tc^\circ$，于是 $x\in A+B=\cup_{p\in B}(A+p)$，这是一组开集的并，所以 $x\in\tc^\circ$，命题得证，从而 @Pre:tits-int-finite-stabilizer 得证。$\blacksquare$

:::note
在上面最后一段中，我们实际上证明了一个凸锥的内部仍然是凸锥。
:::