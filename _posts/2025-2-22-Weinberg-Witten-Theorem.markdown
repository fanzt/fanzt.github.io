---
layout:     post
title:      "A note about Weinberg-Witten Theorem"
subtitle:   "Simple but beautiful result."
date:       2025-01-22 09:00:00
author:     "fromuly"
header-img: "img/post-bg-2025-1.jpg"
catalog: true
usemathjax: true
music-id: 2141328400
tags:
    - Physics
    - Quantum Field Theory
    - Paper note
---

> *读点东西，写点东西。*
>
> <https://inspirehep.net/literature/154422>
> DOI: 10.1016/0370-2693(80)90212-9
> *Limits on Massless Particles*
> Steven Weinberg, Edward Witten,
> Phys.Lett.B 96 (1980) 59-62

## Weinberg-Witten 定理

**Theorem 1**：一个能够构造出 Lorentz 协变的四矢守恒流 `$J^\mu$` 的理论不能够包含任何无质量、带对应非零守恒荷 `$Q=\int J^0\:\mathrm{d}^3x$` 且自旋 `$j>1/2$` 的粒子。

**Theorem 2**：一个能够构造出守恒且 Lorentz 协变的能动张量 `$T^{\mu\nu}$` 并且满足 `$\int T^{0\nu}\:\mathrm{d}^3x$` 是四动量矢量的理论不得包含无质量且自旋 `$j>1$` 的粒子。

证明如下。

*这个证明其实十分简单，很惊讶于如此简单的证明可以给出如此强的限制。*

我们从定理所叙述的守恒流/能动张量的矩阵元开始讨论，这样的矩阵元描述了定理叙述的粒子和与它耦合的场的在壳相互作用顶点，因而是我们可以用散射过程进行探测的。考虑单粒子态 `$|{p,\pm j}\rangle$`，其满足：

$$
\begin{aligned}
    Q|{p,\pm j}\rangle&=q|{p,\pm j}\rangle,\quad q\neq 0;
    \\ P^{\mu}|{p,\pm j}\rangle&=p^{\mu}|{p,\pm j}\rangle,\quad p^{\mu}\neq 0;
\end{aligned}
$$

考察守恒流与能动张量在这样的单粒子态下的矩阵元：

$$
\begin{aligned}
    \langle{p',\pm j}|&J^{\mu}(x)|{p,\pm j}\rangle=\exp[\mathrm{i}(p-p')\cdot x]\langle{p',\pm j}|J^{\mu}(0)|{p,\pm j}\rangle
    \\\langle{p',\pm j}|&T^{\mu\nu}(x)|{p,\pm j}\rangle=\exp[\mathrm{i}(p-p')\cdot x]\langle{p',\pm j}|T^{\mu\nu}(0)|{p,\pm j}\rangle
\end{aligned}
$$

将 $J^{\mu}(0)$ 和 $T^{\mu\nu}(0)$ 简记为 $J^{\mu}$ 和 $T^{\mu\nu}$，基于 Lorentz 不变性，我们有：

$$
\begin{aligned}
    \langle{p',\pm j}|J^{\mu}|{p,\pm j}\rangle&=\langle{p',\pm j}|U^{\dagger}(\Lambda)U(\Lambda)J^{\mu}U^{\dagger}(\Lambda)U(\Lambda)|{p,\pm j}\rangle
    \\&={(\Lambda^{-1})^{\mu}}_{\rho}\langle{p',\pm j}|U^{\dagger}(\Lambda)J^{\rho}U(\Lambda)|{p,\pm j}\rangle
    \\&=\sqrt{\frac{\Lambda p'^0}{p'^0}}\sqrt{\frac{\Lambda p^0}{p^0}}\mathrm{e}^{-\mathrm{i}\cdot(\pm j) [\theta(\Lambda,p')-\theta(\Lambda,p)]}{(\Lambda^{-1})^{\mu}}_{\rho}\langle{\Lambda p',\pm j}|J^{\rho}|{\Lambda p,\pm j}\rangle
\end{aligned}
$$

同理有：

$$
    \langle{p',\pm j}|T^{\mu\nu}|{p,\pm j}\rangle=\sqrt{\frac{\Lambda p'^0}{p'^0}}\sqrt{\frac{\Lambda p^0}{p^0}}\mathrm{e}^{-\mathrm{i}\cdot(\pm j) [\theta(\Lambda,p')-\theta(\Lambda,p)]}{(\Lambda^{-1})^{\mu}}_{\rho}{(\Lambda^{-1})^{\nu}}_{\sigma}\langle{\Lambda p',\pm j}|T^{\rho\sigma}|{\Lambda p,\pm j}\rangle
$$

记：

$$
\begin{aligned}
    \tilde{J}^{\mu}(p',p)&=\sqrt{p'^0p^0}\langle{p',\pm j}|J^{\mu}|{p,\pm j}\rangle
    \\\tilde{T}^{\mu\nu}(p',p)&=\sqrt{p'^0p^0}\langle{p',\pm j}|T^{\mu\nu}|{p,\pm j}\rangle
\end{aligned}
$$

则 Lorentz 不变性告诉我们当 $p'\rightarrow p$ 时：

$$
    {\Lambda^{\mu}}_{\rho}\tilde{J}^{\rho}(p)=\tilde{J}^{\mu}(\Lambda p),\:{\Lambda^{\mu}}_{\rho}{\Lambda^{\nu}}_{\sigma}\tilde{T}^{\rho\sigma}(p)=\tilde{T}^{\mu\nu}(\Lambda p)
$$

于是我们自然有：

$$
    \tilde{J}^{\mu}(p)=\alpha p^{\mu},\:T^{\mu\nu}=\beta p^{\mu}p^{\nu}
$$

即：

$$
    \langle{p',\pm j}|J^{\mu}|{p,\pm j}\rangle\rightarrow\alpha\frac{p^\mu}{p^0},\:\langle{p',\pm j}|T^{\mu\nu}|{p,\pm j}\rangle\rightarrow\beta\frac{p^{\mu}p^{\nu}}{p^0}
$$

再考虑到当 $p'\rightarrow p$ 时：

$$
    \langle{p',\pm j}|\int\mathrm{d}^3x\:J^{0}(x)|{p,\pm j}\rangle=q\delta^3(\mathbf{p}'-\mathbf{p})=(2\pi)^3\delta^3(\mathbf{p}'-\mathbf{p})\alpha
$$

以及：

$$
    \langle{p',\pm j}|\int\mathrm{d}^3x\:T^{0\nu}(x)|{p,\pm j}\rangle=p^{\nu}\delta^3(\mathbf{p}'-\mathbf{p})=(2\pi)^3\delta^3(\mathbf{p}'-\mathbf{p})\beta p^{\nu}
$$

我们可以得到：

$$
    \alpha=\frac{q}{(2\pi)^3},\:\beta=\frac{1}{(2\pi)^3}
$$

即：对于 $p'\rightarrow p$ 的情况，我们有：

$$
\begin{aligned}
    \langle{p',\pm j}|J^{\mu}|{p,\pm j}\rangle&\rightarrow\frac{q}{(2\pi)^3}\frac{p^\mu}{p^0}
    \\\langle{p',\pm j}|T^{\mu\nu}|{p,\pm j}\rangle&\rightarrow\frac{1}{(2\pi)^3}\frac{p^{\mu}p^{\nu}}{p^0}
\end{aligned}
$$

这表示当 $p'\rightarrow p$ 时我们考虑的两个矩阵元都不趋向零。

接下来我们再考虑对于高自旋情况会出现的一个问题，这个问题将会给出定理中对高自旋的限制。既然是对自旋的限制，我们便来考虑旋转变换作用在该矩阵元上的结果。

首先我们选取两个特殊的动量，分别为：

$$
    p=(|\mathbf{p}|,\mathbf{p}),\:p'=(|\mathbf{p}|,-\mathbf{p})
$$

对于任意的 $(p'-p)^2\neq 0$（包括我们上式所论证的 $p'\rightarrow p$），这总是可以取到的，因为此时我们总有：

$$
    (p+p')^2=2p\cdot p'=2|\mathbf{p}||\mathbf{p}'|(\cos{\theta}-1)<0
$$

即 $p+p'$ 是类时的，因此我们总可以取一个 Lorentz 变换使得其没有空间分量。对于这样的两个动量，我们考察绕 $\mathbf{p}$ 轴的旋转变换作用 $R=R(\theta)$ 在单粒子态上的效果：

$$
\begin{aligned}
    U(R)|{p,\pm j}\rangle&=\exp(\pm \mathrm{i}\theta j)|{p,\pm j}\rangle
    \\U(R)|{p',\pm j}\rangle&=\exp(\mp \mathrm{i}\theta j)|{p',\pm j}\rangle
\end{aligned}
$$

这意味着：

$$
\begin{aligned}
    \langle{p',\pm j}|J^{\mu}|{p,\pm j}\rangle&=\langle{p',\pm j}|U^{\dagger}(R)U(R)J^{\mu}U^{\dagger}(R)U(R)|{p,\pm j}\rangle
    \\&={(R^{-1})^{\mu}}_{\rho}\exp(\pm 2\mathrm{i}\theta j)\langle{p',\pm j}|J^{\rho}|{p,\pm j}\rangle
\end{aligned}
$$

以及同理：

$$
\begin{aligned}
    \langle{p',\pm j}|T^{\mu\nu}|{p,\pm j}\rangle&=\langle{p',\pm j}|U^{\dagger}(R)U(R)T^{\mu\nu}U^{\dagger}(R)U(R)|{p,\pm j}\rangle
    \\&={(R^{-1})^{\mu}}_{\rho}{(R^{-1})^{\nu}}_{\sigma}\exp(\pm 2\mathrm{i}\theta j)\langle{p',\pm j}|T^{\rho\sigma}|{p,\pm j}\rangle
\end{aligned}
$$

亦即：

$$
\begin{aligned}
    {R^{\mu}}_{\nu}\langle{p',\pm j}|J^{\nu}|{p,\pm j}\rangle&=\exp(\pm 2\mathrm{i}\theta j)\langle{p',\pm j}|J^{\mu}|{p,\pm j}\rangle
    \\{R^{\mu}}_{\rho}{R^{\nu}}_{\sigma}\langle{p',\pm j}|T^{\rho\sigma}|{p,\pm j}\rangle&=\exp(\pm 2\mathrm{i}\theta j)\langle{p',\pm j}|T^{\mu\nu}|{p,\pm j}\rangle
\end{aligned}
$$

然而我们知道，三维旋转矩阵能且只能由 $\mathrm{e}^{\mathrm{i}\theta}$，$1$ 和 $\mathrm{e}^{-\mathrm{i}\theta}$ 组成。这就意味着，对于第一种情形，我们总是有 $j\leq 1/2$，对于第二种情形我们总是有 $j\leq 1$，此外的所有情况则必须要求我们考虑的矩阵元为零。考虑到又由于无质量粒子的螺旋度不随 Lorentz 变换而改变，且守恒流与能动张量都是 Lorentz 协变的，这意味着我们的结论在任意一个参考系中都成立。

综合两部分讨论，我们可以看到：第一部分的讨论告诉我们一个无质量粒子在 $p'\rightarrow p$ 时，我们考虑的矩阵元不会趋于零（不论其自旋究竟是多少）；第二部分的讨论却告诉我们如果这个粒子自旋过高，其在任意的 $(p'-p)^2\neq 0$ 的情况下都会等于零。二者的矛盾意味着，或者这样的高自旋单粒子态不存在，或者这样的守恒流/能动张量不存在，或者对于守恒流来说，荷 $q$ 不存在。因此定理得证。

我们可以对这个结果进行一些讨论。

首先，这个证明过程并没有对理论的基本性做出任何假设，我们并不要求单粒子态一定是基本粒子（即出现在 Lagrangian 中的那些场），这意味着复合粒子（只要可以被一个单粒子态描述）同样要遵循这个定理。这个证明过程也没有对理论的可重整性做出任何假设，也不是从任何微扰论的角度去讨论的，其本身是一个完全的非微扰结论。

从正面应用来说，这个结论否定了引力子作为两个矢量玻色子组合的无质量束缚态粒子的可能性，因为这种情况下我们可以构造出协变的 Belinfante 张量（也就自然存在能动张量），而这是不被该定理所允许的。

其次，定理的结论十分有力，但众所周知光子和胶子都是无质量的 1 自旋粒子，并且可能地，引力子大概应当是无质量 2 自旋粒子。所以，重要的是，这些例子是如何绕过定理的限制的。

对于光子有一个很显然的结论：它不带荷，所以我们讨论出的 $q$ 直接等于零，因而其成功绕过了定理的限制。然而，这个路径对胶子是不成立的，因为其携带色荷。但胶子（包括光子）仍然可以基于另一角度绕过定理的限制：它们都是规范场。规范场不是真正的 Lorentz 协变场，其 Lorentz 变换会额外附带一个规范项。这意味着，它们构成的规范守恒流，根本不是 Lorentz 协变的守恒流。同理，这也为引力场绕过该限制提供了方案。弱引力场情形下 $h_{\mu\nu}$ 的广义坐标变换不变性同样被视为一种规范对称性，所以我们对它构建起的能动赝张量同样不是真实的 Lorentz 协变张量。

说起来，这种思想是否在凝聚态场论中适用呢？在那里我们似乎更加不需要在意 Lorentz 协变性，这是否意味着我们可以在凝聚态体系中构建出多种多样的高自旋无质量的带荷粒子？

不太清楚。