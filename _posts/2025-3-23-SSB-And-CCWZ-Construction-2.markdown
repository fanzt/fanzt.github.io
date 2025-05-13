---
layout:     post
title:      "Spontaneous Symmetry Breaking and CCWZ Construction 2"
subtitle:   "Anderson-Higgs Mechanism"
date:       2025-3-23 20:20:00
author:     "fromuly"
header-img: "img/post-bg-2025-7.jpg"
catalog: true
usemathjax: true
music-id: 2100328966
tags:
    - Physics
    - Quantum Field Theory
---

## Anderson-Higgs Mechanism

在上一篇文章中，我们讨论了自发破缺的整体对称性与描述产生相应 NG 粒子的 Goldstone 定理。其中，我们提到了“局域对称性”不得自发破缺的结论。然而，广为人知地，标准模型的电弱统一理论经常被描述为通过所谓的“自发规范对称性破缺”（即 Anderson-Higgs 机制）为玻色子和费米子赋予质量。事实上，这一说法多少有一些误导。Anderson-Higgs 机制实际上并没有（依 Elitzur 定理，也不能）破缺定域的规范对称性，其本质是取定规范并破缺了相应的整体对称性。在本篇文章中，我们便来简短地讨论一下这个问题。

作为例子，考虑我们最熟悉的 $U(1)$ 规范对称性（QED）作用量：

$$
    S=\int\mathrm{d}^4x\left\{-|D_\mu\phi|^2-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-V(\phi)\right\}
$$

其中标量场相互作用为：

$$
    V(\phi)=-\mu^2\phi^*\phi+\lambda(\phi^*\phi)^2
$$

协变导数为：

$$
    D_\mu=\partial_\mu+\mathrm{i}eA_\mu\ .
$$

我们说该理论具有 $U(1)$ 规范对称性，是指作用量在如下变换下不发生改变：

$$
    \phi(x)\rightarrow\phi(x)\mathrm{e}^{\mathrm{i}\alpha(x)},\quad A_\mu(x)\rightarrow A_\mu(x)-\frac{1}{e}\partial_\mu\alpha(x)\ .
$$

接下来考虑自发破缺的**整体** $U(1)$ 对称性，一如我们在处理 Goldstone 粒子时的操作一样，将标量场重写为极坐标形式（分离破缺方向与未破缺方向）：

$$
    \phi(x)=\frac{1}{\sqrt{2}}\mathrm{e}^{\mathrm{i}\xi(x)}(v+\sigma(x))
$$

其中 $v=\sqrt{\mu^2/\lambda}$ 是标量场的 VEV.

将其带入 Lagrangian 并化简，有：

$$
\begin{aligned}
    \mathscr{L}&=-\frac{1}{2}\partial_\mu\sigma\partial^\mu\sigma-\frac{1}{2}\left(2\lambda v^2\right)\sigma^2-\frac{1}{2}e^2(v+\sigma(x))^2\left(A_\mu+\frac{1}{e}\partial_\mu\xi\right)^2
    \\&-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\lambda v\sigma^3-\frac{1}{4}\lambda\sigma^4+\frac{1}{4}\lambda v^4\ .
\end{aligned}
$$

注意到，此时的 Lagrangian **仍旧是规范不变的**，因为此时规范变换变为了：

$$
    \xi(x)\rightarrow\xi(x)+\alpha(x),\quad A_\mu(x)\rightarrow A_\mu(x)-\frac{1}{e}\partial_\mu\alpha(x)\ .
$$

我们称其为规范变换的一个**非线性实现**，于是 Lagrangian 显然规范不变[^1]。然而，我们知道所谓 Anderson-Higgs 机制描述的实际上是 NG 粒子被规范场吸收提供了纵向极化态的过程。因此接下来我们要**取定规范**：

$$
    A'_\mu=A_\mu+\frac{1}{e}\partial_\mu\xi
$$

直到这一步，我们才相当于定下了系统的规范（此时从根本上来讲理论仍旧仍旧是规范不变的，但取定这个规范之后原初的 $\mathrm{U}(1)$ 变换对所有剩下的场完全没有任何效果）。从此处可以看到，Higgs 机制**并不是一个自发对称性破缺的过程**，其只是将线性的规范变换隐藏起来，以非线性的方式实现了。没有任何序参量描述规范对称性的消失。

在取定规范后，我们有：

$$
\begin{aligned}
    \mathscr{L}&=-\frac{1}{2}\partial_\mu\sigma\partial^\mu\sigma-\frac{1}{2}\left(2\lambda v^2\right)\sigma^2-\frac{1}{2}e^2(v+\sigma(x))^2A'_\mu A'^\mu
    \\&-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\lambda v\sigma^3-\frac{1}{4}\lambda\sigma^4+\frac{1}{4}\lambda v^4
\end{aligned}
$$

此时，我们会发现，矢量场 `$A'_\mu$` 获得了第三个自由度，并获得了一个大小为 $ev$ 的质量。而获得质量 $2\lambda v^2$ 的标量场 $\sigma$，便是我们所知的 Higgs 粒子。

## Electroweak Theory[^2]

我们当然要展示一下 Anderson-Higgs 机制最为著名的应用（或许也是人类目前为止最为成功的理论），电弱理论标准模型的 `$\mathrm{SU(2)\times U(1)}\rightarrow\mathrm{U(1)}$` 过程。

### 规范群的确定

首先，实验告诉我们，弱相互作用对物质场的效果是手征的。为此，我们先构建轻子部分。首先是电子型轻子：

$$
    e_L=\frac{1}{2}(1+\gamma_5)e,\:e_R=\frac{1}{2}(1-\gamma_5)e
$$

其次是电子中微子型轻子[^3]：

$$
    \gamma_5\nu_{eL}=\nu_{eL}
$$

弱相互作用只与左手场耦合，因此我们简单地假设规范群为：

$$
    \mathrm{SU}(2)_L\otimes\mathrm{U}(1)_L\otimes\mathrm{U}(1)_R
$$

于是场的变换为：

$$
    \delta
    \begin{pmatrix}
        \nu_e
        \\e
    \end{pmatrix}
    =\mathrm{i}[\epsilon_i t^i+\epsilon_L t_L+\epsilon_R t_R]
    \begin{pmatrix}
        \nu_e
        \\e
    \end{pmatrix}
$$

其中我们分别有：

$$
    \boldsymbol{t}=\frac{g}{4}(1+\gamma_5)
        \left\{
            \begin{pmatrix}
                0 & 1
                \\1 & 0
            \end{pmatrix}
            ,
            \begin{pmatrix}
                0 & -\mathrm{i}
                \\\mathrm{i} & 0
            \end{pmatrix}
            ,
            \begin{pmatrix}
                1 & 0
                \\0 & -1
            \end{pmatrix}
        \right\}
$$

称为**弱同位旋（Weak Isospin）**，以及：

$$
    t_L\propto(1+\gamma_5)
    \begin{pmatrix}
        1 & 0
        \\0 & 1
    \end{pmatrix},\:t_R\propto(1-\gamma_5)
$$

出于理论和实验的相符性，我们不使用 `$t_L,\:t_R$` 而使用如下两个生成元：

$$
\begin{aligned}
    y&=g'\left[\left(\frac{1+\gamma_5}{4}\right)
    \begin{pmatrix}
        1 & 0
        \\0 & 1
    \end{pmatrix}+\left(\frac{1-\gamma_5}{2}\right)\right]
    \\n_e&=g''\left[\left(\frac{1+\gamma_5}{2}\right)
    \begin{pmatrix}
        1 & 0
        \\0 & 1
    \end{pmatrix}+\left(\frac{1-\gamma_5}{2}\right)\right]
\end{aligned}
$$

其中第一个称为**超荷（Hypercharge）**，第二个则显然正是轻子数。

我们在这里讨论一下上述这些生成元和我们熟悉的电荷的关系。容易看到，右手电子 $e_R$ 携带的超荷比左手电子中微子和左手电子 $\nu_{eL},e_L$ 多 $1/2$；而左手电子的弱同位旋第三分量又比右手电子多 $1/2$. 我们又知道，电子不论左右手，携带的电荷是一样的，因此我们构造电荷：

$$
    q=\frac{e}{g}t_3-\frac{e}{g'}y
    =g_e\begin{pmatrix}
        0 & 0
        \\0 & -1
    \end{pmatrix}
$$

可以验证这至少满足了电子携带电荷量的要求。同时，这样的构造为我们接下来获取规范破缺方向提供了一个小小的提示。

### 规范场部分

理论上我们应当为这四个生成元都引入对应的规范场，但实验中并未观测到轻子数对应的规范场。因此我们去掉 $n_e$，便获得了电弱理论的规范群：

$$
    \mathrm{SU}(2)_{L}\otimes \mathrm{U}(1)_Y
$$

于是我们写下两个规范矢量场的 Lagrangain：

$$
    \mathscr{L}_{gauge}=-\frac{1}{4}W_{a\mu\nu}W^{a\mu\nu}-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}
$$

其中 `$W^a_{\mu\nu}$` 是 `$\mathrm{SU}(2)_{L}$` 的伴随表示下的规范场张量，对应于弱同位旋，定义为：

$$
    W^a_{\mu\nu}=\partial_{\mu}A^a_{\nu}-\partial_{\nu}A^{a}_{\mu}+g\varepsilon_{abc}A^{b}_{\mu}A^{c}_{\nu}
$$

而 `$F_{\mu\nu}$` 是 `$\mathrm{U}(1)_Y$` 超场，对应于 $Y$ 超荷，定义为我们最熟悉的：

$$
    F_{\mu\nu}=\partial_{\mu}B_{\nu}-\partial_{\nu}B_{\mu}
$$

这二者便是规范群 `$\mathrm{SU}(2)_{L}\otimes U(1)_Y$` 对应的规范场。

实验告诉我们，电弱理论应该有一个自旋为 1 且有质量的带电荷粒子 `$W^{\pm}$`，自旋为 1 且有质量的中性粒子 `$Z^0$`，以及自旋为一且无质量的中性粒子 `$\gamma$`，也就是光子. 基于前面的讨论，我们知道 `$\gamma$` 应当由 `$A_3$` 与 `$B$`组合而成，因此我们分别构造如下四个场：

$$
\begin{aligned}
    W^{\mu}&=\frac{1}{\sqrt{2}}(A^{\mu}_1+\mathrm{i}A^{\mu}_2)
    \\W^{\mu*}&=\frac{1}{\sqrt{2}}(A^{\mu}_1-\mathrm{i}A^{\mu}_2)
    \\Z^{\mu}&=\cos{\theta}A_3^{\mu}+\sin{\theta}B^{\mu}
    \\A^{\mu}&=-sin{\theta}A_3^{\mu}+\cos{\theta}B^{\mu}
\end{aligned}
$$

其中 $\theta$ 称为 Weinberg 角，表征了 `$\mathrm{SU}(2)_L$` 与 `$\mathrm{U}(1)_Y$` 的混合程度。

为了之后的计算方便，我们反解出 $\boldsymbol{A}$ 和 $B$：

$$
\begin{aligned}
    A_1&=\frac{1}{\sqrt{2}}(W+W^*)
    \\A_2&=\frac{1}{\sqrt{2}\mathrm{i}}(W-W^*)
    \\A_3&=Z\cos{\theta}-A\sin{\theta}
    \\B&=Z\sin{\theta}+A\cos{\theta}
\end{aligned}
$$

### 轻子场部分

接下来我们考虑构造规范不变的轻子场 Lagrangian. 轻子场的动力学项是简单的：只是将导数换成协变导数，即有：

$$
    \mathscr{L}_e=-\bar{l}(\gamma^\mu\partial_\mu-\mathrm{i}\gamma^\mu\boldsymbol{A}_\mu\cdot\boldsymbol{t}-\mathrm{i}\gamma^\mu B_\mu y)l
$$

然而轻子的质量项则成为了大麻烦。首先，我们看到不论是电子型轻子还是左手电子中微子型轻子，都至少携带一种内部对称性对应的守恒荷，因此其都应当是 Dirac 费米子[^4][^5]。然而，在我们讨论自发对称性破缺赋予质量之前，轻子到底是什么类型的费米子其实并没有意义（因为 Dirac 和 Majorana 之分别仅在质量项上）。通常的 Dirac 质量项不能被我们在这里引入进来，因为我们讨论的弱相互作用是手性的，而 Dirac 质量项在手性规范对称群下显然不是一个规范单态。但显然地，现实中的轻子都有质量。因此我们希望自发对称性破缺机制也可以合理地为轻子引入质量，为此引入 Higgs 和轻子场的 Yukawa 耦合：

$$
    \mathscr{L}_{\phi e}=-G_e\overline{
        \begin{pmatrix}
            \nu_e\\
            e
        \end{pmatrix}
    }_L
        \begin{pmatrix}
            \phi^+\\
            \phi^0
        \end{pmatrix}e_R+h.c.
$$

其中我们定义 $(\phi^+,\phi^0)$ 双重态的变换生成元为：

$$
    \boldsymbol{t}^{(\phi)}=\frac{g}{2}
    \left\{
        \begin{pmatrix}
            0 & 1
            \\1 & 0
        \end{pmatrix}
        ,
        \begin{pmatrix}
            0 & -\mathrm{i}
            \\\mathrm{i} & 0
        \end{pmatrix}
        ,
        \begin{pmatrix}
            1 & 0
            \\0 & -1
        \end{pmatrix}
    \right\}
$$

以及 `$\mathrm{U}(1)_Y$` 生成元：

$$
    y^{(\phi)}=-\frac{g'}{2}
        \begin{pmatrix}
            1 & 0\\
            0 & 1
        \end{pmatrix}
$$

于是容易看到上述构造的 Yukawa 耦合在 $\mathrm{SU}(2)_L\otimes\mathrm{U}(1)_Y$ 下不变。（$t_3:-1/2+1/2=0,\:y:-1/2-1/2+1=0$.）

于是可以看出 Higgs 的电荷矩阵为：

$$
    q=\frac{e}{g}t_3-\frac{e}{g'}y
    =g_e\begin{pmatrix}
        1 & 0
        \\0 & 0
    \end{pmatrix}
$$

### 电弱标准模型的拉格朗日量

Higgs 的动力学项也需要替换为协变导数，并且 Landau-Ginzburg 势当然也是 SSB 必不可少的。

于是我们至此可以写出 Lagrangian：

$$
\begin{aligned}
    \mathscr{L}_{ElectroWeak}=&-\frac{1}{4}W_{a\mu\nu}W^{a\mu\nu}-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\bar{l}(\gamma^\mu\partial_\mu-\mathrm{i}\gamma^\mu\boldsymbol{A}_\mu\cdot\boldsymbol{t}-\mathrm{i}\gamma^\mu B_\mu y)l\\&-\frac{1}{2}\left|(\partial_\mu-\mathrm{i}\boldsymbol{A}_\mu\cdot\boldsymbol{t}-\mathrm{i}B_\mu y)\phi\right|^2-\frac{\mu^2}{2}\phi^{\dagger}\phi-\frac{\lambda}{4}(\phi^\dagger\phi)^2-G_e\overline{\left(P_L l\right)}\phi P_Rl+h.c.
\end{aligned}
$$

其中 $P_L$ 和 $P_R$ 分别是获取对应手征分量的投影算符。我们在标量场部分添加了 $1/2$ 的系数，这是因为在经历 SSB 之后，标量场只会剩下一个分量作为物理自由度，在这里添加 $1/2$ 才能使这个物理场是正则归一化的。

### 自发对称性破缺

接下来我们来探讨该理论的 SSB 过程，并展示其将为规范玻色子与轻子分别赋予质量。

出于理论的直观完整性，我们先将轻子-规范耦合拆开成 $A、Z、W$ 的形式：

$$
    i\mathscr{L}_e'=-\bar{l}\gamma^\mu A_{\mu}^{a}t_al
$$

将之前的表达式带入化简，有：

$$
\begin{aligned}
    i\mathscr{L}_e'=&\frac{g}{\sqrt{2}}\left(\bar{e}\gamma^\mu W_\mu P_L\nu_e\right)+\frac{g}{\sqrt{2}}\left(\bar{\nu_e}\gamma^\mu W_\mu^*P_Le\right)
    \\&-\frac{1}{2}\sqrt{g^2+g'^2}\bar{\nu_e}\gamma^\mu Z_\mu P_L\nu_e+\frac{(g^2-g'^2)}{2\sqrt{g^2+g'^2}}\bar{e}\gamma^\mu Z_\mu P_L e
    \\&+g'\bar{e}\gamma^\mu Z_\mu P_Re-g_e(\bar{e}\gamma^\mu A_\mu e)
\end{aligned}
$$

现在回来关注 Higgs 场。当参量 $\mu^2<0$ 时，我们可以给出 Landau-Ginzburg 势下的 Higgs 真空期望值：

$$
    \langle\phi^\dagger\rangle\langle\phi\rangle\equiv v^2=\frac{|\mu^2|}{\lambda}
$$

我们总可以取一个规范变换（无非就是转转角度）使得 Higgs 场达到所谓的幺正规范，即 $\phi^+=0$ 而 $\phi^0$ 厄米。于是有：

$$
    \langle\phi^+\rangle=0,\:\langle\phi^0\rangle=v
$$

由此 Higgs 的动力学项中规范联络部分给出了 $W$ 和 $Z$ 的质量：

$$
    -\frac{1}{2}\left|(\boldsymbol{A}_\mu\cdot\boldsymbol{t}+B_\mu y)\langle\phi\rangle\right|^2=-\frac{1}{4}g^2v^2W^{\dagger}_{\mu}W^{\mu}-\frac{1}{8}(g^2+g'^2)v^2Z_\mu Z^\mu
$$

可以看到其中刚好没有 $A_\mu$ 的质量项，这保证了光子仍旧零质量，并且我们有：

$$
    m_W=|g|v,\quad m_Z=\frac{1}{2}\sqrt{g^2+g'^2}v
$$

此外，Yukawa 耦合也给出了电子的质量：

$$
    m_e=vG_e
$$

由此，我们成功地通过自发对称性破缺机制赋予了弱规范玻色子与轻子合适的质量，并给出了轻子-规范玻色子之间的电弱相互作用。以上内容即是著名的 **Glashow–Weinberg–Salam 电弱标准模型**，其被 Sheldon Lee Glashow 于 1961 年，Mohammad Abdus Salam 于 1964 年，Steven Weinberg 于 1967 年分别独立提出、完善，并为他们赢得了 1979 年的诺贝尔物理学奖。Higgs 与规范玻色子之间的相互作用也可以通过对 Lagrangian 的进一步展开获得，我们在此不再详述。

----

[^1]: 这里的规范对称性实际上有很大的作用。如果我们尝试对接下来取了幺正规范的理论进行量子化，我们会发现这种规范下的传播子的性质导致我们无法使用幂次计数讨论理论的可重整性。然而，基于理论仍旧保有的规范不变性，我们只要切换到一个其他的规范（例如，'t Hooft 给出的所谓可重整 $\xi$ 规范），就可以证明理论的实际可重整性（代价是无法明显地看出哪些场是物理实在的粒子）；而又由于规范不变性，我们只要在一个理论下证明了其可重整性，就可以在所有规范下放心的进行讨论。
[^2]: *The Quantum Theory of Fields, Vol.II, Chapter 21*, Steven Weinberg
[^3]: 目前我们尚未发现右手中微子，如果需要的话可以在模型里补入。
[^4]: 这个想法其实是很 naive 的（不然也不会有关于中微子是否是 Majorana 粒子的问题了），这里有很多细节上的问题。首先，对于 $\mathrm{SU}(2)$ 的基本表示（是一个 pseudo-real 表示），最普通的手征 Weyl 费米子 Majorana 质量项其实确实是一个规范单态，因而不被规范对称性禁止；然而，由于 $\mathrm{SU}(2)$ 基本表示的 pseudo-real 性质（“度规”反对称），这样的项其实恒为零。
[^5]: 但是，我们可以构造一个 dimension 5 的单态算符，称为 “Weinberg Operator” $\propto\bar{l}\tilde{H}\tilde{H}l^c$，其保证了在保持规范对称性的情况下实现中微子的 Majorana 质量项（这其实是因为在低能下弱同位旋对称性的破缺，我们根本看不到 weak isospin 荷。）顺便，我们还可以利用所谓的 seesaw 机制给出 Weinberg Operator 的高能可重整实现，这玩意儿还挺好玩的，但我们在此不多赘述。
