---
layout: page
title: On the Schwarzchild and Kerr Metrics
description:
img: 
importance: 1
category: Physics
related_publications: false
toc:
  beginning: true
---

## Introduction

Here we derive the Schwarzschild and Kerr Metrics for static and rotating spherical bodies.

## I. Riemann and Einstein Tensors

We will need the Riemann and Einstein tensors to write the Einstein field equations in a vacuum.

The Riemann curvature tensor is built from the Christoffel symbols of a metric $$g_{\mu\nu}$$
\begin{equation}
R^\rho_{\sigma\mu\nu}=\Gamma^\rho_{\nu\sigma,\mu}-\Gamma^\rho_{\mu\sigma,\nu}+\Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma}-\Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma}
\end{equation}
With Christoffel symbols given by
\begin{equation}
\Gamma^\rho_{\mu\nu}=\frac{1}{2}g^{\rho\lambda}\left(g_{\lambda\mu,\nu}+g_{\lambda\nu,\mu}-g_{\mu\nu,\lambda}\right)
\end{equation}

The Einstein tensor is constructed from the Ricci tensor, $$R_{\mu\nu}=R^\rho_{\mu\rho\nu}$$ and the Ricci Scalar, $$R=R^\nu_\nu$$.
\begin{equation}
G_{\mu\nu}=R_{\mu\nu}-\frac{1}{2}Rg_{\mu\nu}
\end{equation}
In vacua, Einstein's field equations are $$G_{\mu\nu}=0$$ which implies $$R_{\mu\nu}=0$$.

## II. The Schwarzschild Solution

The Schwarzschild metric is the exact solution to the Einstein field equations for the gravitational field outside a spherical mass with no angular momentum. We work in spherical coordinates $$t,r,\theta,\phi$$. Due to a static solution and rotational and azimuthal invariance, we expect our metric to be invariant under $$t\rightarrow-t$$, $$\theta\rightarrow-\theta$$, and $$\phi\rightarrow-\phi$$, which removes off-diagonal terms from our metric. Furthermore, due to spherical symmetry, our metric should only depend on $$r$$ and $$\theta$$. Our line element is
\begin{equation}
ds^2=g_ttd_t^2+g_rrdr^2+g_{\theta\theta}d\theta^2+g_{\phi\phi}d\phi^2
\end{equation}
which we rewrite as
\begin{equation}
ds^2=-e^{2\nu}dt^2+e^{2\mu_2}dr^2+e^{2\mu_3}d\theta^2+e^{2\psi}d\phi^2
\end{equation}
where $$\nu$$, $$\mu_2$$, $$\mu_3$$, and $$\psi$$ are functions of $$r$$ and $$\theta$$.

Now the Ricci tensor has six nonzero elements, of which $$R_{00}$$ and $$R_{11}$$ are of interest. Setting these to zero yields
\begin{equation}
R_{00}=0\rightarrow e^{\mu_3-\mu_2}\left(\partial_r\right)
\end{equation}

