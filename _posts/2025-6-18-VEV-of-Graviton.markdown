---
layout:     post
title:      "Vacuum Energy of Gravitational Field"
subtitle:   "Calculating by Path Integral"
date:       2025-6-18 20:00:00
author:     "fromuly"
header-img: "img/post-bg-2025-10.jpg"
catalog: true
usemathjax: true
music-id: 1972447487
tags:
    - Physics
    - Quantum Field Theory
    - General Relativity
---

> 夏天又到了呀。

在之前的一篇推文 [[Vacuum Energy By Path Integral](https://fanzt.github.io/2025/03/01/Vacuum-Energy-By-Path-Integral/)] 中，我们讨论了如何利用路径积分的方法计算标量、旋量和矢量场的真空零点能。从现代的观点来看，这其实就是在计算自由场的一圈有效作用量。以场论的角度来说，描述引力场的广义相对论也不过只是一种特别的规范场。因此我们自然要问，可以用这种方法计算引力场的真空零点能吗？答案是可以的，至少在线性近似下是可以的。在本文中，我们就来介绍这个方法在引力场中的应用。

## Propagator of Linear Gravity

为了进行接下来的计算，我们首先要获得微扰展开下的线性引力论。考虑最简单的情况，我们将背景度规直接取为 平直的 Minkowski 度规，并执行微扰展开，于是有：

$$
    g_{\mu\nu}=\eta_{\mu\nu}+\kappa h_{\mu\nu}
$$

其中 `$h_{\mu\nu}$` 为微扰部分，`$\kappa=\sqrt{32\pi G_N}$` 为约化系数。相应的，度规的逆可以被展开为：

$$
    g^{\mu\nu}=\eta^{\mu\nu}-\kappa h^{\mu\nu}+\kappa^2 h^{\mu\alpha}{h_{\alpha}}^{\mu}
$$

广义相对论的 Einstein-Hilbert 作用量为：

$$
    S_{EH}=\int{\mathrm{d}^4x}\sqrt{-\det{g}}\frac{2}{\kappa^2}R
$$

其中 `$R=g^{\mu\beta}R_{\mu\beta}=g^{\mu\beta}R^{\nu}_{\mu\nu\beta}$` 为 Riemann 曲率标量。Riemann 曲率张量由下式给出：

$$
    R^{\nu}_{\mu\alpha\beta}=\Gamma^{\nu}_{\beta\mu,\alpha}-\Gamma^{\nu}_{\alpha\mu,\beta}+\Gamma^{\nu}_{\alpha\sigma}\Gamma^{\sigma}_{\beta\mu}-\Gamma^{\nu}_{\beta\sigma}\Gamma^{\sigma}_{\alpha\mu}
$$

其中 `$\Gamma^{\nu}_{\alpha\mu}$` 为与度规适配的联络系数，即 Christoffel 符号：

$$
    \Gamma^{\nu}_{\alpha\mu}=\frac{1}{2}g^{\nu\lambda}(g_{\mu\lambda,\alpha}+g_{\lambda\alpha,\mu}-g_{\alpha\mu,\lambda})
$$

将这些全部代入 Riemann 曲率标量的表达式，可以得到：

$$
\begin{aligned}
    R&=\partial_{\nu}(g^{\mu\beta}\Gamma^{\nu}_{\beta\mu})-\frac{1}{2}\partial^\mu(g^{\nu\lambda}\partial_{\mu}g_{\lambda\nu})-g_{\mu\lambda,\beta}g^{\beta\mu,\lambda}+\frac{1}{2}g_{\beta\mu,\nu}g^{\beta\mu,\nu}
    \\&+\frac{1}{4}(2g^{\nu\lambda}g_{\nu\lambda,\sigma}g^{\sigma\rho}g_{\mu\rho,\mu}-g^{\nu\lambda}g_{\nu\lambda,\sigma}g^{\beta\mu}g_{\beta\mu,\sigma})-\frac{1}{4}(2g_{\sigma\lambda,\mu}g^{\mu\sigma,\lambda}-g_{\mu\rho,\nu}g^{\mu\rho,\nu})
\end{aligned}
$$

注意到 `$\sqrt{-\det{g}}$` 对微扰展开也有如下贡献：

$$
    \sqrt{-\det{g}}=\sqrt{-\det{\eta}}\left(1+\frac{1}{2}h-\frac{1}{4}h_{\mu\nu}h^{\mu\nu}+\frac{1}{8}h^2\right)
$$

其中 `$h={h^{\mu}}_{\mu}$`. 将这些微扰展开带入到 E-H 作用量表达式中，并舍去所有的全导数项，我们可以获得直到二阶的线性化引力场的 Lagrangian [^1]（亦即 Fierz-Pauli Lagrangian）：

$$
    \mathscr{L}=h_{\lambda\mu,\lambda}h^{\beta\mu,\beta}-\frac{1}{2}h_{\beta\mu,\lambda}h^{\beta\mu,\lambda}-{h^{\nu,\beta}_{\:\:\nu}}h_{\mu\beta,\mu}+\frac{1}{2}\partial_{\lambda}h\partial^{\lambda}h
$$

为了获取传播子，我们引入广义 $\xi$ 规范：

$$
    \mathscr{L}_{GF}=-\frac{1}{\xi}G_{\mu}G^{\mu}
$$

其中规范固定函数取为谐和坐标条件：

$$
    G_{\mu}=\partial^{\nu}\left(h_{\mu\nu}-\frac{1}{2}\eta_{\mu\nu}h\right)
$$

于是可以写出含规范固定作用项之后的 Lagrangian：

$$
    \mathscr{L}'=\left(1-\frac{1}{\xi}\right)h_{\lambda\mu,\lambda}h^{\beta\mu,\beta}-\frac{1}{2}h_{\beta\mu,\lambda}h^{\beta\mu,\lambda}-\left(1-\frac{1}{\xi}\right)h^{\mu\lambda,\lambda}\partial_{\mu}h+\left(\frac{1}{2}-\frac{1}{4\xi}\right)\partial_{\lambda}h\partial^{\lambda}h
$$

提取出二次项的系数为：

$$
    \mathscr{D}^{\mu\nu,\rho\sigma}=-2\cdot\left[-\left(1-\frac{1}{\xi}\right)(p^{\mu}p^{\nu}\eta^{\rho\sigma}-p^{\nu}p^{\rho}\eta^{\mu\sigma})-\frac{1}{2}p^2\eta^{\mu\rho}\eta^{\nu\sigma}+\left(\frac{1}{2}-\frac{1}{4\xi}\right)p^2\eta^{\mu\nu}\eta^{\rho\sigma}\right]
$$

取逆可以获得传播子的表达式[^2]：

$$
    \mathscr{D}^{-1}_{\mu\nu,\rho\sigma}=\frac{1}{p^2-\mathrm{i}\varepsilon}\left\{\frac{1}{2}\left[(\eta_{\mu\rho}\eta_{\nu\sigma}+\eta_{\mu\sigma}\eta_{\nu\rho}-\eta_{\mu\nu}\eta_{\rho\sigma})-\frac{1-\xi}{p^2}(p_{\mu}p_{\sigma}\eta_{\nu\rho}+p_{\nu}p_{\sigma}\eta_{\mu\rho}+p_{\mu}p_{\rho}\eta_{\nu\sigma}+p_{\nu}p_{\rho}\eta_{\mu\sigma})\right]\right\}
$$

注意，这里 $\mathscr{D}$ 指标里的逗号只表示分割指标组，不表示导数。

（其实我们的目的并不是获得传播子，而是获得二次项的逆以计算积分。）

## Faddeev-Popov Ghost

为了获得鬼场的相应 Lagrangian, 我们需要考虑对度规的规范变换：

$$
    h_{\mu\nu}\rightarrow h_{\mu\nu}+\partial_{\mu}\varepsilon_{\nu}+\partial_{\nu}\varepsilon_{\mu}
$$

在该规范变换下，容易求得规范固定函数 `$G_{\mu}$` 的变化为：

$$
    \mathcal{M}_{\mu\nu}=\frac{\delta G^{\varepsilon}_{\mu}}{\delta\varepsilon^{\nu}}=+\eta_{\mu\nu}\partial^2
$$

于是自然有鬼场的 Lagrangian 项：

$$
    \mathscr{L}_{Ghost}=\bar{c}^{\mu}\partial^2c_{\mu}
$$

其中 `$\mathcal{M}_{\mu\nu}$` 也正是我们接下来计算真空能量所需要的二次型。

## Calculation of Vacuum Energy

做完了前置准备工作，我们便可以实际进行真空能量的计算了。整体的计算思路和方法其实与矢量场别无二致，考虑到接下来的计算过程实际其实很繁琐，在计算开始之前，通过一个简单的分析先给出预期的结果将会是十分有益的。

我们知道，对于任意的一个四维时空，度规的分量组成了一个对称的 $4\times 4$ 矩阵。这意味着从表观上来看，度规张量场至少有 $4\times 4-6=10$ 个自由度。因此我们预期应当首先计算出一个 $10\times1/2\hbar\omega$ 的真空零点能。但正如电磁场被规范不变性限制到了只剩两个自由度，实际的引力场也只有两个独立的自由度，因此我们还需要鬼场去抵消掉 $8\times 1/2\hbar\omega$ 的零点能。而注意到对于引力场来说，鬼场 $c$ 和 $\bar{c}$ 将会直接称为一个携带有 Lorentz 指标的四分量 Grassmann 矢量，这意味着其将刚好提供 $-2\times 4=-8$ 倍的自由度抵消，使得引力场最终只剩下 $2\times 1/2\hbar\omega$ 的真空零点能。

接下来我们将通过计算验证这一点。

写下规范固定后的生成泛函：

$$
\begin{aligned}
    \mathcal{Z}[0]_{h}&=\int\mathcal{D}g_{\mu\nu}\exp\left\{\mathrm{i}\int\mathrm{d}^4x\:\frac{R}{16\pi G_N}\right\}
    \\&\sim\int\mathcal{D}h_{\mu\nu}\exp\left\{\mathrm{i}\int\mathrm{d}^4x\mathrm{d}^4y\left[-\frac{1}{2}h_{\mu\nu}(x)\mathscr{D}^{\mu\nu,\rho\sigma}(x,y)h_{\rho\sigma}(y)+\mathscr{L}_{GF}-\mathrm{i}\varepsilon\text{项}\right]\right\}
\end{aligned}
$$

基于与之前推文一致的讨论，我们接下来要计算：

$$
    I=\sum_{\mu\nu=\rho\sigma}\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\mathscr{D}^{\mu\nu,\rho\sigma}(p)
$$

在有正规化的意义下我们可以执行分部积分，于是有：

$$
\begin{aligned}
    I&=-\sum_{\mu\nu=\alpha\beta}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{p^0}{2\pi}\mathrm{d}(\ln\mathscr{D}^{\mu\nu,\alpha\beta}(p))
    \\&=-\sum_{\mu\nu=\alpha\beta}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\mathscr{D}^{-1}_{\mu\nu,\rho\sigma}\frac{\mathrm{d}}{\mathrm{d}p^0}\mathscr{D}^{\rho\sigma,\alpha\beta}(p)
\end{aligned}
$$

最复杂繁琐的处理便是计算 `$\mathscr{D}^{-1}_{\mu\nu,\alpha\beta}{\mathrm{d}}/{\mathrm{d}p^0}(\mathscr{D}^{\alpha\beta,\rho\sigma}(p))$` 这一项。首先计算出 `$\mathscr{D}^{\alpha\beta,\rho\sigma}(p)$` 对 $p^0$ 的导数，有：

$$
\begin{aligned}
    \frac{\mathrm{d}}{\mathrm{d}p^0}\mathscr{D}^{\rho\sigma,\alpha\beta}(p)=-2&\cdot\left[-\left(1-\frac{1}{\xi}\right)({\delta^{\rho}}_{0}p^{\sigma}\eta^{\alpha\beta}+p^{\rho}{\delta^{\sigma}}_{0}\eta^{\alpha\beta}-{\delta^{\sigma}}_{0}p^{\alpha}\eta^{\rho\beta}-p^{\sigma}{\delta^{\alpha}}_{0}\eta^{\rho\beta})\right.
    \\&\left.-\frac{1}{2}(-2p^0\eta^{\rho\alpha}\eta^{\sigma\beta})+\left(\frac{1}{2}-\frac{1}{4\xi}\right)(-2p^0\eta^{\rho\sigma}\eta^{\alpha\beta})\right]
\end{aligned}
$$

其次调用传播子的结果，给出：

$$
    \mathscr{D}^{-1}_{\mu\nu,\rho\sigma}=\frac{1}{p^2-\mathrm{i}\varepsilon}\left\{\frac{1}{2}\left[(\eta_{\mu\rho}\eta_{\nu\sigma}+\eta_{\mu\sigma}\eta_{\nu\rho}-\eta_{\mu\nu}\eta_{\rho\sigma})-\frac{1-\xi}{p^2}(p_{\mu}p_{\sigma}\eta_{\nu\rho}+p_{\nu}p_{\sigma}\eta_{\mu\rho}+p_{\mu}p_{\rho}\eta_{\nu\sigma}+p_{\nu}p_{\rho}\eta_{\mu\sigma})\right]\right\}
$$

将对 $p^0$ 的导数中除去 $-2$ 后的第一项记为 `$A^{\rho\sigma,\alpha\beta}$`，第二、三项记为 `$B^{\rho\sigma,\alpha\beta}$`；将传播子分子的第一项记为 `$C_{\mu\nu,\rho\sigma}$`，第二项记为 `$D_{\mu\nu,\rho\sigma}$`. 逐项相乘，给出：

$$
\begin{aligned}
    C_{\mu\nu,\rho\sigma}A^{\rho\sigma,\alpha\beta}=-\frac{1}{2}\left(1-\frac{1}{\xi}\right)&(\eta_{\mu 0}p_{\nu}\eta^{\alpha\beta}+p_{\mu}\eta_{\nu 0}\eta^{\alpha\beta}-p_0\eta_{\mu\nu}\eta^{\alpha\beta}
    \\&+p_{\mu}\eta_{\nu 0}\eta^{\alpha\beta}+p_{\nu}\eta_{\mu 0}\eta^{\alpha\beta}-p_0\eta_{\mu\nu}\eta^{\alpha\beta}
    \\&-\eta_{\nu 0}p^{\alpha}{\delta_{\mu}}^{\beta}-\eta_{\mu 0}p^{\alpha}{\delta_{\nu}}^{\beta}+{\delta_{0}}^{\beta}p^{\alpha}\eta_{\mu\nu}
    \\&-p_{\nu}{\delta_{\mu}}^{\beta}{\delta^{\alpha}}_{0}-p_{\mu}{\delta_{\nu}}^{\beta}{\delta^{\alpha}}_{0}+p^{\beta}{\delta^{\alpha}}_0\eta_{\mu\nu})
\end{aligned}
$$

$$
\begin{aligned}
    C_{\mu\nu,\rho\sigma}B^{\rho\sigma,\alpha\beta}=\frac{1}{2}({\delta_{\mu}}^{\alpha}+{\delta_{\mu}}^{\beta}{\delta_{\nu}}^{\alpha}-\eta_{\mu\nu}\eta^{\alpha\beta})p^0-\frac{1}{2}\left(1-\frac{1}{2\xi}\right)(\eta_{\mu\nu}\eta^{\alpha\beta}+\eta_{\mu\nu}\eta^{\alpha\beta}-4\eta_{\mu\nu}\eta^{\alpha\beta})p^0
\end{aligned}
$$

$$
\begin{aligned}
    D_{\mu\nu,\rho\sigma}A^{\rho\sigma,\alpha\beta}=\frac{1}{2p^2}\left(1-\frac{1}{\xi}\right)(1-\xi)&(\eta_{\nu 0}p_{\mu}\eta^{\alpha\beta}p^2+p_{0}p_{\mu}p_{\nu}\eta^{\alpha\beta}-p_{0}p^{\alpha}p_{\mu}{\delta_{\nu}}^{\beta}-p^2p_{\mu}{\delta^{\alpha}}_{0}{\delta_{\nu}}^{\beta}
    \\&+\eta_{\mu 0}p_{\nu}\eta^{\alpha\beta}p^2+p_{0}p_{\mu}p_{\nu}\eta^{\alpha\beta}-p_{0}p_{\nu}p^{\alpha}{\delta_{\mu}}^{\beta}-p_{\nu}{\delta_{\mu}}^{\beta}{\delta^{\alpha}}_{0}p^2
    \\&+p_{0}p_{\mu}p_{\nu}\eta^{\alpha\beta}+p^2\eta_{\nu 0}p_{\mu}\eta^{\alpha\beta}-\eta_{\nu 0}p^{\alpha}p^{\beta}p_{\mu}-p_{\nu}p^{\beta}\eta_{\mu 0}p^{\alpha}
    \\&+p_{0}p_{\mu}p_{\nu}\eta^{\alpha\beta}+p^2\eta_{\mu 0}p_{\nu}\eta^{\alpha\beta}-\eta_{\mu 0}p^{\alpha}p^{\beta}p_{\nu}-p_{\mu}{\delta^{\alpha}}_{0}p_{\beta}p_{\nu})
\end{aligned}
$$

$$
\begin{aligned}
    D_{\mu\nu,\rho\sigma}B^{\rho\sigma,\alpha\beta}=&-\frac{1-\xi}{2p^2}(p_{\mu}{\delta_{\nu}}^{\alpha}p^{\beta}+p_{\nu}p^{\beta}{\delta_{\mu}}^{\alpha}+p_{\mu}p^{\alpha}{\delta_{\nu}}^{\beta})p^0
    \\&+\frac{1-\xi}{2p^2}\left(1-\frac{1}{2\xi}\right)(p_{\mu}p_{\nu}\eta^{\alpha\beta}+p_{\mu}p_{\nu}\eta^{\alpha\beta}+p_{\mu}p_{\nu}\eta^{\alpha\beta}+p_{\mu}p_{\nu}\eta^{\alpha\beta})p^0
\end{aligned}
$$

取迹，即令 `$\mu\nu=\alpha\beta$`，给出：

$$
\begin{aligned}
    &C_{\mu\nu,\rho\sigma}A^{\rho\sigma,\mu\nu}=-6\left(1-\frac{1}{\xi}\right)p^0
    \\&C_{\mu\nu,\rho\sigma}B^{\rho\sigma,\mu\nu}=8p^0+4\left(1-\frac{1}{2\xi}\right)p^0
    \\&D_{\mu\nu,\rho\sigma}A^{\rho\sigma,\mu\nu}=3\left(1-\frac{1}{\xi}\right)(1-\xi)p^0
    \\&D_{\mu\nu,\rho\sigma}B^{\rho\sigma,\mu\nu}=-5(1-\xi)p^0+2(1-\xi)\left(1-\frac{1}{2\xi}\right)p^0
\end{aligned}
$$

将这些项加在一起，我们发现所有含 $\xi$ 的项恰好相互消除掉，这表明引力场的零点能同样不依赖于规范的选取。于是我们有：

$$
\begin{aligned}
    \sum_{\mu\nu=\alpha\beta}\mathscr{D}^{-1}_{\mu\nu,\rho\sigma}\frac{\mathrm{d}}{\mathrm{d}p^0}\mathscr{D}^{\rho\sigma,\alpha\beta}(p)&=\frac{-2}{p^2-\mathrm{i}\varepsilon}(C_{\mu\nu,\rho\sigma}A^{\rho\sigma,\mu\nu}+C_{\mu\nu,\rho\sigma}B^{\rho\sigma,\mu\nu}+D_{\mu\nu,\rho\sigma}A^{\rho\sigma,\mu\nu}+D_{\mu\nu,\rho\sigma}B^{\rho\sigma,\mu\nu})
    \\&=\frac{-2p^0}{p^2-\mathrm{i}\varepsilon}\times 10
\end{aligned}
$$

代回到零点能的积分，有：

$$
    I=-\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}\frac{-2(p^0)^2}{p^2-\mathrm{i}\varepsilon}\times 10
$$

而我们又有：

$$
    E_0=\frac{1}{2\mathrm{i}}V\cdot I
$$

因而有：

$$
    E_0=\frac{1}{2}\int\frac{\mathrm{d}^3p}{(2\pi)^3}E_{\mathbf{p}}V\times 10
$$

这正是我们最开始预期的表观结果。

而进一步考虑鬼场的贡献，有：

$$
    \begin{aligned}
        \mathcal{Z}[0]_G=C_1\int\mathcal{D}\bar{c}^{\mu}\mathcal{D}c^{\nu}\exp\left\{\mathrm{i}\int\mathrm{d}^4x\mathrm{d}^4y\bar{c}^{\mu}(x)c^{\nu}(y)\mathcal{M}_{\mu\nu}(x,y)\right\}=C_1\det\mathcal{M}(x,y)
    \end{aligned}
$$

其中 `$\mathcal{M}_{\mu\nu}(x,y)=\eta_{\mu\nu}\partial^2\delta^4(x-y)$`. 基于类似的讨论，有：

$$
\begin{aligned}
    -\mathrm{i}E_{0G}T&=VT\sum_{\mu=\nu}\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\eta_{\mu\nu}(p^2-\mathrm{i}\varepsilon)\right)+\ln{C'_1}
    \\&=VT\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{-2p^0}{p^2-\mathrm{i}\varepsilon}\times 4
\end{aligned}
$$

于是这给出：

$$
    E_{0G}=-\frac{1}{2}\int\frac{\mathrm{d}^3p}{(2\pi)^3}E_{\mathbf{p}}V\times 8
$$

二者相加，恰好给出：

$$
    E_{0,Gravity}=2\times\frac{1}{2}\int\frac{\mathrm{d}^3p}{(2\pi)^3}E_{\mathbf{p}}V
$$

该结果不依赖于规范的选取，且与我们最初的预期完美一致。

----

[^1]: Gerard ’t Hooft and M. J. G. Veltman. One loop divergencies in the theory of gravitation. *Ann. Inst. H. Poincare A Phys. Theor.*, 20:69–94, 1974.
[^2]: Gustav Uhre Jakobsen. Schwarzschild-tangherlini metric from scattering amplitudes, 2020.
