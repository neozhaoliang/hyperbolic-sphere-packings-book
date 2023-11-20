# 球的反演

在这一章中，我们都约定 $V=\R^{n+1,1}$ 是 $n+2$ 维的 Lorentzian 空间，$e_1,e_2,\ldots,e_{n+2}$ 是 $V$ 的一组标准正交基，即在这组基下内积的 Gram 矩阵为
$$\begin{pmatrix}I_{n+1} &\\ & -1\end{pmatrix}.$$
令
$$e_0=\frac{1}{2}(e_{n+2}-e_{n+1}),\quad e_\infty=\frac{1}{2}(e_{n+2}+e_{n+1}).$$
则 $\{e_1,\ldots,e_n,e_0,e_\infty\}$ 也构成 $V$ 的一组基，$\inn$ 在这组基下的 Gram 矩阵为
$$\begin{pmatrix}I_n&&\\&0& -\frac{1}{2}\\&-\frac{1}{2}&0\end{pmatrix}.$$
任何 $v\in V$ 可以写成 $v=\x + ae_0 + be_\infty$ 的形式，其中 $\x\in{\rm span}\{e_1,\ldots,e_n\}$ 是一个 Euclidean 度量空间中的向量，$a,b\in\R$。所以 $v$ 可以用一个三元组 $v=(\x,a,b)$ 来表示，并且两个三元组之间的内积为：
$$((\x,a,b), (\y,c,d)) = (\x,\y)-\frac{1}{2}(ad+bc).$$
这种表示方式在处理球面时会更加方便。


## 射影模型


对 $v\in\R^{n+1,1}$，我们约定用 $[v]$ 表示 $v$ 在射影空间 $\PR$ 中的等价类。

::: definition
定义光锥 (light cone/null cone) 为
$$\L = \{v\in \LR \mid(v,v)=0\}.$$
以及
$$\PL=\{[v]\mid v\in\L-\{0\}\}.$$
$\PL$ 可以看作是 $\L$ 中所有直线组成的集合。
:::

在除去原点以后，$\L$ 同样由上下两个连通分支组成。记 $\L_+$ 是其上半分支，则 $\PL$ 也可以写成 $\PL =\L_+/\R_{>0}$。

我们知道 $\ER=\R^n\cup\{\infty\}$ 和单位球 $S^n=\{x_1^2+x_2^2+\cdots+x_{n+1}^2=1\}\subset\R^{n+1}$ 在球极投影下是一一对应的。我们来说明它们分别和 $\PL$ 是一一对应的，并且当 $x\in\ER$ 和 $y\in S^n$ 是球极投影下对应的点时，它们在 $\PL$ 中对应的是同一个点。

具体的对应如下图所示：$S^n$ 对应的是图中的红圈，它是 $\L_+$ 与超平面 $v_{n+2}=1$ 相交的截线；$\R^n$ 对应的是图中的 horosphere，它是 $\L_+$ 和超平面 $v_{n+2}-v_{n+1}=1$ 相交的截线；$\infty$ 对应的是 $e_\infty$，它不在 horosphere 上。

![原图出自 [conformalgeometricalgebra](http://conformalgeometricalgebra.org/wiki/index.php?title=Main_Page)](images/Horosphere.svg){width=400}

我们来计算验证一下。

设 $\y\in\R^{n+1}$，记 $|\y|$ 为 $\y$ 的 Euclidean 范数，则
$$\y\in S_n\Leftrightarrow |\y|=1\Leftrightarrow((\y,1),(\y,1))=0\Leftrightarrow(\y,1)\in\L.$$
所以 $S^n$ 确实可以等同于截线
$$S^n_1=\{v\in\L_+ \mid v_{n+2}=1\},$$
对应由映射 $\jmath: S^n\to S^n_1$
$$\jmath(\y)= \y + e_{n+2}$$
给出，即 $\jmath$ 是把 $S^n$ 沿着 $e_{n+2}$ 的方向整体平移 1。由于 $\PL$ 中每个元素在 $S^n_1$ 中有唯一代表元，所以
$$S^n\to\PL: \y\to [\y+e_{n+2}],$$
是一一对应，此即为 $\PL$ 的第一种参数化表示。

另一方面，对 $[v]\in\PL$，如果 $v$ 的 $e_0$ 分量非零，则 $v$ 形如 $v=(\x,1,b),\,\x\in\R^n$。$v\in\L$ 说明 $|\x|^2-b=0$，即 $b=|\x|^2$，从而 $v=(\x,1,|\x|^2)$。如果 $v$ 的 $e_0$ 分量为 0，则 $v$ 形如 $v=(\x,0,b)$，$v\in\L$ 给出 $|\x|^2=0$，从而 $\x=0$，即 $v=(0,0,b),\,b\ne 0$，从而 $[v] = [(0,0,1)]=[e_\infty]$。

于是我们可以定义如下从 $\ER$ 到 $\PL$ 的一一对应 $\imath:\ER\to\PL$:
$$
\imath(\x)=\begin{cases}[(\x,1,|\x|^2)] & \x\in\R^n,\\
[e_\infty] & \x = \infty.
\end{cases}
$$
此即为 $\PL$ 的第二种参数化表示。

注意到形如 $(\x,1,|\x|^2)$ 的点构成了 $\L_+$ 与超平面 $v_{n+2}-v_{n+1}=1$ 的截线 $H_1$：
$$H_1 = \{ v\in\L \mid v_{n+2} - v_{n+1}  = 1\}.$$

设 $\y=y_1e_1+\cdots+y_{n+1}e_{n+1}\in S^n$，为方便记 $\ty=y_1e_1+\cdots+y_n\in\R^n$。$\y$ 在以 $e_{n+1}$ 为北极的球极投影下对应于
$$\x=\begin{cases}\frac{\ty}{1-y_{n+1}} & y_{n+1}\ne1\\
\infty & y_{n+1}=1.
\end{cases}
$$
我们来验证 $\jmath(\y)$ 和 $\imath(\x)$ 对应的是 $\PL$ 中的同一个点，即
$$[\y + e_{n+2}] = \begin{cases}[(\x,1,|\x|^2)] & y_{n+1}\ne1\\
[e_\infty] & y_{n+1}=1.
\end{cases}.$$

当 $y_{n+1}=1$ 时 $\y=e_{n+1}$ 从而 $\y+e_{n+2}= e_{n+1}+e_{n+2}=2e_\infty$，这显然与 $e_\infty$ 是射影等价的。

当 $y_{n+1}\ne 1$ 时，$\y\in S^n$ 说明 $(\ty,\ty)+y_{n+1}^2=1$，即 $$|\x|^2=\left|\frac{\ty}{1-y_{n+1}}\right|^2 = \frac{1+y_{n+1}}{1-y_{n+1}}.$$
把 $\y+e_{n+2}$ 转化为 $\{e_1,\ldots,e_n,e_0,e_\infty\}$ 这组基下的表示：
$$\y+e_{n+2} = \ty + (1-y_{n+1})e_0+(1+y_{n+1})e_\infty=(\ty, 1-y_{n+1}, 1+y_{n+1}).$$
从而
$$[\y+e_{n+2}] = \left[\left(\frac{\ty}{1-y_{n+1}}, 1, \frac{1+y_{n+1}}{1-y_{n+1}}\right)\right] = [(\x, 1, |\x|^2)].$$

