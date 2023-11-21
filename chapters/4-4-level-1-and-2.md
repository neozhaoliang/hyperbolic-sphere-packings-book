## level = 1, 2 等价于双曲和分离

:::{.theorem #level-12}
下面两点是等价的：

1. $\Gamma$ 的 level 等于 1 或 2；
2. $\Gamma$ 是双曲的，且任何两个权都互相分离。
:::

**证明**：


$1\Rightarrow 2$：只要再证明对任何 $w\in W$，以及两个基本权 $\omega_i,\,\omega_j$，如果有 $\omega_i\ne w(\omega_j)$，则 $(\omega_i,w(\omega_j))\leq0$，并且二维子空间 $\{\omega_i,w(\omega_j)\}$ 不是正定的。

对长度 $l(w)$ 归纳：$l(w)=0$ 的情形在 @Pre:level-1 和 @Pre:level-2 中已经证明。下面假设 $l(w)>0$，且结论对所有长度 $<l(w)$ 的群元素成立。

1. 如果存在 $k\ne i$ 使得 $l(s_kw)<l(w)$，则 $\omega_i=s_k(\omega_i)\ne s_kw(\omega_j)$，由归纳假设 $\{\omega_i,s_k(\omega_j)\}$ 是分离的，从而 $\{\omega_i,\omega_j\}$ 作为 $\{\omega_i,s_k(\omega_j)\}$ 的正交变换得到的向量组也是分离的。

2. 如果对任何 $k\ne i$ 都有 $l(s_kw)>l(w)$，则 $w$ 的任一既约表示必然以 $s_i$ 开头，即 $w$ 形如 $w=s_iw'$ 且 $l(w)>l(w')$。从而
    $$(\omega_i,w(\omega_j))=(s_i(\omega_i), w'(\omega_j))=(\omega_i, w'(\omega_j))-2(\alpha_i,w'(\omega_j)).$$

    + 如果 $\omega_i\ne w'(\omega_j)$，则由归纳假设上面第一项 $(\omega_i, w'(\omega_j))\leq0$。第二项由于 $l(s_iw')>l(w')$，即 $l(w'^{-1}s_i)>l(w'^{-1})$，所以 $w'^{-1}\alpha_i\in\Phi^+$，从而 $(w'^{-1}\alpha_i, \omega_j)\geq0$，即 $(\alpha_i, w'(\omega_j))\geq0$，所以 $(\omega_i,w(\omega_j))\leq0$ 成立。
    + 如果 $\omega_i=w'(\omega_j)$，则 $s_i(\omega_i)=w(\omega_j)$，于是
      $$(\omega_i, w(\omega_j))=(\omega_i, s_i(\omega_i))=(\omega_i,\omega_i-2\alpha_i)=(\omega_i, \omega_i)-2 <0.$$
      其中最后一个不等号是利用了 @Pre:level-1 和 @Pre:level-2 的结论：若 $\Gamma$ 的 level 是 1 则 $(\omega_i, \omega_i)\leq0$，若 $\Gamma$ 的 level 是 2 则 $(\omega_i,\omega_i)\leq 1$。

    为了证明 ${\rm span}\{\omega_i,w(\omega_j)\}$ 不是正定的，用反证法。我们先插入一个简单的线性代数引理，它的证明很简单，我这里省略。

    > **引理**：在一个内积空间中，设 $x$ 是一个向量，$U$ 是一个子空间，$v$ 是 $x$ 在 $U$ 上的投影分量，$U_1$ 是 $v$ 在 $U$ 中的正交补，则 $U_1=x^\bot\cap U$。

    回到反证法。如果二维子空间 ${\rm span}\{\omega_i,w(\omega_j)\}$ 是正定的，设 $v$ 是 $w(\omega_j)$ 在
    $$U=\omega_i^\bot={\rm span}\{\alpha_k,\,k\ne i\}$$
    上的投影分量，$U_1$ 是 $v$ 在 $U$ 中的正交补，则
    $$U_1=w(\omega_j)^\bot\cap U=w(\omega_j)^\bot\cap\omega_i^\bot=\{\omega_i,w(\omega_j)\}^\bot$$
    是一个 time-like 的子空间，所以 $v\in U_1^\bot$ 是 space-like 的：$(v,v)>0$。然而对任何 $k\ne i$，由于 $\alpha_k\in U$ 所以 $(\alpha_k, w(\omega_j)-v)=0$，所以
    $$(v,\alpha_k) = (w(\omega_j),\alpha_k)=(\omega_j, w^{-1}\alpha_k).$$
    $l(s_kw)>l(w)$ 说明 $w^{-1}\alpha_k\in\Phi^+$，所以 $(\omega_j, w^{-1}\alpha_k)\geq0$，即 $(v,\alpha_k)\geq0$。这对任何 $k\ne i$ 都成立所以 $v$ 属于 $\minus{\Gamma}{i}$ 的基本区域的闭包。但是根据反证假设 $\omega_i$ 是实的，所以 $\minus{\Gamma}{i}$ 的 level 是 1，它的基本区域的闭包中的点都是 time-like 或者 light-like 的，从而必须有 $(v, v)\leq0$，这与 $v$ 是 space-like 的矛盾。

$2\Rightarrow 1$：由于内积 $\inn$ 是双曲的，而子空间 $\span\{\omega_i,\omega_j\}$ 不是正定的，所以其正交补是正定或者半正定的。于是 $\minus{\Gamma}{i,j}$ 是有限或者仿射的，从而 $\Gamma$ 的 level 等于 1 或 2。

:::note
这里考虑 $w(\omega_j)$ 的投影分量 $v$ 的理由同样是因为 $w(\omega_j)$ 未必属于 ${\rm span}\{\alpha_k,\,k\ne i\}$，所以由 $(w(\omega_j),\alpha_k)\geq0$ 无法得出 $w(\omega_j)$ 属于 $\minus{\Gamma}{i}$ 的基本区域。
:::