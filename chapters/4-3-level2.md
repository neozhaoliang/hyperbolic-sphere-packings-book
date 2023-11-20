## Level 2 也是双曲的

本节我们在上一小节的结论中再进一步，证明 level 2 的群也是双曲的。论证会更加繁琐一些。

::: {.theorem #level-2}
level 等于 2 的群都是双曲的，所有的基本权两两分离。$\omega_s\in\Delta^\ast$ 是实的当且仅当 $\minus{T}{s}$ 的 level 等于 1，且对这样的 $\omega_s$ 有 $0<(\omega_s,\omega_s)\leq 1$。
:::

**证明**：我们先来证明 $\Gamma$ 是双曲的。

如果 $\Gamma$ 是不连通的，则 $\Gamma$ 必须是一个 level 为 1 的子图和一个独立顶点的并，由于 @Pre:thm-level-1 已经证明了 level 1 的群是双曲的，再加上一个独立顶点仍然是双曲的，所以 $\Gamma$ 是双曲的。于是我们不妨假设 $\Gamma$ 是连通的。

再针对 $\Gamma$ 的顶点个数是否大于 3 分别处理。在 $\Gamma$ 只包含 3 个顶点的情形，$\Gamma$ 的 level 是 2 说明其必然有一条边的 Vinberg 标号小于 -1。不妨设 $\inn$ 的 Gram 矩阵形如
$$\begin{pmatrix}1&a&b\\a&1&c\\b&c&1\end{pmatrix}.$$
其中 $a,\,b,\,c\leq0$ 且 $a < -1$。这个矩阵的行列式是
$$1 - a^2 + 2abc - b^2-c^2 = 1-a^2 + 2bc(a+1)-(b+c)^2<0.$$
由于矩阵的迹等于 3，所以其符号必然是 $(2, 1)$，从而是双曲的。

再处理 $\Gamma$ 包含至少 4 个顶点的情形。

仍然根据 @Pre:lemma-uv，如果 $\Gamma$ 不是双曲的，则我们可以取两个非零且正交的向量 $u,v$ 满足 $(u, u)<0,\,(v, v)=0$。

我们也有如下两个断言：

1. 任何满足 $(u,u)<0$ 的向量 $u=\sum_{s\in S}u_s\alpha_s$ 除去至多一个系数 $u_j$ 之外，其它的 $u_s$ 都非零且同号。
2. 任何满足 $(v,v)=0$ 的向量 $v=\sum_{s\in S}v_s\alpha_s$ 除了满足断言 1 的情形之外，还有一种情形是 $\{v_s\}$ 中有两个是 0，其余的非零且同号。

我们仍然把断言的证明放在后面，先承认它们是正确的并完成证明。

由于 $u$ 的系数 $\{u_s\}$ 中至多只有一个是 0，$v$ 的系数 $\{v_s\}$ 中至多只有两个是 0，而 $|\Gamma|\geq4$，所以存在下标 $i$ 使得 $u_i,\,v_i$ 均不为 0。于是 $u'=v_iu-u_iv$ 仍然满足 $u'$ 与 $v$ 正交和 $(u',u')<0$，但是它的下标 $i$ 的系数 $u'_i=0$，所以我们不妨一开始就取 $u$ 为 $u'$，于是 $u$ 有一个系数 $u_i=0$，其它系数都非 0 且同号，不妨假设这些非零系数都大于 0。

现在我们已经有了 $v_i\ne0$，由于 $\{v_s\}$ 中至多只有两个为 0，而 $|\Gamma|\geq4$，所以 $\{v_j,\,j\ne i\}$ 中至少还有一个非零。

+ 如果 $\{v_j,\,j\ne i\}$ 中仅有一个非零，则这时必有 $|\Gamma|=4$ 且 $v$ 形如 $v=v_i\alpha_i + v_j\alpha_j$。根据 @Pre:level-l ${\rm span}\{\alpha_i,\alpha_j\}$ 是有限/或者仿射的，但是由于此平面包含 $(v,v)=0$，所以是仿射的，从而 $(\alpha_i,\alpha_j)=-1$。我们可以不妨把 $v$ 取为 $v=\alpha_i+\alpha_j$。

    |   | $i$  |  $j$  |  $k$  | $m$ |
    |:---:|:---:|:---:|:---:|:---:|
    | $u$ | 0   |  $>0$ | $>0$ |$>0$ |
    | $v$ | $\ne0$ | $\ne0$ | 0 | 0 |

    $u_i=0$ 说明 $u$ 形如 $u=u_j\alpha_j+u_k\alpha_k+u_m\alpha_m$。
    由 $(u,v)=0$ 有
    $$(u, v)=(u_j\alpha_j+u_k\alpha_k+u_m\alpha_m, v)=(u_k\alpha_k+u_m\alpha_m, \alpha_i+\alpha_j)=0,$$
    由于 $\{\alpha_k,\alpha_m\}$ 和 $\{\alpha_i,\alpha_j\}$ 之间的内积都小于等于 0，而 $u_k,u_m$ 大于 0，这说明
    $$(\alpha_k,\alpha_i) = (\alpha_k,\alpha_j) =(\alpha_m, \alpha_i) =(\alpha_m,\alpha_j)=0.$$
    即顶点 $\{i, j\}$ 与 $\{k,m\}=\minus{\Gamma}{i,j}$ 是不连通的，与 $\Gamma$ 连通矛盾。

+ 如果 $\{v_j,\,j\ne i\}$ 至少有两个非零，则可以取下标 $j,k$ 使得 $v_j/u_j\ne0,\,v_k/u_k\ne0$。

    |   | $i$  |  $j$  |  $k$  | $\cdots$ |
    |:---:|:---:|:---:|:---:|:---:|
    | $u$ | 0   |  $>0$ | $>0$ |$>0$ |
    | $v$ | $<0$ | $\ne0$ | $\ne0$ | $\cdots$ |

    由于 $v_i\ne0$，通过选择 $v$ 或者 $-v$ 可以不妨设 $v_i<0$，并不妨设 $v_j/u_j\leq v_k/u_k$。记 $a=v_j/u_j$，则 $u'=au-v$ 满足 $(u',u')<0$，但是 $u'_i=-v_i>0$，$u'_j=0$，$u'_k\leq 0$，这与上面断言中 $u'$ 的系数除去至多一个例外，剩下的均非零且同号矛盾。

至此我们证明了当 $\Gamma$ 的 level 等于 2 时是双曲的。

我们接下来证明所有的基本权 $\{\omega_s\}$ 是两两分离的。

仍然利用恒等式

$$\begin{align*}
\omega_s &= (\omega_s,\omega_s)\alpha_s + \sum_{t\ne s} (\omega_s,\omega_t)\alpha_t,\\
1 &= (\omega_s,\omega_s) + \sum_{t\ne s} (\omega_s,\omega_t)\underbrace{(\alpha_t,\alpha_s)}_{\leq0}.\end{align*}$$

并分情况讨论：

+ 如果 $(\omega_s,\omega_s)\leq0$，则根据第二个等式，$\{(\omega_s,\omega_t)\}_{t\ne s}$ 中必然至少有一个严格小于 0，从而根据断言，在 $\{(\omega_s,\omega_t)\}_{t\ne s}$ 中至多有一个为正。但我们将证明这不可能。否则不妨设 $k\ne s$ 使得 $(\omega_s,\omega_k)>0$。在第一个等式两边用 $\alpha_k$ 内积得到
$$0=(\omega_s,\omega_s)(\alpha_s,\alpha_k) +\sum_{t\ne s,k} (\omega_s,\omega_t)(\alpha_t,\alpha_k) + (\omega_s,\omega_k).$$
上面的和项前两个都非负，最后一个大于 0，矛盾。所以所有的 $\{(\omega_s,\omega_t)\}_{t\ne s}$ 都非正。

+ 如果 $(\omega_s,\omega_s)>0$，则其正交补 $U=\omega_s^\bot={\rm span}\{\alpha_t,\,t\ne s\}$ 是双曲的，即 $\minus{\Gamma}{s}$ 的 level 是 1。考虑 $\alpha_s$ 在 $U$ 上的正交投影 $\alpha_s'=\alpha_s-\omega_s/(\omega_s,\omega_s)$。$\alpha_s'$ 满足对任何 $t\ne s$ 有 $(\alpha_s',\alpha_t)\leq0$，从而 $-\alpha_s'$ 属于 $\minus{\Gamma}{s}$ 的基本区域的闭包 $\barfd_s$，而 @Pre:thm-level-1 和 @Pre:level-1 已经证明了 $\minus{\Gamma}{s}$ 的 Tits 锥中的点都是 time-like 或者 light-like 的，从而 $(\alpha_s',\alpha_s')= 1-(\omega_s,\omega_s)^{-1}\leq0$，即 $0<(\omega_s,\omega_s)\leq1$。又由于 @Pre:level-1 证明了 $\minus{\Gamma}{s}$ 作为不可约的 level 1 的图，其基本区域的闭包 $\barfd_s$ 属于 $\Q$ 的同一个连通分支（此 $\Q$ 是 ${\rm span}\{\alpha_t,t\ne s\}$ 中 $(v,v)\leq0$ 构成的集合），从而 $-\alpha_s'$ 和 $\{\omega_t,t\ne s\}$ 都属于此分支，所以对任何 $t\ne s$ 有 $(-\alpha_s',\omega_t)=(\omega_s,\omega_t)/(\omega_s,\omega_s)\leq0$，即 $(\omega_s,\omega_t)\leq 0$，于是所有的 $\{(\omega_s,\omega_t)\}_{t\ne s}$ 都非正。

总之我们证明了不论 $(\omega_s,\omega_s)$ 的符号如何，它与其它的基本权的内积 $(\omega_s, \omega_t)$ 都非正。

又因为对任何 $s,t$，$\minus{\Gamma}{s,t}$ 是有限或者仿射的，所以其正交补，即 $\{\omega_s,\omega_t\}$ 张成的二维子空间不是正定的，从而 $\{\omega_s\}$ 之间是两两分离的。

:::note
我们需要考虑 $\alpha_s$ 的投影 $\alpha_s'$ 是因为 $\alpha_s$ 不属于 ${\rm span}\{\alpha_t,\,t\ne s\}$，无法直接根据 $(\alpha_s,\alpha_t)\leq0$ 得出 $\alpha_s$ 属于 $\minus{\Gamma}{s}$ 的基本区域的闭包。
:::

最后我们来补上断言的证明。

首先是断言 1 的证明。和 level 1 那里的证明一样，我们仍然记
$$I_+=\{s\in S\mid u_s>0\},\quad I_-=\{s\in S\mid u_s<0\},\quad I_0=\{s\in S\mid u_s=0\}.$$
并记 $u_+=\sum_{s\in I_+}u_s\alpha_s$，$u_-=\sum_{t\in I_-}u_t\alpha_t$。则 $(u,u)<0$ 和 $(u_+,u_-)\geq0$ 说明 $(u_+, u_+) < 0$ 和 $(u_-, u_-)<0$ 中至少有一个成立。

如果 $|I_0|\geq2$，则 $(u,u)<0$ 与 $\Gamma$ 的 level 是 2 矛盾。所以 $|I_0|\leq 1$。

1. 如果 $I_+,I_-$ 都不是空集，则 $u_+,\,u_-$ 均不为 0。由于 $(u_+, u_+) < 0$ 和 $(u_-, u_-)<0$ 中至少有一个成立，不妨设 $(u_+,u_+)<0$，结合 $\Gamma$ 的 level 是 2，这要求 $|I_-\cup I_0|\leq 1$，从而只能是 $|I_-|=1,\, I_0=\emptyset$。即系数全部非 0 且恰好有一个异号。
2. 如果 $I_+,I_-$ 中有一个是空集，不妨设 $I_-=\emptyset$，我们仍然有 $|I_-\cup I_0|=|I_0|\leq1$。即系数至多有一个为 0 且其它的均同号。

总之我们证明了除去至多一个系数之外，其它的系数均非 0 且同号。断言 1 得证。

对断言 2，类似地我们记
$$I_+=\{s\in S\mid v_s>0\},\quad I_-=\{s\in S\mid v_s<0\},\quad I_0=\{s\in S\mid v_s=0\}.$$
并记 $v_+=\sum_{s\in I_+}v_s\alpha_s$，$v_-=\sum_{t\in I_-}v_t\alpha_t$。

首先 $|I_0|\leq2$ 是显然的，否则 $(v,v)=0$ 与 $\Gamma$ 的 level 是 2 和 @Pre:level-l 矛盾。

1. 如果 $I_0\ne\emptyset$，则 $I_+,I_-$ 中必有一个为空。否则 $|I_+\cup I_0|\geq2,\,|I_-\cup I_0|\geq2$。level 2 要求 $(v_+,v_+)\geq0,\,(v_-,v_-)\geq0$，从而 $(v,v)=0$ 和 $(v_+,v_-)\geq0$ 导致 $(v_+,v_+)=(v_-, v_-)=(v_+,v_-)=0$。由于 $\Gamma$ 至少包含 4 个顶点，所以 $I_+,\,I_-$ 中必有一个包含两个或者更多的顶点。不妨设 $|I_+|\geq2$，则删除 $I_+\cup I_0$ 会至少删掉 3 个顶点，但得到的子图不是正定的，与 $\Gamma$ 的 level 等于 2 矛盾。所以系数 $\{v_s\}$ 中如果有 0 的话，则至多只有两个 0，且剩下的都同号。
3. 如果 $I_0=\emptyset$ 是空集，则要么 $I_+,I_-$ 中有一个也是空集，从而所有的系数都非 0 且同号；要么 $v_+,\,v_-$ 均不为 0。这时 $\Gamma$ 连通说明 $(v_+,v_-)>0$，结合 $(v,v)=0$ 可以得出 $(v_+,v_+) < 0$ 和 $(v_-, v_-)<0$ 中至少有一个成立。不妨设 $(v_+,v_+)<0$，则 level 2 要求 $|I_-|\leq1$，即 $\{v_s\}$ 均非零且恰有一个元素与其它元素异号。

至此断言 2 得证，从而定理得证。$\blacksquare$