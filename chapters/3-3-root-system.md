## 根系

::: Definition
我们称集合
$$\Phi=\{w\alpha_s\mid w\in W, \, s\in S\}$$
为 $(W, S)$ 的**根系**，任何 $\lambda\in\Phi$ 叫做根向量，简称为**根**。$\Delta=\{\alpha_s\mid s\in S\}$ 叫做**单根系**，其中的根叫做**单根**。由于 $\Delta$ 构成 $V$ 的一组基，所以 $\Phi$ 中任何根 $\lambda$ 都是单根的线性组合：
$$\lambda = \sum_{s\in S}c_s\alpha_s,\quad c_s\in\mathbb{R}.$$
如果上面的所有系数 $c_s$ 都非负，就称 $\lambda$ 是一个**正根**；若所有系数 $c_s$ 都非正，就称 $\lambda$ 是一个**负根**。正根和负根组成的集合分别记作 $\Phi^+$ 和 $\Phi^-$，显然 $\Phi^+\cap\Phi^-=\emptyset$。
:::

这里有个问题：每个根都必然是正根或者负根吗？即是否有 $\Phi=\Phi^+\cup\Phi^-$ 成立？这并不显然，但其实答案是肯定的，为此我们需要一个关键引理。这个引理的证明有点长，但是它非常非常重要，Coxeter 群的几乎所有性质的证明多少都会用到它。在引入它之前，我们需要做一点小小的准备。

设 $I\subseteq S$ 是 $S$ 的子集，$I$ 中的生成元在 $(W,S)$ 中生成一个子群 $W_I \leqslant (W,S)$，$W_I$ 叫做**标准椭圆子群**。记 $l_I(\cdot)$ 是 $W_I$ 上的长度函数，则显然对任何 $w\in W_I$ 有 $l(w)\leq l_I(w)$ 成立（因为 $W_I$ 中的任何既约表示是 $W$ 中的未必既约的表示）。我们后面会看到 $l_I=l\mid_{W_I}$，但现在我们暂时还证明不了它。

现在我们给出本文最重要的一个引理，不夸张地说，几乎所有 Coxeter 群性质的证明中多少都要用到它。

::: {.lemma #key-lemma}
设 $s\in S,\, w\in W$，则

1. $l(ws) > l(w)$ 当且仅当 $w\alpha_s\in\Phi^+$。
2. $l(ws) < l(w)$ 当且仅当 $w\alpha_s\in\Phi^-$。
:::

这里 1 和 2 是等价的：如果 1 成立，则

$$
\begin{align*}
l(ws)<l(w)&\Leftrightarrow l((ws)s) > l(ws)\\
&\Leftrightarrow ws(\alpha_s)\in\Phi^+\\
&\Leftrightarrow w(-\alpha_s)\in\Phi^+\\
&\Leftrightarrow w\alpha_s\in\Phi^-.
\end{align*}
$$

所以只需要证明 1 即可。

我们先证明充分性：若 $l(ws)>l(w)$ 则 $w\alpha_s\in\Phi^+$。

对 $l(w)$ 归纳：$l(w)=0$ 时 $w=1$，结论显然成立。下面设结论对所有长度小于 $l(w)$ 的元素成立。

我们总是可以取 $t\ne s$ 使得 $l(wt)<l(w)$，比如 $t$ 取为 $w$ 的某个既约表达式的最后一项。令 $I=\{s,t\}$，定义
$$A = \{(x,x_I)\in W\times W_I\mid w=xx_I,\,l(w)=l(x)+l_I(x_I)\}.$$
由于 $(wt,t)\in A$ 所以 $A$ 不是空集。取 $(v,v_I)\in A$ 使得 $l(v)$ 取得最小值，则 $l(v)\leq l(wt)=l(w)-1$。我们断言对任何 $u\in I$ 都有 $l(vu)>l(v)$。若不然，则 $l(vu)=l(v)-1$，于是
$$\begin{align*}
l(w)&=l(vu\cdot uv_I)\leq l(vu) + l(uv_I) = (l(v) -1) + l(uv_I)\\
&\leq (l(v) -1) + l_I(uv_I)\\
&\leq (l(v) -1) + (l_I(v_I) + 1)\\
& = l(v) + l_I(v_I)=l(w).
\end{align*}$$
于是所有的不等号都是等式，从而 $(vu,uv_I)\in A$，但这与 $(v,v_I)$ 的选择矛盾。所以不论 $u=s$ 或是 $u=t$ 都有 $l(vu)>l(v)$。

由于 $l(v)\leq l(w)-1$ 所以根据归纳假设 $v\alpha_s,\,v\alpha_t$ 都是正根。如果我们能够证明 $v_I\alpha_s$ 是 $\alpha_s$ 和 $\alpha_t$ 的非负线性组合：$$v_I\alpha_s = a\alpha_s + b\alpha_t,\quad a,\,b\geq0,$$
则
$$w\alpha_s=vv_I\alpha_s=v(a\alpha_s + b\alpha_t)=av\alpha_s + bv\alpha_t\in\Phi^+.$$
这就证明了结论。

首先注意到 $v_I\in W_I$ 的任何既约表示都是 $s,t$ 的交错乘积，而且不能以 $s$ 结尾，否则 $l_I(v_Is)=l_I(v_I)-1$，从而
$$l(ws)=l(vv_Is)\leq l(v) + l(v_Is)\leq l(v)+l_I(v_Is)=l(v)+l_I(v_I)-1=l(w)-1.$$
这与 $l(ws) > l(w)$ 矛盾！

于是 $v_I$ 形如 $v_I=st\cdots t$ 或者 $v_I=ts\cdots t$，问题归结为分析这样的 $v_I$ 在 $\alpha_s$ 上的作用。这个我们已经在 [前面计算过了](#rank2-roots)，直接拿过来分析就行：

1. $m=m_{s,t}<\infty$ 时，$$\alpha_s\xrightarrow{\ t\ }\sthe{}\alpha_s+\sthe{2}\alpha_t\xrightarrow{\ s\ }\sthe{3}\alpha_s+\sthe{2}\alpha_t\xrightarrow{\ t\ }\cdots$$
其中 $\theta=\pi/m$。这个链的第 $k$ 项形如
$$
\begin{cases}
\sthe{k}\alpha_s + \sthe{(k-1)}\alpha_t, & \text{$k$ odd},\\
\newline
\sthe{(k-1)}\alpha_s + \sthe{k}\alpha_t, & \text{$k$ even}.
\end{cases}
$$
看起来并不是每一项都是 $\alpha_s,\alpha_t$ 的非负线性组合，但是前 $m$ 项都是，这就足够了：由于 $v_I$ 的任何既约表示不能以 $s$ 结尾，所以 $v_I$ 可能的取值是二面体群 $D_m$ 中所有长度小于 $m$ 且以 $t$ 结尾的那些元素：
$$1,\ t,\ st,\ \ldots,\ \overbrace{\ast\cdots\ast t}^{\leq m-1},$$
它们正好构成序列的前 $m$ 项。$v_I$ 的长度不能等于 $m$ 是因为根据辫关系
$$\overbrace{sts\cdots}^{m_{s,t}}=\overbrace{tst\cdots}^{m_{s,t}}$$
$v_I$ 会等于以 $s$ 结尾的另一个既约表示，与 $v_I$ 的任何既约表示不能以 $s$ 结尾矛盾。

2. $m=m_{s,t}=\infty$ 时，仍然记 $\cosh\theta=a_{s,t},\,\theta\geq0$，则
$$\alpha_s\xrightarrow{\ t\ }\shthe{}\alpha_s+\shthe{2}\alpha_t\xrightarrow{\ s\ }\shthe{3}\alpha_s+\shthe{2}\alpha_t\xrightarrow{\ t\ }\cdots$$
每一项都是 $\alpha_s,\alpha_t$ 的非负线性组合。

必要性的证明：

我们要证明若 $w\alpha_s\in\Phi^+$ 则 $l(ws)>l(w)$。若不然，则 $l(w)=l(wss)>l(ws)$，从而由充分性的证明知道 $ws\alpha_s\in\Phi^+$，即 $w\alpha_s\in\Phi^-$，矛盾！至此关键引理得证。$\blacksquare$

从 @Pre:key-lemma 出发我们可以得到许多重要推论：

:::corollary
如果 $w\in W$ 满足对任何 $v\in V$ 有 $wv=v$ 则 $w=1$。即表示 $\rho: W\to{\rm GL}(V)$ 是忠实的。
:::

**证明**：若 $w\ne 1$，则存在 $s\in S$ 使得 $l(ws)<l(w)$，从而 $w\alpha_s\in\Phi^-$，这与 $w\alpha_s=\alpha_s$ 矛盾。

::: {.corollary #pos-neg}
每个根不是正根就是负根，即 $\Phi=\Phi^+\cup\Phi^-$。
:::

**证明**：由定义任何 $\lambda\in\Phi$ 可以表示为 $\lambda=w\alpha_s$。若 $l(ws)>l(w)$ 则 $\lambda\in\Phi^+$，否则 $\lambda\in\Phi^-$。

:::{.corollary #simple-ref}
任何单反射 $s$ 置换 $\Phi^+-\{\alpha_s\}$ 中的正根，同时将 $\alpha_s$ 变为 $-\alpha_s$。
:::

**证明**：这是因为对任何正根 $\lambda\ne\alpha_s\in\Phi^+$，其作为单根的线性组合 $\lambda=\sum_{t\in S}c_t\alpha_t$ 中必有某个 $t\ne s$ 使得 $c_t>0$，于是 $s\lambda=\lambda-2(\lambda,\alpha_s)\alpha_s$ 的 $\alpha_t$ 分量保持不变仍然为正，从而根据 @Pre:pos-neg $s\lambda$ 必须仍然是正根。

:::{.corollary #lw-nw}
对 $w\in W$，定义 $N(w)$ 为被 $w$ 变成负根的那些正根组成的集合：
$$N(w)=\{\lambda\in\Phi^+\mid w\lambda\in\Phi^-\},$$
则 $|N(w)|=l(w)$。
:::

**证明**：我们已经知道 $l(w)$ 满足如下的递推关系：

$$
l(ws) =\begin{cases}
l(w)+1,& w\alpha_s\in\Phi^+,\\
l(w)-1,& w\alpha_s\in\Phi^-.
\end{cases}
$$

以及 $l(1)=0$。由于 $N(1)=\emptyset$，所以只需要证明 $|N(w)|$ 也满足同样的递推关系即可：

$$
|N(ws)| =\begin{cases}|N(w)|+1,& w\alpha_s\in\Phi^+,\\
|N(w)|-1,& w\alpha_s\in\Phi^-.\end{cases}
$$

实际上对任何 $\lambda\in\Phi^+$ 且 $\lambda\ne\alpha_s$，根据 @Pre:simple-ref $s\lambda$ 也是正根，所以由恒等式
$$(ws)\lambda\in\Phi^- \Leftrightarrow w(s\lambda)\in\Phi^-.$$
可得当 $\lambda\in\Phi^+-\{\alpha_s\}$ 时有
$$\lambda\in N(ws)\Leftrightarrow s\lambda\in N(w),$$
即 $\lambda\leftrightarrow s\lambda$ 给出了 $N(ws)-\{\alpha_s\}$ 和 $N(w)-\{\alpha_s\}$ 的一一对应。除此之外，$\alpha_s$ 必然恰好属于 $N(ws)$ 和 $N(w)$ 之一：

+ 当 $l(ws) > l(w)$ 时 $w\alpha_s\in\Phi^+\Rightarrow ws\alpha_s\in\Phi^-\Rightarrow\alpha_s\in N(ws)$，这对应第一条递推关系；
+ 当 $l(ws)<l(w)$ 时 $w\alpha_s\in\Phi^-\Rightarrow\alpha_s\in N(w)$，这对应第二条递推关系。

$\blacksquare$

:::{.corollary #nw-zero-means-identity}
若 $w\in W$ 把正根仍然映射为正根，即 $w(\Phi^+)\subseteq\Phi^+$，则 $w=1$。
:::

**证明**：若 $w$ 将正根仍然映射为正根，则根据 @Pre:lw-nw 有 $l(w)=|N(w)|=0$，从而 $w=1$。

:::{.corollary #w-phi-both-finite-infinite}
$|W|<\infty$ 当且仅当 $|\Phi|<\infty$。
:::

**证明**：如果 $W$ 是有限群，由于 $\Phi=W\cdot \Delta$，$|\Phi|\leq |W|\cdot |\Delta|$ 也是有限的。

反之若 $|\Phi|<\infty$，由于 $W$ 保持 $\Phi$ 不变，所以 $W$ 置换地作用在 $\Phi$ 上，即有 $W$ 到置换群 $S_{|\Phi|}$ 的同态 $W\xrightarrow{\varphi} S_{|\Phi|}$。@Pre:nw-zero-means-identity 说明 $\varphi$ 是嵌入，从而 $W$ 也是有限的。

:::{.corollary #longest}
若 $W$ 是一个有限群，则存在唯一的元素 $w$，$w$ 是 $W$ 中长度最大者，它交换 $\Phi^+$ 和 $\Phi^-$：$w(\Phi^+)=\Phi^-$，且 $w$ 是一个对合：$w^2=1$。
:::

**证明**：由于 $W$ 有限所以可以任取一个长度最大的元素 $w$。于是对任何 $s\in S$ 有 $l(ws)<l(w)$，从而 $w\alpha_s\in\Phi^-$，从而 $w$ 把 $\Phi^+$ 变为 $\Phi^-$。

由于 $w^2$ 仍然把 $\Phi^+$ 映射为 $\Phi^+$，所以由 @Pre:nw-zero-means-identity $w^2=1$，因此 $w$ 是一个对合。

如果还存在其它的最长元素 $w'\ne w$ 的话，则 $w'$ 也满足 $w'(\Phi^+)=\Phi^-$，从而 $w^{-1}w'$ 保持 $\Phi^+$ 不变，根据 @Pre:nw-zero-means-identity 有 $w^{-1}w'=1$，即 $w=w'$。

:::{.corollary #remain-positive-root}
设 $I\subsetneqq S$ 是真子集，$\lambda\in \Phi^+\backslash \Phi^+_I$ 是正根，则对任何 $w\in W_I$，$w\lambda$ 仍然是正根。
:::

**证明**：注意到对任何根 $\lambda\in\Phi$ 和 $s\in S$，$s\lambda=\lambda-2(\alpha_s,\lambda)\alpha_s$ 是 $\lambda$ 和 $\alpha_s$ 的线性组合。同理 $ts\lambda$ 是 $s\lambda$ 和 $\alpha_t$ 的线性组合，从而是 $\lambda,\alpha_s,\alpha_t$ 的线性组合。由此可以推广到对任何 $w=s_1s_2\cdots s_k$，$w\lambda$ 是 $\lambda$ 和 $\{\alpha_1,\ldots,\alpha_k\}$ 的线性组合：
$$w\lambda=\lambda + \sum_{t\in I}c_t\alpha_t.$$
由于 $\lambda\in \Phi^+\backslash \Phi^+_I$，所以 $\lambda$ 表示为单根的线性组合时，其至少有一项 $\alpha_s,\,s\notin I$ 的系数大于 0，从而 $w\lambda$ 关于这一项的系数也大于 0，所以 $w\lambda$ 不可能是负根。$\blacksquare$

::: {.corollary #wv-minus-v}
设 $w=s_{\alpha_1}s_{\alpha_2}\cdots s_{\alpha_n}$，则对任何 $v\in V$ 有
$$wv = v - \sum_{i=1}^n2(v,\alpha_i)\beta_i.$$
其中 $\beta_i=s_{\alpha_1}\cdots s_{\alpha_{i-1}}(\alpha_i)$ 是正根。（$i=1$ 时 $\beta_1$ 理解为 $\alpha_1$）
:::

**证明**：对 $n$ 归纳，$n=1$ 时 $w=s_{\alpha_1}$，$\beta_1=\alpha_1$，所以
$$wv=s_{\alpha_1}v=v-2(v,\alpha_1)\alpha_1=v-2(v,\alpha_1)\beta_1.$$
结论成立。下设结论在小于 $n$ 时都成立。对 $w'=s_{\alpha_2}\cdots s_{\alpha_n}$ 应用归纳假设，有
$$w'v=v - \sum_{i=2}^n2(v,\alpha_i)\beta_i'.$$
其中 $\beta_i'=s_{\alpha_2}\cdots s_{\alpha_{i-1}}(\alpha_i)$，并且由归纳假设 $\beta_i'$ 是正根。
于是
$$wv=s_{\alpha_1}w'v=s_{\alpha_1}v-\sum_{i=2}^n2(v,\alpha_i)s_{\alpha_1}(\beta_i')=\sum_{i=1}^n2(v,\alpha_i)\beta_i.$$
注意到每个 $\beta_i'$ 是 $\{\alpha_i,2\leq i\leq i\}$ 的线性组合，它是正根说明 $\beta_i'\ne\alpha_1$，从而 $s_{\alpha_1}(\beta_i')=\beta_i$ 仍然是正根。于是结论对 $n$ 也成立。$\blacksquare$

::: {.corollary #lI-equals-l}
设 $w\in W_I$，则对 $w$ 的任何既约表示 $w=s_{i_1}\cdots s_{i_r}$ 都有 $s_{i_1},\ldots,s_{i_r}\in I$，特别地 $l_I(w)=l(w)$。
:::

**证明**：我们从右到左依次验证 $s_{i_r},\ldots,s_{i_1}\in I$。记 $s=s_{i_r}$，由于 $l(ws)<l(w)$ 所以 $w\alpha_s\in\Phi^-$。又由于 $w\in W_I$ 所以 $w$ 形如 $w=t_1\cdots t_q,\,t_i\in I$。于是 $w\alpha_s$ 是 $\alpha_s$ 和一些 $\alpha_{t_i}$ 的线性组合：
$$w\alpha_s=\alpha_s+\sum_{i=1}^q c_i\alpha_{t_i}.$$
由于 $w\alpha_s<0$ 所以必然有某个 $i$ 使得 $s=t_i$，即 $s\in I$。继续对 $ws=s_{i_1}\cdots s_{i_{r-1}}\in W_I$ 重复此论证即得每个 $s_{i_j}\in I$。