---
layout:     post
title:      "Kaluza-Klein Theory-1"
subtitle:   "Extra Dimensions."
date:       2026-2-2 22:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-18.jpg"
catalog: true
usemathjax: true
music-id: 1453962590
tags:
    - Physics
    - Quantum Field Theory
    - Mathematics
---

## Intro

Kaluza-Klein theory is a kind of theory with some extra dimension, and they are often assumed to be compactified in a tiny scale. In this note, we will give a brief overview of some famous model based on this theory, and their experimental constraints.

## Kaluza-Klein Theory

The basic set-up of Kaluza-Klein theory is a higher dimension action with a given geometric structure of those extra dimensions.

Considering an Einstein-Hilbert action in $d+n$ dimension with $d$ macroscopic and $n$ mesoscopic or microscopic, we have:

$$
	\hat{S}_{EH}=\frac{1}{2}\hat{M}_P^{d+n-2}\int\mathrm{d}^{d+n}x\sqrt{-\hat{g}}\hat{R},
$$

where hat means they are defined in $d+n$ dimension, and the power of `$\hat{M}_P$` is determined by simply dimensional analysis. We will take $\eta=\mathrm{diag}(-,+,+,\cdots)$ and denote coordinates in $d+n$ dimension as `$x^{\hat{\mu}}=(x^\mu,z^i)$`. To see the relation between $\hat{M}_P$ and $M_P$ defined in $d$ macroscopic dimension, constraining metric $\hat{g}$ in $d$ dimension:

$$
	\det\hat{g}(x,z=0)=\det g\cdot \det g_n,
$$

and integrating out $n$ extra dimension:

$$
	\begin{aligned}
		\hat{S}_{EH}&\simeq \frac{1}{2}\hat{M}_P^{d+n-2}\int\mathrm{d}^{d}x\mathrm{d}^{n}z\sqrt{-g}\sqrt{g_n}R+\cdots
		\\&=\frac{1}{2}V_n\hat{M}_P^{d+n-2}\int\mathrm{d}^{d}x\sqrt{-g}R+\cdots
		\\&=\frac{1}{2}M_P^{d-2}\int\mathrm{d}^{d}x\sqrt{-g}R+\cdots
		\\&\simeq S_{EH},
	\end{aligned}
$$

where $\cdots$ denotes some other term beyond $d$ dimension E-H action. Thus, we can see the relationship between `$M_P$` and `$\hat{M}_P$`:

$$
	M_P^{d-2}=V_n\hat{M_P}^{n+d-2}.
$$

We will denote `$R\sim V_n^{1/n}$` as the characteristic scale of the extra dimension.

\subsection{$T^n$ Compactification}

The simplest Kaluza-Klein model is constructed by taking $n$ extra dimension as $T^n$. We will show the complete construction of $T^n$ K-K model in this subsection.

\subsubsection*{Scalar Field}

We can begin with the easiest situation. The Lagrangian of a $d+n$ dimension massless scalar field is:

$$
	\hat{\mathscr{L}}_{scalar}=-\frac{1}{2}\partial_{\hat{\mu}}\phi\partial^{\hat{\mu}}\phi=-\frac{1}{2}\partial_{\mu}\phi\partial^{\mu}\phi-\frac{1}{2}\partial_i\phi\partial^i\phi
$$

notice that we have taken `$\eta_{\hat{\mu}\hat{\nu}}$` as the background metric of $T^n$. We will assume that this field can propagate in the bulk, otherwise we need to add `$\delta^n(z-z_0)$` in the Lagrangian (which we do need to in the ADD model will be introduced later).

By compactification, $\phi$ should have the mode expansion:

$$
	\phi(x,z)=\sum_{\vec{n}}\phi^{\vec{n}}(x)\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right)
$$

Plugging this into the Lagrangian, and integrating out the $n$ extra dimension, we can get $d$ dimension effective Lagrangian:

$$
	\begin{aligned}
		\mathscr{L}_{scalar}&=\int\mathrm{d}^n{z}\:\hat{\mathscr{L}}_{scalar}
		\\&=\sum_{\vec{n}}\int\mathrm{d}^n{z}\:\exp\left[\mathrm{i}\frac{2\pi(\vec{n}+\vec{m})\cdot\vec{z}}{R}\right]\left\{-\frac{1}{2}\partial_\mu\phi^{\vec{n}}\partial^{\mu}\phi^{\vec{m}}+\frac{1}{2}\frac{4\pi^2\vec{n}\cdot\vec{m}}{R^2}\phi^{\vec{n}}\phi^{\vec{m}}\right\}
		\\&=V_n\sum_{\vec{n}}\left\{-\frac{1}{2}\partial_\mu\phi^{\vec{n}}\partial^{\mu}\phi^{-\vec{n}}-\frac{1}{2}m_{\vec{n}}^2\phi^{\vec{n}}\phi^{-\vec{n}}\right\},
	\end{aligned}
$$

where we have `$m_{\vec{n}}^2=4\pi^2n^2/R^2$`.

This shows that through compactification, we get a series of field with mass `$m_{\vec{n}}$`, which is known as K-K tower. The propagator is easy to get:

$$
	D_{\vec{n},\vec{m}}(p)=\frac{\mathrm{i}\delta_{\vec{n},\vec{-m}}}{p^2+m_{\vec{n}}^2-\mathrm{i}\varepsilon}.
$$

\subsubsection*{Vector Field\cite{Sundrum:2005jf}}

The treatment of fermions in Kaluza-Klein theory is rather subtle. We will deal with it later, and consider vector fields for now. It is easy to write down the Yang-Mills Lagrangian in $d+n$ dimension:

$$
	\begin{aligned}
		\hat{\mathscr{L}}_{vec}&=\mathrm{Tr}\:\left\{-\frac{1}{4}F_{\hat{\mu}\hat{\nu}}F^{\hat{\mu}\hat{\nu}}\right\}
		\\&=\mathrm{Tr}\:\left\{-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\frac{1}{2}F_{\mu i}F^{\mu i}-\frac{1}{4}F_{ij}F^{ij}\right\}
	\end{aligned}
$$

where we have `$F_{\hat{\mu}\hat{\nu}}=\partial_{\hat{\mu}}A_{\hat{\nu}}-\partial_{\hat{\nu}}A_{\hat{\mu}}-\mathrm{i}g[A_{\hat{\mu}},A_{\hat{\nu}}],\:A_{\hat{\mu}}=A_{\hat{\mu}}^aT_a$`. 

The gauge transformation is:

$$
	A'_{\hat{\mu}}=\frac{\mathrm{i}}{g}U^{-1}D_{\hat{\mu}}U,\:U(x^\mu,z^i)\in G,
$$

where `$D_{\hat{\mu}}$` is the covariant derivative. We can get its infinitesimal formal:

$$
	\delta A_{\hat{\mu}}=\frac{1}{g}D_{\hat{\mu}}\Omega(x^{\mu},z^i).
$$

Writing down the model expansion:

$$
	\begin{aligned}
		&A_{\hat{\mu}}(x,z)=\sum_{\vec{n}}A_{\hat{\mu}}^{\vec{n}}(x)\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right)
		\\&\Omega(x,z)=\sum_{\vec{n}}\Omega^{\vec{n}}(x)\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right)
	\end{aligned}
$$

and we can begin to calculate the reduced form of Lagrangian. The `$F_{\mu i}$` can be expanded as:

$$
	\begin{aligned}
		F_{\mu i}(x,z)&=\partial_{\mu}A_{i}-\partial_{i} A_{\mu}+g{f^{a}}_{bc}A^{b}_{\mu}A^{c}_{i}T_{a}
		\\&=\sum_{\vec{n}}\left\{\partial_{\mu}A_{i}^{\vec{n}}-\mathrm{i}\frac{2\pi}{R}n_i A_{\mu}^{\vec{n}}+g{f^{a}}_{bc}\sum_{\vec{k}}A^{b,\vec{k}}_{\mu}A^{c,\vec{n}-\vec{k}}_{i}T_{a}\right\}\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right)
		\\&=\sum_{\vec{n}}F^{\vec{n}}_{\mu i}(x)\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right),
	\end{aligned}
$$

where we have:

$$
	F^{\vec{n}}_{\mu i}(x)=\partial_{\mu}A_{i}^{\vec{n}}(x)-\mathrm{i}\frac{2\pi}{R}n_i A_{\mu}^{\vec{n}}(x)+g{f^{a}}_{bc}\sum_{\vec{k}}A^{b,\vec{k}}_{\mu}(x)A^{c,\vec{n}-\vec{k}}_{i}(x)T_{a}.
$$

Similarly, expanding `$F_{ij}$` to the K-K mode:

$$
	\begin{aligned}
		F_{ij}(x,z)&=\partial_{i}A_{j}-\partial_{j}A_{i}+g{f^{a}}_{bc}A^{b}_{i}A^{c}_{j}T_{a}
		\\&=\sum_{\vec{n}}\left\{\mathrm{i}\frac{2\pi}{R}n_iA^{\vec{n}}_{j}-\mathrm{i}\frac{2\pi}{R}n_jA^{\vec{n}}_{i}+g{f^{a}}_{bc}\sum_{\vec{k}}A^{b,\vec{k}}_{i}A^{c,\vec{n}-\vec{k}}_{j}T_{a}\right\}\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right)
		\\&=\sum_{\vec{n}}F^{\vec{n}}_{ij}(x)\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right),
	\end{aligned}
$$

where `$F^{\vec{n}}_{ij}$` is:

$$
	F^{\vec{n}}_{ij}(x)=\mathrm{i}\frac{2\pi}{R}n_iA^{\vec{n}}_{j}(x)-\mathrm{i}\frac{2\pi}{R}n_jA^{\vec{n}}_{i}(x)+g{f^{a}}_{bc}\sum_{\vec{k}}A^{b,\vec{k}}_{i}(x)A^{c,\vec{n}-\vec{k}}_{j}(x)T_{a}
$$

and `$F_{\mu\nu}$` is:

$$
	\begin{aligned}
		F_{\mu\nu}(x,z)&=\partial_{\mu}A_{\nu}-\partial_{\mu}A_{\nu}+g{f^{a}}_{bc}A^{b}_{\mu}A^{c}_{\nu}T_{a}
		\\&=\sum_{\vec{n}}\left\{\partial_{\mu}A^{\vec{n}}_{\nu}-\partial_{\nu}A^{\vec{n}}_{\mu}+g{f^{a}}_{bc}\sum_{\vec{k}}A^{b,\vec{k}}_{\mu}A^{c,\vec{n}-\vec{k}}_{\nu}T_{a}\right\}\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right)
		\\&=\sum_{\vec{n}}F^{\vec{n}}_{\mu\nu}(x)\exp\left(\mathrm{i}\frac{2\pi\vec{n}\cdot\vec{z}}{R}\right),
	\end{aligned}
$$

which is obvious. Plugging them into Lagrangian, we can get:

$$
	\begin{aligned}
		\mathscr{L}_{vec}&=\int\mathrm{d}^n z\:\hat{\mathscr{L}}_{vec}
		\\&=V_n\mathrm{Tr}\sum_{\vec{n}}\left\{-\frac{1}{4}F^{\vec{n}}_{\mu\nu}F^{\mu\nu,-\vec{n}}-\frac{1}{2}F^{\vec{n}}_{\mu i}F^{\mu i,-\vec{n}}-\frac{1}{4}F^{\vec{n}}_{ij}F^{ij,-\vec{n}}\right\}
	\end{aligned}
$$

after some calculation, we can get:

$$
	\begin{aligned}
		\mathscr{L}_{vec}^{\vec{n}}=\mathrm{Tr}&\left\{-\frac{1}{4}(\partial_{\mu}A_{\nu}^{\vec{n}}-\partial_{\nu}A_{\mu}^{\vec{n}})(\partial^{\mu}A^{\nu,-\vec{n}}-\partial^{\nu}A^{\mu,-\vec{n}})-\frac{1}{2}(\partial_{\mu}A_{i}^{\vec{n}}-\mathrm{i}\frac{2\pi}{R}n_i A_{\mu}^{\vec{n}})(\partial^{\mu}A^{i,-\vec{n}}+\mathrm{i}\frac{2\pi}{R}n^i A^{\mu,-\vec{n}})\right.
		\\&\left.-\frac{1}{4}\cdot\frac{4\pi^2}{R^2}(n_iA_j^{\vec{n}}-n_jA_{i}^{\vec{n}})(n^iA^{j,-\vec{n}}-n^jA^{i,-\vec{n}})+\mathscr{L}_{int}^{\vec{n}}\right\}.
	\end{aligned}
$$

Reorganizing the expression, we have:

$$
	\begin{aligned}
		\mathscr{L}_{vec,kin}^{\vec{n}}=\mathrm{Tr}&\left\{-\frac{1}{4}(\partial_{\mu}A_{\nu}^{\vec{n}}-\partial_{\nu}A_{\mu}^{\vec{n}})(\partial^{\mu}A^{\nu,-\vec{n}}-\partial^{\nu}A^{\mu,-\vec{n}})-\frac{1}{2}\cdot\frac{4\pi^2}{R^2}n^2A_{\mu}^{\vec{n}}A^{\mu,-\vec{n}}-\frac{1}{2}\partial_{\mu}A_{i}^{\vec{n}}\partial^{\mu}A^{i,-\vec{n}}\right.
		\\&\left.-\frac{1}{2}\cdot\frac{4\pi^2}{R^2}n^2A_{i}^{\vec{n}}A^{i,-\vec{n}}+\mathrm{i}\frac{\pi}{R}\left(n_i A^{\vec{n}}_{\mu}\partial^{\mu}A^{i,-\vec{n}}-n_i A^{-\vec{n}}_{\mu}\partial^{\mu}A^{i,\vec{n}}\right)+\frac{2\pi^2}{R^2}n_i A^{i,\vec{n}}n_j A^{j,\vec{-n}}\right\}.
	\end{aligned}
$$

Notice that for modes who have $\vec{n}\neq 0$, fields `$A^{\vec{n}}_{\mu}$` are massive, which indicates some kinds of "Higgs" mechanism. Recalling the gauge transformation of `$A_{\hat{\mu}}$`, we have:

$$
	\begin{aligned}
		&\delta A_{\mu}^{\vec{n}}(x)=\frac{1}{g}\partial_{\mu}\Omega^{\vec{n}}(x)-\mathrm{i}\sum_{\vec{k}}[A^{\vec{k}}_{\mu}(x),\Omega^{\vec{n}-\vec{k}}(x)]
		\\&\delta A_{i}^{\vec{n}}(x)=\frac{\mathrm{i}}{g}\cdot\frac{2\pi}{R}n_i\Omega^{\vec{n}}(x)-\mathrm{i}\sum_{\vec{k}}[A^{\vec{k}}_{i}(x),\Omega^{\vec{n}-\vec{k}}(x)]
	\end{aligned}
$$

In order to do the quantization, we add the gauge fixing term to the Lagrangian:

$$
	\mathscr{L}_{GF}=\mathrm{Tr}\left\{-\frac{1}{2\xi}(\partial_{\mu}A^{\mu}-\xi\partial_{i}A^{i})^2\right\},
$$

and get the F-P ghost term:

$$
	\mathscr{L}_{gh}=-\int\mathrm{d}^{d+n}y\:\bar{c}_a(x)\mathcal{M}^{ab}(x,y)c_b(y)
$$

where we have:

$$
	\mathcal{M}_{ab}=\frac{\delta \mathcal{F}_{a}}{\delta \Omega^{b}}\simeq\frac{1}{g}\delta_{ab}(\partial_{\mu}\partial^{\mu}-\xi\partial_i\partial^i)-f_{abc}(\partial_{\mu}A^{c \mu}-\xi\partial_i A^{c i})
$$

Expanding in K-K modes:

$$
	\begin{aligned}
		\mathscr{L}^{\vec{n}}_{GF}&=-\frac{1}{2\xi}(\partial_{\mu}A^{\mu,\vec{n}}-\mathrm{i}\xi\frac{2\pi}{R}n_{i}A^{i,\vec{n}})(\partial_{\mu}A^{\mu,-\vec{n}}+\mathrm{i}\xi\frac{2\pi}{R}n_{i}A^{i,-\vec{n}})
		\\&=-\frac{1}{2\xi}\partial_{\mu}A^{\mu,\vec{n}}\partial_{\mu}A^{\mu,-\vec{n}}-\frac{\xi}{2}\cdot\frac{4\pi^2}{R^2}(n_i A^{i,\vec{n}})(n_i A^{i,-\vec{n}})+\mathrm{i}\frac{\pi}{R}(n_i A^{i,\vec{n}}\partial_{\mu}A^{\mu,-\vec{n}}-n_i A^{i,-\vec{n}}\partial_{\mu}A^{\mu,\vec{n}})
	\end{aligned}
$$

notice that when we sum overall $\vec{n}$, the mixing term in `$\mathscr{L}^{\vec{n}}_{vec}$` will be eliminated by the last term in `$\mathscr{L}^{\vec{n}}_{GF}$`. Thus we can get the whole Lagrangian:

$$
	\begin{aligned}
		\mathscr{L}^{\vec{n}}&=\mathscr{L}^{\vec{n}}_{vec}+\mathscr{L}^{\vec{n}}_{GF}+\mathscr{L}^{\vec{n}}_{gh}
		\\&=\mathrm{Tr}\left\{-\frac{1}{2}(\partial_{\mu}A_{\nu}^{\vec{n}}\partial^{\mu}A^{\nu,-\vec{n}}-\partial_{\mu}A_{\nu}^{\vec{n}}\partial^{\nu}A^{\mu,-\vec{n}})-\frac{1}{2\xi}\partial_{\mu}A^{\mu,\vec{n}}\partial_{\mu}A^{\mu,-\vec{n}}-\frac{1}{2}\cdot\frac{4\pi^2}{R^2}n^2A_{\mu}^{\vec{n}}A^{\mu,-\vec{n}}\right.
		\\&\left.-\frac{1}{2}\partial_{\mu}A_{i}^{\vec{n}}\partial^{\mu}A^{i,-\vec{n}}-\frac{1}{2}\cdot\frac{4\pi^2}{R^2}n^2A_{i}^{\vec{n}}A^{i,-\vec{n}}-\frac{\xi}{2}\cdot\frac{4\pi^2}{R^2}(n_i A^{i,\vec{n}})(n_i A^{i,-\vec{n}})+\frac{2\pi^2}{R^2}n_i A^{i,\vec{n}}n_j A^{j,\vec{-n}}\right\}
		\\&-\frac{1}{g}\bar{c}^{\vec{n}}_a\left(\partial_{\mu}\partial^{\mu}-\xi\frac{4\pi^2}{R^2}n^2\right)c^{a,-\vec{n}}+\mathscr{L}_{int}^{\vec{n}}.
	\end{aligned}
$$

So we can read out the propagators.

TBD.
