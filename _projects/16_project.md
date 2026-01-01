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
ds^2=g_{tt}d_t^2+g_{rr}dr^2+g_{\theta\theta}d\theta^2+g_{\phi\phi}d\phi^2
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
\begin{equation}\label{long beta eq}
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
\begin{equation}\label{beta eq 2}
0=\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\left(\nu-\psi\right)\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\left(\nu-\psi\right)\right)
\end{equation}
Defining $$\chi=e^{\nu-\psi}$$, we obtain
\begin{equation}
0=\partial_r\left(e^{3\psi-\nu+\mu_3-\mu_2}\partial_r\left(\chi^2\right)\right)+\partial_\theta\left(e^{3\psi-\nu+\mu_2-\mu_3}\partial_\theta\left(\chi^2\right)\right)
\end{equation}

Now we now there exists a null surface $$N(r,\theta)$$ such that $$g^{\nu\mu}N_\nu N_\mu=0$$. For our ansatz, this reduces to
\begin{equation}
e^{2\mu_3-2\mu_2}\left(\partial_rN\right)^2+\left(\partial_\theta N\right)^2=0
\end{equation}
Now we chose $$e^{2\mu_3-2\mu_2}=\Delta\left(r\right)$$, and seperate $$e^\beta=\sqrt{\Delta(r)}f(\theta)$$. Inserting these two functions into \ref{beta eq 1}
\begin{equation}
0=\frac{f}{2}\partial_r^2\Delta+\partial_\theta^2f
\end{equation}
This is solved by $$\partial_r^2\Delta=2$$ and $$f=\sin\left(\theta\right)$$. Introducing the constants $$M$$ and $$a$$, we write $$\Delta=r^2+a^2-2Mr$$.

Using our solutions
\begin{equation}
e^{\mu_3-\mu_2}=\sqrt{\Delta}\quad e^\beta=\sqrt{\Delta\delta}
\end{equation}
with $$\mu=\cos\left(\theta\right)$$ and $$\delta=1-\mu^2=\sin^2\left(\theta\right)$$. Note that $$\partial_\theta=-\sqrt{\delta}\partial_\mu$$. Now writing \ref{beta eq 2}
\begin{equation}
0=\partial_r\left(\Delta\partial_r\left(\nu-\psi\right)\right)+\partial_\mu\left(\delta\partial_\mu\left(\nu-\psi\right)\right)
\end{equation}
which we can express as
\begin{equation}\label{partial Delta and chi eq}
0=\partial_r\left(\frac{\Delta}{\chi}\partial_r\chi\right)+\partial_\mu\left(\frac{\delta}{\chi}\partial_\mu\chi\right)
\end{equation}
\begin{equation}
\chi\left(\partial_r\left(\Delta\partial_r\chi\right)+\partial_\mu\left(\delta\partial_\mu\chi\right)\right)=\Delta\left(\partial_r\chi\right)^2+\delta\left(\partial_\mu\chi\right)^2
\end{equation}
We can also write \ref{long beta eq} with these new definitions
\begin{equation}
\frac{1}{2}\left(\partial_r^2\Delta-\partial_\mu^2\delta\right)=\partial_r\Delta\partial_r\mu_3+2\Delta\partial_r\psi\partial_r\nu-\partial_\mu\delta\partial_\mu\mu_2-2\delta\partial_\mu\psi\partial_\mu\nu
\end{equation}
Now using $$\partial_r\Delta=2$$ and $$\partial_\mu\delta=-2$$
\begin{equation}\label{intermediate 2= eq}
2=\partial_r\Delta\partial_r\mu_3+2\Delta\partial_r\psi\partial_r\nu-\partial_\mu\delta\partial_\mu\mu_2-2\delta\partial_\mu\psi\partial_\mu\nu
\end{equation}
with $$e^{2\psi}=e^\beta\chi^{-1}$$ and $$e^{2\nu}=e^\beta\chi$$
\begin{equation}
\partial_r\psi=\frac{1}{4\Delta}\partial_r\Delta-\frac{1}{2\chi}\partial_r\chi\quad
\partial_r\nu=\frac{1}{4\Delta}\partial_r\Delta+\frac{1}{2\chi}\partial_r\chi
\end{equation}
\begin{equation}
\partial_\mu\psi=\frac{1}{4\delta}\partial_\mu\delta-\frac{1}{2\chi}\partial_\mu\chi\quad
\partial_\mu\nu=\frac{1}{4\delta}\partial_\mu\delta+\frac{1}{2\chi}\partial_\mu\chi
\end{equation}
And we reduce \ref{intermediate 2= eq} to
\begin{equation}
2=\partial_r\Delta\partial_r\mu_3-\partial_\mu\delta\partial_\mu\mu_2+\frac{\Delta}{2}\left(\frac{1}{2\Delta}\partial_r\Delta-\frac{1}{\chi}\partial_r\chi\right)\left(\frac{1}{2\Delta}\partial_r\Delta+\frac{1}{\chi}\partial_r\chi\right)-\frac{\delta}{2}\left(\frac{1}{2\delta}\partial_\mu\delta-\frac{1}{\chi}\partial_\mu\chi\right)\left(\frac{1}{2\delta}\partial_\mu\delta+\frac{1}{\chi}\partial_\mu\chi\right)
\end{equation}
\begin{equation}
2=\partial_r\Delta\partial_r\mu_3-\partial_\mu\delta\partial_\mu\mu_2+\frac{1}{8\Delta}\left(\partial_r\Delta\right)^2-\frac{1}{8\delta}\left(\partial_\mu\delta\right)^2+\frac{\delta}{2\chi^2}\left(\partial_\mu\chi\right)^2-\frac{\Delta}{2\chi^2}\left(\partial_r\chi\right)^2
\end{equation}
With $$\partial_r\Delta=2\left(r-M\right)$$ and $$\partial_\mu\delta=-2\mu$$
\begin{equation}
2=2\left(r-M\right)\partial_r\mu_3+2\mu\partial_\mu\mu_2+\frac{1}{2\Delta}\left(r-M\right)^2-\frac{1}{2\delta}\mu^2+\frac{1}{2\chi^2}\left(\delta\left(\partial_\mu\chi\right)^2-\Delta\left(\partial_r\chi\right)^2\right)
\end{equation}
We now observe $$\partial_r\left(\mu_3-\mu_2\right)=\partial_r\log\left(\sqrt{\Delta}\right)=\left(r-M\right)\Delta^{-1}$$ and $$\partial_\mu\left(\mu_2-\mu_3\right)=-\partial_\mu\log\left(\sqrt{\Delta}\right)=0$$, so
\begin{equation}
2=\left(\left(r-M\right)\partial_r\right)\left(\mu_2+\mu_3\right)+\left(r-M\right)\partial_r\left(\mu_3-\mu_2\right)+\left(\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)+\mu\partial_\mu\left(\mu_2-\mu_3\right)+\frac{1}{2\Delta}\left(r-M\right)^2-\frac{1}{2\delta}\mu^2+\frac{1}{2\chi^2}\left(\delta\left(\partial_\mu\chi\right)^2-\Delta\left(\partial_r\chi\right)^2\right)
\end{equation}
\begin{equation}
2=\left(\left(r-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)+\frac{3}{2\Delta}\left(r-M\right)^2-\frac{1}{2\delta}\mu^2+\frac{1}{2\chi^2}\left(\delta\left(\partial_\mu\chi\right)^2-\Delta\left(\partial_r\chi\right)^2\right)
\end{equation}
And simplifying further with $$\mu^2=1-\delta$$ and $$(r-M)^2=\Delta+M^2-a^2$$
\begin{equation}\label{chi^2 master eq}
2\left(\left(r-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)-\frac{1}{\chi^2}\left(\Delta\left(\partial_r\chi\right)^2-\delta\left(\partial_\mu\chi\right)^2\right)+3\frac{M^2-a^2}{\Delta}-\frac{1}{\delta}=0
\end{equation}

We next define $$f=e^{2\nu}=e^\beta\chi=\sqrt{\Delta\delta}\chi$$. Writing \ref{partial Delta and chi eq} in terms of $$f$$
\begin{equation}
0=\partial_r\left(\frac{\Delta}{f}\partial_rf\right)+\partial_\mu\left(\frac{\delta}{f}\partial_\mu f\right)
\end{equation}
\begin{equation}
\frac{\Delta}{f}\left(\partial_rf\right)^2+\frac{\delta}{f}\left(\partial_\mu f\right)^2=\partial_r\left(\Delta\partial_rf\right)+\partial_\mu\left(\delta\partial_\mu f\right)
\end{equation}
This equation is easier to solve if we make the change of variable
\begin{equation}
f=\frac{1+\epsilon}{1-\epsilon}
\end{equation}
We know note that $$f\in\mathcal{R}$$, so $$\Im\left(\epsilon\right)=0$$.
with $$\partial_r f=\frac{2}{\left(1-\epsilon\right)^2}\partial_r\epsilon$$
\begin{equation}
\frac{4}{1-\epsilon^2}\left(\Delta\left(\partial_r\epsilon\right)^2+\delta\left(\partial_\mu\epsilon\right)^2\right)=\frac{4}{1-\epsilon}\left(\Delta\left(\partial_r\epsilon\right)^2+\delta\left(\partial_\mu\epsilon\right)^2\right)+2\left(\partial_r\left(\Delta\partial_r\epsilon\right)+\partial_\mu\left(\delta\partial_\mu\epsilon\right)\right)
\end{equation}
\begin{equation}
-2\epsilon\left(\Delta\left(\partial_r\epsilon\right)^2+\delta\left(\partial_\mu\epsilon\right)^2\right)=\left(1-\epsilon^2\right)\left(\partial_r\left(\Delta\partial_r\epsilon\right)+\partial_\mu\left(\delta\partial_\mu\epsilon\right)\right)
\end{equation}
Now define $$\eta=\frac{\left(r-M\right)^2}{M^2-a^2}=\frac{\Delta}{M^2-a^2}+1$$, $$\partial_r=\frac{1}{\sqrt{M^2-a^2}}\partial_\eta$$ and with $$\delta=1-\mu^2$$
\begin{equation}
-2\epsilon\left(\left(\eta^2-1\right)\left(\partial_\eta\epsilon\right)^2+\left(1-\mu^2\right)\left(\partial_\mu\epsilon\right)^2\right)=\left(1-\epsilon^2\right)\left(\partial_\eta\left(\left(\eta^2-1\right)\partial_\eta\epsilon\right)+\partial_\mu\left(\left(1-\mu^2\right)\partial_\mu\epsilon\right)\right)
\end{equation}
this equation is solved by $$\epsilon=\pm\nu$$ and $$\epsilon=\pm\mu$$.
First let's consider $$\epsilon=\mu$$, from which we have $$f=\frac{1+\mu}{1-\mu}$$, from which we arive at
\begin{equation}
\chi=\frac{1}{\sqrt{\Delta\delta}}\frac{1+\mu}{1-\mu}
\end{equation}
Now from \ref{chi^2 master eq}, with our solution for $$\chi$$
\begin{equation}
\left(\left(r-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)+\frac{M^2-a^2}{\Delta}+\frac{1+\mu}{1-\mu}=0
\end{equation}
We solve this to find
\begin{equation}
\mu_2+\mu_3=\log{\left(\frac{\left(r-M\right)\left(1-\mu\right)^2}{\mu\Sqrt{\Delta}}\right)}
\end{equation}
And finally, obtaining the componenets of the metric
\begin{equation}
g_{tt}=-e^{2\nu}=-f=\frac{1-\mu}{1+\mu}
\end{equation}
\begin{equation}
g_{rr}=e^{2\mu_2}=\frac{1}{\sqrt[\Delta}}e^{\mu_2+\mu_3}=\frac{\left(r-M\right)\left(1-\mu\right)^2}{\mu\Delta}
\end{equation}
\begin{equation}
g_{\theta\theta}=e^{2\mu_3}=\sqrt{\Delta}e^{\mu_2+\mu_3}=\frac{\left(r-M\right)\left(1-\mu\right)^2}{\mu}
\end{equation}
\begin{equation}
g_{\phi\phi}=e^{2\psi}=\frac{f}{\chi^2}=\Delta\left(1-\mu\right)^2
\end{equation}
