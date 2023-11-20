# Coxeter 群的 level

## level 的定义

在这一章中，我们来介绍 Coxeter 群的 level 的概念。

设 $\Gamma$ 是 $W$ 的 Coxeter 图，如果 $\Gamma'$ 是 $\Gamma$ 的子图，其顶点集是 $I\subseteq S$，则我们可以讨论 $\Gamma'$ 的类型，这个子图的类型由 $\inn$ 在子空间 ${\rm span}\{\alpha_s,s\in I\}$ 上的限制决定。

:::definition
@Maxwell82

一个 Coxeter 群 $(W,S)$ 的 level 定义为最小的非负整数 $l$，使得在其 Coxeter 图 $\Gamma$ 中删去任何 $l$ 个顶点后，剩下的每个连通分支都是仿射或者有限的。
:::

根据定义有限和仿射 Coxeter 群的 level 都是 0（因为不需要删去任何顶点）。

我们来看几个 level 大于 0 的例子：

::: example

|     |     |     |
|:---:|:---:|:---:|
| level=1 | level=2 | level=3 |
|![](images/level1.svg){width=120}|![](images/level2.svg){width=120}|![](images/level3.svg){width=120}|

+ 第一个图的三条边标号分别是 $(3,3,7)$，它不是有限的也不是仿射的，但是删去任何一个顶点以后剩下的两个顶点都构成一个有限二面体群，所以其 level 等于 1。
+ 第二个图的三条边标号分别是 $(3, 4, -1.1)$，它删去红色顶点以后剩下的两个顶点仍然构成一个 Vinberg 记号下的双曲群，所以 level 肯定大于 1；删去任何两个顶点的话只剩一个顶点当然是有限的，所以这个群的 level 等于 2。
+ 第三个图删去两个红色顶点以后剩下的两个顶点仍然构成一个 Vinberg 记号下的双曲群，所以 level 肯定大于 2；删去任何三个顶点以后只剩一个顶点当然是有限的，所以这个群的 level 等于 3。
:::

:::{.theorem #level-l}
在一个 level 等于 $l$ 的图中删去任何 $l+1$ 个顶点后，剩下的必然是一些有限的子图。
:::

**证明**：对 $l$ 归纳。当 $l=0$ 时，根据 [前面介绍过的事实](#affine-facts)，在一个有限或者仿射的图里面删去一个顶点剩下的一定都是有限子图，所以结论成立。

假设结论对所有小于 $l$ 的正整数成立，考虑 $l$ 的情形。用反证法。

不妨设删去 $\{i_1,\ldots,i_{l+1}\}$ 这 $l+1$ 个顶点后得到的不都是有限子图，那么剩下的部分中某个连通分支必然是仿射的。不妨设 $\Gamma-\{i_1,\ldots,i_{l+1}\}=\Gamma'\cup\Gamma''$，其中 $\Gamma'$ 是一个仿射的连通分支，$\Gamma''$（可能为空集）和 $\Gamma'$ 之间没有边相连。

由于 $\Gamma$ 是连通的，所以 $\Gamma'$ 必然和 $\{i_1,\ldots,i_{l+1}\}$ 中某个顶点有边连接，不妨设为 $i_{l+1}$：

![](images/lemma.svg){width=400}

由于 $\Gamma$ 的 level 是 $l$，所以 $\{i_{l+1}\}\cup\Gamma'\subseteq\Gamma-\{i_1,\ldots,i_l\}$ 是一个仿射的连通子图，这个仿射子图删除 $i_{l+1}$ 后得到的 $\Gamma'$ 仍然是仿射的，这与 $l=0$ 的情形矛盾，所以结论得证。$\blacksquare$
