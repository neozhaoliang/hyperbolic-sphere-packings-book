## 几何实现

抽象 Coxeter 群是用生成元和生成关系定义的，直接从这种定义出发研究群结构是非常困难的。在这一节中，我们将介绍如何将抽象的 Coxeter 群“实现”为一个内积空间中的正交反射群，从而可以使用几何、线性代数等多种工具来研究它。

设 $(W,S)$ 是一个 Coxeter 系，$M=(m_{s,t})_{s,t\in S}$ 是 Coxeter 矩阵，$V$ 是一个维数为 $n=|S|$ 的实向量空间，其一组基为 $\{\alpha_s \mid s\in S\}$。我们规定 $V$ 上的一个内积 $\inn$ 如下：

$$(\alpha_s,\alpha_t)=\begin{cases}-\cos\frac{\pi}{m_{s,t}}&m_{s,t}<\infty,\\-a_{s,t}&m_{s,t}=\infty.\end{cases}$$

这里 $a_{s,t}\geq 1$，不同的 $(s,t)$ 对可以使用不同的 $a_{s,t}$。

根据定义 $(\alpha_s,\alpha_s)=-\cos\frac{\pi}{1}=1$。

::: note
$a_{s,t}=1$ 表示 Euclidean 空间中两个平行的镜面（或者双曲空间中两个平行的镜面）；$a_{s,t}>1$ 表示双曲空间中两个超平行的镜面；$m_{s,t}<\infty$ 表示两个相交的镜面。

下图显示了对同一个抽象 Coxeter 群

![](images/3-4-inf.svg){height=100}

对标号为 $\infty$ 的边选择 $a_{s,t}=1$ 和 $a_{s,t}=1.15$ 时给出的效果：

| 平行 $a_{s,t}=1$ | 超平行  $a_{s,t}=1.15$ |
|:---:|:---:|
|![](images/parallel.png)|![](images/hypparallel.png)|

所以同一个抽象 Coxeter 群在实现为反射群时，尽管这些反射群都是同构的，但它们给出的万花筒的几何结构却可以不同。
:::

上面定义的 $\inn$ 未必是通常所指的欧氏内积，而且不同的 $W$ 给出的 $\inn$ 的 Sylvester 符号可能是不同的。但我们最关心的情形有三种：

1. 如果 $\inn$ 是正定的，就称 $\inn$ 是有限型的；
2. 如果 $\inn$ 是半正定的，但不是正定的，就称 $\inn$ 是仿射型的；
3. 如果 $\inn$ 的 Sylvester 符号是 $(n-1, 1)$，就称 $\inn$ 是双曲型的。

不属于以上三种类型的一律称为不定的。

正如名字所暗示的那样，$\inn$ 是有限型的当且仅当 $W$ 是有限反射群，这时 $W$ 给出的万花筒是球面上的密铺；$\inn$ 是仿射型的当且仅当 $W$ 是 Euclidean 空间上的仿射 Weyl 群，这时 $W$ 给出的万花筒是 Euclidean 空间中的密铺；$\inn$ 是双曲型的意味着 $W$ 给出的是双曲空间中的密铺。这些我们会在后面进行仔细的讨论。

::: note
在后文中，我们也会用 $\inn$ 的类型来称呼 $W$ 以及对应的 Coxeter 图 $\Gamma$。例如当 $\inn$ 是仿射型时，我们也称 $W$ 是仿射的，$\Gamma$ 是仿射的。其它类型同理。这样做有个问题是，$a_{s,t}$ 的选择可能会影响 $\inn$ 的 Sylvester 符号，导致同一个群 $W$ 在不同的几何实现中有不同的类型。为避免这一问题，我们假定已经事先确定好了一个几何实现，并始终在此实现下讨论。
:::

对任何 $s\in S$，定义 $V$ 上的反射 $\rho_s$ 为
$$\rho_s(v) = v -2(v,\alpha_s)\alpha_s ,\quad v\in V.$$

我们来证明 $s\to\rho_s$ 实际上是从 $(W,S)$ 到 $\gl(V)$ 的群同态，从而 $\rho: W\to\rho(W)\leqslant\gl(V)$ 是一个线性表示。为此只要证明：

::: Proposition
$(\rho_s\rho_t)^{m_{s,t}}=1$ 对任何 $s,t\in S$ 成立。
:::

**证明**：当 $s=t$ 时所证即为 $\rho_s^2=1$，由于 $\rho_s$ 是反射这当然是成立的。

下设 $s\ne t$，令 $V_{s,t}={\rm span}\{\alpha_s,\alpha_t\}$ 是 $\alpha_s,\alpha_t$ 张成的二维子空间，并记 $V_{s,t}^\bot$ 是 $V_{s,t}$ 在 $\inn$ 下的正交补空间。不难验证 $\rho_s$ 和 $\rho_s$ 限制在 $V_{s,t}^\bot$ 上都是恒等变换。

注意不一定有 $V=V_{s,t}\oplus V_{s,t}^\bot$ 成立，因为 $\inn$ 有可能是退化的。但是只要 $\inn$ 非退化，或者 $\inn\mid_{V_{s,t}}$ 是非退化的，那么 $V=V_{s,t}\oplus V_{s,t}^\bot$ 就成立。

我们来计算 $\sigma=\rho_s\rho_t$ 的阶。记 $m=m_{s,t}$，分情况讨论：

:::{#rank2-roots}
:::

1. $m<\infty$。这时 $\inn$ 限制在 $V_{s,t}$ 上的 Gram 矩阵是
$$\begin{pmatrix}1&-\cos\theta\\-\cos\theta&1\end{pmatrix},\qquad \theta=\frac{\pi}{m}.$$
这个矩阵是正定的，从而 $\inn\mid_{V_{s,t}}$ 非退化，这时 $V=V_{s,t}\oplus V_{s,t}^\bot$ 是成立的，而 $\sigma$ 限制在 $V_{s,t}^\bot$ 上是恒等变换，所以 $\sigma$ 在 $V$ 上的阶就等于它在 $V_{s,t}$ 上的阶。我们有 $\rho_s(\alpha_s)=-\alpha_s$ 和 $\rho_s(\alpha_t)=2\cos\theta\alpha_s+\alpha_t$，以及关于 $\rho_t$ 的类似表达式。不难验证有
$$\begin{align*}&\alpha_s\xrightarrow{\ \rho_t\ }\sthe{}\alpha_s+\sthe{2}\alpha_t\xrightarrow{\ \rho_s\ }\sthe{3}\alpha_s+\sthe{2}\alpha_t\xrightarrow{\ \rho_t\ }\sthe{3}\alpha_s+\sthe{4}\alpha_t\xrightarrow{\ \rho_s\ }\cdots\\
&\alpha_t\xrightarrow{\ \rho_s\ }\sthe{2}\alpha_s+\sthe{}\alpha_t\xrightarrow{\ \rho_t\ }\sthe{2}\alpha_s+\sthe{3}\alpha_t\xrightarrow{\ \rho_s\ }\sthe{4}\alpha_s+\sthe{3}\alpha_t\xrightarrow{\ \rho_t\ }\cdots\end{align*}
$$
这两个链的周期都是 $2m$，它们的第 $2m+1$ 项分别是 $\sthe{(2m+1)}\alpha_s+\sthe{(2m)}\alpha_t=\alpha_s$ 和 $\sthe{(2m)}\alpha_s+\sthe{(2m+1)}\alpha_t=\alpha_t$，又回到了各自的第一项。所以 $\sigma$ 的阶等于 $m$。

2. $m=\infty$。这时未必有 $V=V_{s,t}\oplus V_{s,t}^\bot$。我们来论证 $\sigma$ 在 $V_{s,t}$ 上的阶是无穷，那么它在 $V$ 上的阶必然也是无穷。
设 $\theta\geq0$ 使得 $a_{s,t}=\cosh\theta$，不难验证有
$$\begin{align*}&\alpha_s\xrightarrow{\ \rho_t\ }\shthe{}\alpha_s+\shthe{2}\alpha_t\xrightarrow{\ \rho_s\ }\shthe{3}\alpha_s+\shthe{2}\alpha_t\xrightarrow{\ \rho_t\ }\shthe{3}\alpha_s+\shthe{4}\alpha_t\xrightarrow{\ \rho_s\ }\cdots\\
&\alpha_t\xrightarrow{\ \rho_s\ }\shthe{2}\alpha_s+\shthe{}\alpha_t\xrightarrow{\ \rho_t\ }\shthe{2}\alpha_s+\shthe{3}\alpha_t\xrightarrow{\ \rho_s\ }\shthe{4}\alpha_s+\shthe{3}\alpha_t\xrightarrow{\ \rho_t\ }\cdots\end{align*}
$$（当 $a_{s,t}=1$ 时 $\theta=0$，$\shthe{k}$ 应当理解为 $k$）

   这两个链条都是永不重复的，所以 $\sigma$ 的阶是无穷。

至此命题得证。$\blacksquare$

::: note
这个命题的证明虽然看起来包含了一些复杂的计算，但是我们做的事情很重要：我们实际上计算了 $s,t$ 生成的二面体群的根系，这个计算结果在后面会用到。
:::


后面我们会看到 $\rho$ 实际是一个同构，这样就把抽象的 Coxeter 群 $W$ “实现为”具体的反射群 $\rho(W)$。

最后是一个记号的简化：我们把 $w\in W$ 在 $V$ 上的作用简写为 $\rho(w)(v)=wv$。
