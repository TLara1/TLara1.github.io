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
R_{00}=0\rightarrow e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu+\mu_3-\mu_2\right)\partial_r\nu+\partial_r^2\nu\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu+\mu_2-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\nu\right)=0
\end{equation}
\begin{equation}
R_{11}=0\rightarrow e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu+\mu_3-\mu_2\right)\partial_r\psi+\partial_r^2\psi\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu+\mu_2-\mu_3\right)\partial_\theta\psi+\partial_\theta^2\psi\right)=0
\end{equation}
The important components of the Einstein tensor are $$G_{22}$$ and $$G_{33}$$.
\begin{equation}
G_{22}=e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\mu_3\right)\partial_r\nu+\partial_r\mu_3\partial_r\psi\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\left(\nu+\psi\right)+\partial_\theta\left(\psi-\mu_3\right)\partial_\theta\psi\right)=0
\end{equation}
\begin{equation}
G_{33}=e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\mu_2\right)\partial_\theta\nu+\partial_\theta\mu_2\partial_\theta\psi\right)+e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu-\mu_2\right)\partial_r\nu+\partial_r^2\left(\nu+\psi\right)+\partial_r\left(\psi-\mu_2\right)\partial_r\psi\right)=0
\end{equation}
Now define $$\beta=\psi+\nu$$, and calculating the difference of $$G_{22}$$ and $$G_{33}$$
\begin{equation}
e^{\mu_3-\mu_2}\left(\partial_r\left(\nu-\mu_2-\mu_3\right)\partial_r\nu+\partial_r^2\beta+\partial_r\left(\psi-\mu_2-\mu_3\right)\partial_r\psi\right)-e^{\mu_2-\mu_3}\left(\partial_\theta\left(\nu-\mu_2-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\beta+\partial_\theta\left(\psi-\mu_2-\mu_3\right)\partial_\theta\psi\right)=0
\end{equation}
which we rewrite as
\begin{equation}
e^{-\beta}\left(\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\beta\right)-\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\beta\right)\right)=2e^{\mu_3-\mu_2}\left(\partial_r\beta\partial_r\mu_3+\partial_r\psi\partial_r\nu\right)-2e^{\mu_2-\mu_3}\left(\partial_\theta\beta\partial_\theta\mu_2+\partial_\theta\psi\partial_\theta\nu\right)
\end{equation}
We can rewrite $$R_{00}$$ and $$R_{11}$$ as
\begin{equation}
0=\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\nu\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\nu\right)
\end{equation}
\begin{equation}
0=\partial_\theta\left(e^{\beta+\mu_3-\mu_2}\partial_r\psi\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\psi\right)
\end{equation}
and adding and subtracting these two equations
\begin{equation}\label{beta eq 1}
0=\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\beta\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\beta\right)
\end{equation}
\begin{equation}
0=\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\left(\nu-\psi\right)\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\left(\nu-\psi\right)\right)
\end{equation}
Defining $$\chi=e^{\nu-\psi}$$, we obtain
\begin{equation}
0=\partial_r\left(e^{3\psi-\nu+\mu_3-\mu_2}\partial_r\left(\chi^2\right)\right)+\partial_\theta\left(e^{3\psi-\nu+\mu_2-\mu_3}\partial_\theta\left(\chi^2\right)\right)
\end{equation}

Now we now there exists a null surface $$N(r,\theta)$$ such that $$g^{\nu\mu}N_\nuN_\mu=0$$. For our ansatz, this reduces to
\begin{equation}
e^{2\mu_3-2\mu_2}\left(\partial_rN\right)^2+\left(\partial_\theta N\right)^2=0
\end{equation}
Now we chose $$e^{2\mu_3-2\mu_2}=\Delta\left(r\right)$$, and seperate $$e^\beta=\sqrt{\Delta(r)}f(\theta)$$. Inserting these two functions into \ref{beta eq 1}
\begin{equation}

\end{equation}

