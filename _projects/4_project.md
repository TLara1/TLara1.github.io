---
layout: page
title: project 4
description: another without an image
img:
importance: 3
category: Physics
---

<h3>II.III Solution for a Circular Disk</h3>

For a circular object centred at $$z=0$$ of radius $$R$$, clearly $$z=\omega\left(\zeta\right)=R\zeta$$. \eqref{varphi complex final} becomes:

\begin{equation}\label{varphi a expand}
    \varphi\left(\zeta\right)+\frac{1}{2\pi i}\oint_\gamma\frac{\varsigma\bar{\varphi}_{,\zeta}\left(\bar{\varsigma}\right)}{\varsigma-\zeta}d\varsigma=\mathcal{A}
\end{equation}

Because $$\varphi\left(\zeta\right)$$ is analytic in the unit circle, we express the function as a power series: $$\varphi\left(\zeta\right)=a_0+a_1\zeta+a_2\zeta^2+...$$. Using $$\bar{\varsigma}\varsigma=1$$ on the unit circle:

\begin{equation}
  \frac{1}{2\pi i}\oint_\gamma\frac{\varsigma\bar{\varphi}_{,\zeta}\left(\bar{\varsigma}\right)}{\varsigma-\zeta} d\varsigma= \frac{1}{2\pi i}\oint _\gamma\frac{\bar{a_1}\varsigma+2\bar{a_2}}{\varsigma-\zeta}d\varsigma+\sum _{k=3}^\infty\frac{1}{2\pi i}\oint _\gamma\frac{n!\bar{a} _n \bar{\varsigma}^{k-2}}{\varsigma-\zeta}d\varsigma
\end{equation}

With \eqref{f0 comp}:

\begin{equation}
  \frac{1}{2\pi i}\oint _\gamma\frac{\bar{a} _n \bar{\varsigma}^{k-2}}{\varsigma-\zeta}d\varsigma = 0^n = 0
\end{equation}

So, reducing \eqref{varphi a expand} and simplfying integrals:

\begin{equation}\label{varphi simple}
  \varphi\left(\zeta\right)+\bar{a_1}\zeta+2\bar{a_2}=\mathcal{A}
\end{equation}

By definition $$a_1\equiv\varphi_{,\zeta}\left(0\right)$$ and $$a_2\equiv\varphi_{,\zeta\zeta}\left(0\right)$$, using \eqref{varphi simple}, taking derivatives and setting $$\zeta=0$$, we find:

\begin{equation}
  a_1+\bar{a_1}=\mathcal{A}_{,\zeta} \nonumber
\end{equation}

\begin{equation}
  a_2=\mathcal{A}_{,\zeta\zeta} \nonumber
\end{equation}

Only the real part of $$a_1$$ is determined, as the imaginary portion cancels in \eqref{varphi simple}. 

Using \eqref{{psi complex final} we can find a similar expression for $$\psi\left(\zeta\right)$$, noting that for our circular case:

\begin{equation}
  \frac{1}{2\pi i}\oint_\gamma\frac{\bar{\varsigma}\varphi_{,\zeta}\left(\varsigma\right)}{\varsigma-\zeta}d\varsigma = \frac{\varphi_{,\zeta}\left(\zeta\right)}{\zeta}
\end{equation}

And:

\begin{equation}
  \psi\left(\zeta\right)+\mathcal{A}-2a_2+\frac{\mathcal{A}_{,\zeta}}{\zeta}-\frac{\bar{a_1}}{\zeta}=\mathcal{B}
\end{equation}


