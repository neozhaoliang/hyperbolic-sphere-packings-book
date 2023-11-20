# 预备知识

## 双线性型

设 $V$ 是一个实向量空间，维数 $\dim V=n$，$\inn$ 是 $V$ 上的一个对称双线性型。我们也称 $\inn$ 是一个内积。通过选取一组标准正交基，$\inn$ 的 Gram 矩阵形如
$$
\begin{pmatrix}
I_p&&\\
&-I_q&\\
&& {\bf 0}_r
\end{pmatrix}.
$$
其中 $p+q+r=n$。

在 $n$ 确定的情况下，我们用二元组 $(p,q)$ 表示内积的符号。例如：

1. $(n,0)$ 表示 $p=n,\,q=0$，即 $\inn$ 是正定的。
2. $(n-1,0)$ 表示 $p=n-1,\,q=0$，从而 $r=1$，即 $\inn$ 是半正定的。
3. $(n-1,1)$ 表示 $p=n-1,\,q=1$，即 $\inn$ 是双曲 (Lorentzian) 内积。

$V$ 的根空间 (radical) 定义为
$$\rad(V) = \{v\in V\mid (v, u)=0,\  \forall u\in V\}.$$
当 $\rad(V)=\{0\}$ 时我们称 $\inn$ 是非退化的。

设 $U$ 是 $V$ 的子空间，其正交补空间 $U^\bot$ 定义为
$$U^\bot = \{v\in V\mid (v,u)=0,\  \forall u\in U\}.$$

::: {.proposition  #orth-complement}
1. 如果 $\inn$ 或者 $\inn\mid_U$ 之一是非退化的，则 $\dim U+\dim U^\bot=n$。
2. 如果 $\inn\mid_U$ 是非退化的，则有 $V=U\oplus U^{\bot}$ 成立。
:::
**证明**：见 [@roman Chapter 11]。$\blacksquare$


当 $\inn$ 的符号是 $(n-1,1)$ 时，$V$ 在此内积下成为一个 Lorentzian 空间。我们称 $v\in V$ 是

1. space-like 的，如果 $(v,v)>0$；
2. light-like 的，如果 $(v,v)=0$；
3. time-like 的，如果 $(v,v)<0$。

这个概念也可以推广到 $V$ 的子空间中：如果 $U\subset V$ 是一个子空间，我们称 $U$ 是

1. space-like 的，如果 $\inn\mid_U$ 是正定的；
2. light-like 的，如果 $\inn\mid_U$ 是半正定的，但不是正定的；
3. time-like 的，如果 $\inn\mid_U$ 不属于以上两种情形，即 $U$ 包含 time-like 的向量。

由于 Lorentzian 内积是非退化的，所以对任何子空间 $U$ 都有 $\dim U + \dim U^\bot=n$ 成立。

::: {.proposition #orth-complement-lorentzian}
1. $U$ 是 space-like 的当且仅当 $U^\bot$ 是 time-like 的；
2. $U$ 是 light-like 的当且仅当 $U^\bot$ 是 light-like 的。
:::

**证明**：2 是 1 的直接推论。而 1 可以由 @Pre:orth-complement 的第二条立刻得出。

::: example
1. 如果 $v$ 是 space-like 的向量，那么 $(\R v)^\bot$ 是 $n-1$ 维的 time-like 的子空间，符号为 $(n-2, 1)$，并且 $V=\R v\oplus (\R v)^\bot$。
2. 如果 $v$ 是 time-like 的向量，那么 $(\R v)^\bot$ 是 $n-1$ 维的 space-like 的子空间，符号为 $(n-1, 0)$，并且 $V=\R v\oplus(\R v)^\bot$。
3. 如果 $v$ 是 light-like 的向量，那么 $(\R v)^\bot$ 是 $n-1$ 维的 light-like 的子空间，符号为 $(n-2,0)$。这时 $V\ne \R v\oplus(\R v)^\bot$，因为 $v\in\R v\cap(\R v)^\bot$。
:::

:::{#lorentzinian-decomposition}
:::

取 $z$ 是任一满足 $(z,z)=-1$ 的 time-like 的向量，记 $U=\R z$，则 $U^\bot$ 是 space-like 的并且有 $V=U\oplus U^\bot$ 成立。于是任何 $v\in V$ 可以写成 $v = \x + cz$ 的形式，这里 $\x\in U^\bot$ 是一个 Euclidean 度量空间中的向量，$c\in\R$ 是实数，$\x$ 和 $z$ 是正交的。

记
$$\Q=\{v\in V\mid (v,v)\leq 0\}$$
是所有非 space-like 的向量组成的集合，则 $v=\x+cz\in\Q$ 当且仅当 $(\x,\x)-c^2\leq0$。

在除去原点以后，$\Q-\{0\}$ 由两个连通分支 $\Q_+,\,\Q_-$ 组成，它们分别由 $\Q$ 中满足 $c>0$ 和 $c<0$ 的点组成，并且 $\Q_+=-\Q_-$。

![](images/hyperboloid.svg){width=400}

在本文中我们用记号 $u\sim v$ 来表示 $u,v$ 属于同一个连通分支，$u\not\sim v$ 表示 $u,v$ 属于不同的连通分支。

::: {.proposition #connected-component-dot}
设 $u,v\in \Q-\{0\}$。

1. 如果 $u\sim v$ 则 $(u,v)\leq0$。
2. $(u,v)=0$ 当且仅当 $u,v$ 是 light-like 的向量。
:::

**证明**：[参考 @ratcliffe section 3.1]

1. 不妨设 $u,v$ 都属于 $\Q_+$。记 $u=\x+cz,\, v=\y+dz$，其中 $x,y$ 是 space-like 的向量，$c,d>0$。记 $|\x|=\sqrt{(\x,\x)}$ 是 $x$ 的 Euclidean 范数，$|\y|$ 同理，则 $|\x|\leq c,\, |\y|\leq d$。由 Cauchy-Schwartz 不等式有
$$(u,v)=(\x,\y) - cd\leq |\x| |\y| - cd\leq cd-cd=0.$$
此即为所证。

2. 由 $(u,v)=0$ 有 $(\x,\y)=cd$，结合 $|(\x,\y)|\leq |\x| |\y|$ 有 $|cd|\leq |\x||\y|$。然而 $|\x|\leq |c|,\, |\y|\leq |d|$，这只能是所有等号成立。从而 $|\x|=|c|,\, |\y|=|d|$ 说明 $u,v$ 都是 light-like 的向量。由 $|(\x,\y)|=|\x||\y|$ 可得 $\x,\y$ 共线，设 $\x=\lambda \y$，代入 $(\x,\y)=cd$ 可得 $c=\lambda d$，从而 $u=\lambda v$。

$\blacksquare$


这个命题有显然的推论是：

::: {.corollary #suff-for-equiv}
设 $u,v\in\Q-\{0\}$。

1. 若 $(u,v)>0$ 则 $u\not\sim v$。
2. 若 $(u,v)\leq0$，且 $u,v$ 中有一个是 time-like 的，则 $u\sim v$。
:::
