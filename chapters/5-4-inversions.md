## 球面的反演

::: definition
设 $B$ 是 $\R^n$ 中以 $\a$ 为中心，半径为 $r$ 的球。关于 $B$ 的反演 $\tau:\ER\to\ER$ 定义为
$$\tau(\x)=\frac{r^2}{|\x-\a|^2}(\x-\a) +\a.$$
:::
$\tau$ 是 $\R^n$ 中关于球面镜 $B$ 的反射，它保持 $B$ 的球面不动，将 $B$ 的内部映射为外部（反之亦然），并且 $\tau^2=1$。

![](images/cartoon_mirror.png){width=400}

我们来说明 $\tau$ 可以实现为 $n+1$ 维射影空间 $\PR$ 中的射影正交变换。

设 $\x\in\R^n$，$\imath(x)=(\x,1,|\x|^2)\in\L$。记 $k_B=\left(\frac{\a}{r},\frac{1}{r},\frac{|\a|^2-r^2}{r}\right)$ 为 $B$ 对应的单位向量，考虑反射 $\rho_B:\LR\to\LR$：
$$\rho_B(v) = v - 2(v,k_B)k_B,\quad v\in V.$$
注意到 $(\imath(x),k_B)=\frac{r^2-|\x-\a|^2}{2r}$，我们来验证
$$\begin{align*}
\begin{pmatrix}\x\\1\\ |\x|^2\end{pmatrix} &\xrightarrow{\rho_B}
\begin{pmatrix}\x\\1\\ |\x|^2\end{pmatrix} -\frac{r^2-|\x-\a|^2}{r}\begin{pmatrix}\frac{\a}{r}\\\frac{1}{r}\\ \frac{|\a|-r^2}{r}\end{pmatrix}\\
&=\begin{pmatrix}\x+\left(\frac{|\x-\a|^2}{r^2}-1\right)\a\\\frac{|\x-\a|^2}{r^2}\\ \ast \end{pmatrix}\\
&\sim \begin{pmatrix}\a+\frac{r^2}{|\x-\a|^2}(\x-\a)\\1\\ \ast \end{pmatrix}.
\end{align*}$$
这里我们不用关心 $\ast$ 是什么，最后的 $\sim$ 表示两个向量是射影等价的。注意到最后一步使用的归一化因子是 $\frac{|\x-\a|^2}{r^2}\geq0$，所以还是正射影等价的。

即我们有如下的交换图：

$$\require{amsCd}
\begin{CD}
\ER @>{\imath}>> \PL\\
@V{\tau}VV  @VV{\rho_B}V \\
\ER @>{\imath}>> \PL
\end{CD}$$

不仅如此，球和球之间的反演也可以通过 $\rho_B$ 来计算。设 $k$ 是球 $B'$ 对应的 space-like 的单位向量，则 $\rho_B(k)$ 也是 space-like 的单位向量，从而对应另一个球 $B''$。对 $\x\in\R^n$，根据上面的交换图有 $\rho_B\imath=\imath\tau$，从而
$$\x\in B''\Leftrightarrow (\imath(\x), \rho_B(k))=0
\Leftrightarrow(\rho_B(\imath(\x)), k)=0
\Leftrightarrow(\imath(\tau(\x)), k)=0
\Leftrightarrow \tau(\x)\in B'.
$$
