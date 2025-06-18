---
layout:     post
title:      "Vacuum-Energy-of-Gravitational-Field"
subtitle:   "Calculating by Path Integral"
date:       2025-6-18 20:00:00
author:     "fromuly"
header-img: "img/post-bg-2025-9.jpg"
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

TBD.

----

[^1]: Gerard ’t Hooft and M. J. G. Veltman. One loop divergencies in the theory of gravitation.
*Ann. Inst. H. Poincare A Phys. Theor.*, 20:69–94, 1974.
[^2]: Gustav Uhre Jakobsen. Schwarzschild-tangherlini metric from scattering amplitudes, 2020.
