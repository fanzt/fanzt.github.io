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

于是 Lagrangian 显然规范不变。然而，我们知道所谓 Anderson-Higgs 机制描述的实际上是 NG 粒子被规范场吸收提供了纵向极化态的过程。因此接下来我们要**取定规范**：

$$
    A'_\mu=A_\mu+\frac{1}{e}\partial_\mu\xi
$$

直到这一步，我们才相当于移除了系统的规范对称性。从此处可以看到，规范对称性的消失**并不是一个自发对称性破缺的过程**。没有任何序参量描述规范对称性的消失。

在取定规范后，我们有：

$$
\begin{aligned}
    \mathscr{L}&=-\frac{1}{2}\partial_\mu\sigma\partial^\mu\sigma-\frac{1}{2}\left(2\lambda v^2\right)\sigma^2-\frac{1}{2}e^2(v+\sigma(x))^2A'_\mu A'^\mu
    \\&-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\lambda v\sigma^3-\frac{1}{4}\lambda\sigma^4+\frac{1}{4}\lambda v^4
\end{aligned}
$$

此时，我们会发现，矢量场 `$A'_\mu$` 获得了第三个自由度，并获得了一个大小为 $ev$ 的质量。而获得质量 $2\lambda v^2$ 的标量场 $\sigma$，便是我们所知的 Higgs 粒子。

## Electroweak Theory[^1]

我们当然要展示一下 Anderson-Higgs 机制最为著名的应用（或许也是人类目前为止最为成功的理论），电弱理论标准模型的 `$\mathrm{SU(2)\times U(1)}\rightarrow\mathrm{U(1)}$` 过程。

### 规范群的确定

首先，实验告诉我们，弱相互作用对物质场的效果是手征的。为此，我们先构建轻子部分。首先是电子型轻子：

$$
    e_L=\frac{1}{2}(1+\gamma_5)e,\:e_R=\frac{1}{2}(1-\gamma_5)e
$$

其次是电子中微子型轻子[^2]：

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
    =e\begin{pmatrix}
        0 & 0
        \\0 & -1
    \end{pmatrix}
$$

可以验证这至少满足了电子携带电荷量的要求。同时，这样的构造为我们接下来获取规范破缺方向提供了一个小小的提示。

### 规范场部分

理论上我们应当为这四个生成元都引入对应的规范场，但实验中并未观测到轻子数对应的规范场。因此我们去掉 $n_e$，便获得了电弱理论的规范群：

$$
    \mathrm{SU}(2)_{L}\otimes U(1)_Y
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

实验告诉我们电弱理论中有且仅有一个无质量的规范玻色子，也就是光子。因此接下来我们考虑如何将这个所谓的 `$\mathrm{SU}(2)_{L}\otimes U(1)_Y$` 规范作用量破缺到只剩下一个 `$\mathrm{U}(1)_{EM}$` 的作用量。为此，我们需要考虑这些规范场的线性组合（也就是这些李代数的线性组合）。

实验告诉我们，电弱理论应该有一个自旋为 1 且有质量的带电荷粒子 `$W^{\pm}$`，自旋为 1 且有质量的中性粒子 `$Z^0$`，以及自旋为一且无质量的中性粒子 `$\gamma$`. 基于前面的讨论，我们知道 `$\gamma$` 应当由 `$A_3$` 与 `$B$`组合而成，因此我们分别构造如下四个场：

$$
\begin{aligned}
    W^{\mu}&=\frac{1}{\sqrt{2}}(A^{\mu}_1+iA^{\mu}_2)
    \\W^{\mu*}&=\frac{1}{\sqrt{2}}(A^{\mu}_1-iA^{\mu}_2)
    \\Z^{\mu}&=\cos{\theta}A_3^{\mu}+\sin{\theta}B^{\mu}
    \\A^{\mu}&=-sin{\theta}A_3^{\mu}+\cos{\theta}B^{\mu}
\end{aligned}
$$

其中 $\theta$ 称为 Weinberg 角，表征了 `$\mathrm{SU}(2)_L$` 与 `$\mathrm{U}(1)_Y$` 的混合程度。

### 轻子场部分

接下来我们考虑构造规范不变的轻子场 Lagrangian. 首先，我们看到不论是电子型轻子还是左手电子中微子型轻子，都至少携带一种内部对称性对应的守恒荷，因此其都应当是 Dirac 费米子[^3][^4]。

----

[^1]: *The Quantum Theory of Fields, Vol.II, Chapter 21*, Steven Weinberg
[^2]: 目前我们尚未发现右手中微子，如果需要的话可以在模型里补入。
[^3]: 然而这个想法其实是有些 naive 的，我们可以构造一个 dimension 5 的 “Weinberg Operator” $\propto\bar{l}\tilde{H}\tilde{H}l^c$，其保证了在保持手征二重态的情况下实现中微子的 Majorana 质量项（这其实是因为在低能下弱同位旋对称性的破缺，我们根本看不到 weak isospin 荷。）
[^4]: 顺便，我们还可以利用所谓的 seesaw 机制给出 Weinberg Operator 的高能可重整实现，在此不多赘述。
