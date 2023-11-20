## Tits 锥的对偶锥

这一节来讨论 Tits 锥的对偶锥。研究对偶锥对理解 Tits 锥本身的结构也很有帮助。

设 $C$ 是 $V$ 中的一个锥，定义 $C$ 的对偶锥 $C^\ast\in V^\ast$ 为
$$C^\ast = \{f\in V^\ast\mid f(v)\geq0,\ \forall v\in C\}.$$
即 $C^\ast$ 是对偶空间中那些在 $C$ 上取值均非负的线性泛函组成的集合。

不难看出 $C^\ast$ 也构成 $V^\ast$ 中的一个锥，所以我们又可以取其对偶锥 $C^{\ast\ast}\subset V$。

:::{.theorem #dual-dual-cone}
$C^{\ast\ast} = \overline{C}$。其中 $\overline{C}$ 是 $C$ 的拓扑闭包。
:::

**证明**：显然 $\overline{C}\subseteq C^{\ast\ast}$，只要论证 $C^{\ast\ast} \subseteq \overline{C}$ 即可。

对任何 $x\notin\overline{C}$，根据凸集分离定理，存在超平面 $H$，其法向量 $n$ 满足 $(n,C)\geq 0$ 但是 $(n,x) < 0$。于是线性泛函 $(n,\cdot)\in C^\ast$ 且由于 $(n,x)<0$ 从而 $x\notin C^{\ast\ast}$。反向包含得证。$\blacksquare$

:::note
对不熟悉凸集分离定理的读者，下面是一点细节补充：设 $u\in\overline{C}$ 是 $\overline{C}$ 中与 $x$ 距离最近的点：$|x-u|=\inf_{z\in \overline{C}}|x-z|$。对任何 $z\in\overline{C}$，考虑线段 $[u,z]$ 上的点与 $x$ 的距离 $$f(t) = |u + t(z-u) - x|,\quad 0\leq t\leq1.$$
$f$ 在 $t=0$ 时取得最小值： $$ |u-x|^2 \leq |u-x|^2 + 2t(u-x, z-u) + t^2|z-u|^2.$$ 即 $$0\leq t\cdot\left(2(u-x,z-u) + t|z-u|^2\right)\leq 2(u-x,z-u) + t|z-u|^2.$$ 令 $t\to0^+$ 可得 $(u-x,z-u)\geq 0$。 这个式子对任何 $z\in\overline{C}$ 成立，特别地取 $z=tu$ 代入有 $$(1-t)\cdot(u-x, u)\geq0.$$ 上式对任何 $t\geq0$ 成立必须只能是 $(u-x, u)=0$。于是不等式 $$(u-x,z-u)\geq 0$$ 可以改写为 $$(u-x,z)\geq0$$ 对任何 $z\in\overline{C}$ 成立。而 $(u-x,x)=-(u-x,u-x)<0$。所以 $u-x$ 即为所求的法向量 $n$。
:::

定义 $\cone{\Delta}$ 为单根系 $\Delta$ 的所有非负系数线性组合：
$$\cone{\Delta} = \left\{\sum_{s\in S}c_s\alpha_s,c_s\geq0\right\}.$$
显然 $\cone{\Delta}$ 是 $V$ 中的一个闭凸锥，它在 $V^\ast$ 中的对偶锥正是基本区域的闭包 $\barfd$：
$$\barfd = \{x\in V^\ast\mid \lfun{v}{x}\geq0,\ \forall v\in\cone{\Delta}\}.$$

回到 Tits 锥 $\tc$ 的讨论上来。由于 $\tc\in V^\ast$ 所以 $\tc^\ast\in V$。我们有如下定理：

:::{.theorem #tits-cone-dual}
Tits 锥 $\tc$ 的对偶锥为 $\tc^\ast=\bigcap\limits_{w\in W}w(\overline{\cone{\Delta}})$。
:::

:::note
由定理结论可见 Tits 锥的对偶锥同样是 $W-$ 不变的。
:::

**证明**：

$$
\begin{align}
\tc^\ast &=\{v\in V \mid \lfun{v}{x}\geq 0 \text{ for all } x \in \tc\}\\
&= \{v\in V \mid \lfun{v}{wz}\geq0 \text{ for all } z\in\barfd \text{ and } w \in W\}\\
&= \{v\in V \mid \lfun{w^{-1}v}{z}\geq0 \text{ for all } v\in\barfd \text{ and } w \in W\}\\
&= \{v\in V \mid w^{-1}v\in (\barfd)^\ast \text{ for all } w \in W\}\\
&\stackrel{(\ast)}{=} \{v\in V \mid w^{-1}v\in \overline{\cone{\Delta}} \text{ for all } w \in W\}\\
&= \{v\in V \mid v\in w(\overline{\cone{\Delta}}) \text{ for all } w \in W\}.
\end{align}
$$

其中 $(\ast)$ 一步正是将 @Pre:dual-dual-cone 应用在 $C=\cone{\Delta},\,C^\ast=\barfd$ 上得到的。$\blacksquare$

虽然我们得到了上面关于 $\tc^\ast$ 的刻画，但是它并不好用。我们下面用内积的形式给出 $\tc^\ast$ 的一个更好的刻画。

:::{.proposition #dual-cone-dot-neg}
如果 $v\in\cone{\Delta}$ 满足对任何 $\alpha_s\in\Delta$ 有 $(v,\alpha_s)\leq0$，则 $v\in\tc^\ast$。
:::

**证明**：只要证明对任何 $w$ 都有 $wv\in\cone{\Delta}$ 即可。对 $l(w)$ 归纳：$l(w)=0$ 的情形是已知，假设结论对小于 $l(w)$ 都成立，对 $l(w)$ 的情形设 $w=w's$，其中 $l(w')<l(w)$，则 $w'\alpha_s\in\Phi^+$。于是

$$
\begin{align}wv &= w'sv\\
&=w'(v - 2(v,\alpha_s)\alpha_s)\\
&=w'v - 2(v,\alpha_s)w'\alpha_s.
\end{align}
$$

根据归纳假设 $w'v\in\cone{\Delta}$，再结合 $w'\alpha_s\in\Phi^+\subset\cone{\Delta}$，所以结论成立。

:::{.proposition #dual-cone-nonspace}
对任何 $u,v\in\tc^\ast$ 有 $(u,v)\leq 0$。
:::

**证明**：由于 $\Delta$ 构成 $V$ 的一组基，所以任何 $v\in V$ 可以表示为 $\Delta$ 的线性组合：$v = \sum_{s\in S}c_s\alpha_s$。定义 $S(v)=\sum_{s\in S}c_s$ 为所有系数的和。特别地，当 $v\in\tc^\ast\subset\cone{\Delta}$ 时，每个 $c_s$ 都是非负的，所以 $S(v)\geq0$。

用反证法，设 $u,v\in\tc^\ast$ 满足 $(u,v)>0$，不妨设 $(u,v)=1$。记 $n=|S|$ 和 $M=S(u)$。定义

$$X=\{x\in\tc^\ast\mid S(x)\leq S(v) \text{ and $(z,x)\geq1$ for some $z\in\tc^\ast$ with $S(z)\leq M$}\}.$$

显然 $v\in X$。

记 $\epsilon=2/(nM)$，我们将证明对任何 $x\in X$，都存在 $y\in X$ 使得 $S(y)\leq S(x)-\epsilon$。

对 $x\in X$，设 $z=\sum_{s\in S}z_s\alpha_s\in\tc^\ast$ 满足 $S(z)\leq M$ 和 $(z,x)\geq1$，则
$$(z,x)=\sum_{s\in S}z_s(\alpha_s, x)\geq1.$$
所以必有某个 $\alpha_s$ 使得 $z_s(\alpha_s,x)\geq 1/n$。由于 $z_s\leq S(z)\leq M$，我们有 $(\alpha_s,x)\geq 1/(nz_s)\geq 1/(nM)=\epsilon/2$。

考察
$$y=sx=x-2(x,\alpha_s)\alpha_s.
$$
由于 $x\in\tc^\ast$ 以及 $\tc^\ast$ 是 $W-$ 不变的所以 $y\in\tc^\ast$。又注意到 $S(y)=S(x)-2(x,\alpha_s)\leq S(x)-\epsilon$，所以要证明 $y$ 符合要求，只要再找到某个 $z'\in\tc^\ast$ 满足 $S(z')\leq M$ 和 $(z',y)\geq1$ 即可。

如果 $(z,\alpha_s)<0$，那么 $z'=z$ 就满足要求，因为这时
$$(z,y)=(z,x-2(x,\alpha_s)\alpha_s)=(z,x)-2\underbrace{(x,\alpha_s)}_{\geq\epsilon/2}\underbrace{(z,\alpha_s)}_{<0}>(z,x)\geq1.$$

反之如果 $(z,\alpha_s)>0$，我们来验证 $z'=sz=z-2(z,\alpha_s)\alpha_s$ 满足要求：由于 $z\in\tc^\ast$ 所以 $z'\in\tc^\ast$，并且 $S(z')=S(z)-2(z,\alpha_s)<S(z)$，以及
$$(z', y)=(sz, sx)=(z,x)\geq1.$$

所以从 $v=x$ 开始出发，我们经过有限次后取到 $y\in X$ 使得 $S(y)$ 是负数，这与 $y\in\tc^\ast$ 矛盾。$\blacksquare$