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
ds^2=g_{tt}dt^2+g_{rr}dr^2+R^2g_{\theta\theta}d\theta^2+R^2g_{\phi\phi}d\phi^2
\end{equation}
which we rewrite as
\begin{equation}
ds^2=-e^{2\nu}dt^2+e^{2\mu_2}dr^2+R^2e^{2\mu_3}d\theta^2+R^2e^{2\psi}d\phi^2
\end{equation}
where $$\nu$$, $$\mu_2$$, $$\mu_3$$, and $$\psi$$ are dimensionless functions of $$\frac{r}{R}$$ and $$\theta$$. $$R$$ is a constant with units of length needed to restore dimensions.

Now the Ricci tensor has five nonzero elements, of which $$R_{00}$$ and $$R_{33}$$ are of interest. Setting these to zero yields
\begin{equation}
R_{00}=0\rightarrow R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu+\mu_3-\mu_2\right)\partial_r\nu+\partial_r^2\nu\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu+\mu_2-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\nu\right)=0
\end{equation}
\begin{equation}
R_{33}=0\rightarrow R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu+\mu_3-\mu_2\right)\partial_r\psi+\partial_r^2\psi\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu+\mu_2-\mu_3\right)\partial_\theta\psi+\partial_\theta^2\psi\right)=0
\end{equation}
The important components of the Einstein tensor are $$G_{22}$$ and $$G_{33}$$.
\begin{equation}
G_{22}=e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\mu_2\right)\partial_\theta\nu+\partial_\theta\mu_2\partial_\theta\psi\right)+R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu-\mu_2\right)\partial_r\nu+\partial_r^2\left(\nu+\psi\right)+\partial_r\left(\psi-\mu_2\right)\partial_r\psi\right)=0
\end{equation}
\begin{equation}
G_{33}=R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\mu_3\right)\partial_r\nu+\partial_r\mu_3\partial_r\psi\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\left(\nu+\psi\right)+\partial_\theta\left(\psi-\mu_3\right)\partial_\theta\psi\right)=0
\end{equation}
Our solution, with four unknowns $$\nu$$, $$\mu_2$$, $$\mu_3$$, and $$\psi$$ will solve these from the four equations $$R_{00}=0$$, $$R_{33}=0$$, $$G_{22}=0$$, and $$G_{33}=0$$. 
Now define $$\beta=\psi+\nu$$, and calculating the difference of $$G_{33}$$ and $$G_{22}$$
\begin{equation}
R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\nu-\mu_2-\mu_3\right)\partial_r\nu+\partial_r^2\beta+\partial_r\left(\psi-\mu_2-\mu_3\right)\partial_r\psi\right)-e^{\mu_2-\mu_3}\left(\partial_\theta\left(\nu-\mu_2-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\beta+\partial_\theta\left(\psi-\mu_2-\mu_3\right)\partial_\theta\psi\right)=0
\end{equation}
which we rewrite as
\begin{equation}\label{long beta eq}
R^2e^{-\beta}\left(\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\beta\right)-\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\beta\right)\right)=2R^2e^{\mu_3-\mu_2}\left(\partial_r\beta\partial_r\mu_3+\partial_r\psi\partial_r\nu\right)-2e^{\mu_2-\mu_3}\left(\partial_\theta\beta\partial_\theta\mu_2+\partial_\theta\psi\partial_\theta\nu\right)
\end{equation}
We can rewrite $$R_{00}$$ and $$R_{33}$$ as
\begin{equation}
0=R^2\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\nu\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\nu\right)
\end{equation}
\begin{equation}
0=R^2\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\psi\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\psi\right)
\end{equation}
and adding and subtracting these two equations
\begin{equation}\label{beta eq 1}
0=R^2\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\beta\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\beta\right)
\end{equation}
\begin{equation}\label{beta eq 2}
0=R^2\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\left(\nu-\psi\right)\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\left(\nu-\psi\right)\right)
\end{equation}
Defining $$\chi=e^{\nu-\psi}$$, we obtain
\begin{equation}
0=R^2\partial_r\left(e^{3\psi-\nu+\mu_3-\mu_2}\partial_r\left(\chi^2\right)\right)+\partial_\theta\left(e^{3\psi-\nu+\mu_2-\mu_3}\partial_\theta\left(\chi^2\right)\right)
\end{equation}

Now we now there exists a null surface $$N(r,\theta)$$ such that $$g^{\nu\mu}N_\nu N_\mu=0$$. For our ansatz, this reduces to
\begin{equation}
R^2e^{2\mu_3-2\mu_2}\left(\partial_rN\right)^2+\left(\partial_\theta N\right)^2=0
\end{equation}
Now we chose $$e^{2\mu_3-2\mu_2}=\Delta\left(r\right)$$, and seperate $$e^\beta=\sqrt{\Delta(r)}f(\theta)$$. Inserting these two functions into \ref{beta eq 1}
\begin{equation}
0=R^2\frac{f}{2}\partial_r^2\Delta+\partial_\theta^2f
\end{equation}
This is solved by $$\partial_r^2\Delta=\frac{2}{R^2}$$ and $$f=\sin\left(\theta\right)$$. Introducing dimensionless constants $$M$$ and $$a$$, we write $$\Delta=\frac{r^2}{R^2}+a^2-2M\frac{r}{R}$$.

Using our solutions
\begin{equation}
e^{\mu_3-\mu_2}=\sqrt{\Delta}\quad e^\beta=\sqrt{\Delta\delta}
\end{equation}
with $$\mu=\cos\left(\theta\right)$$ and $$\delta=1-\mu^2=\sin^2\left(\theta\right)$$. Note that $$\partial_\theta=-\sqrt{\delta}\partial_\mu$$. Now writing \ref{beta eq 2}
\begin{equation}
0=R^2\partial_r\left(\Delta\partial_r\left(\nu-\psi\right)\right)+\partial_\mu\left(\delta\partial_\mu\left(\nu-\psi\right)\right)
\end{equation}
which we can express as
\begin{equation}\label{partial Delta and chi eq}
0=R^2\partial_r\left(\frac{\Delta}{\chi}\partial_r\chi\right)+\partial_\mu\left(\frac{\delta}{\chi}\partial_\mu\chi\right)
\end{equation}
\begin{equation}
\rightarrow
\chi\left(R^2\partial_r\left(\Delta\partial_r\chi\right)+\partial_\mu\left(\delta\partial_\mu\chi\right)\right)=R^2\Delta\left(\partial_r\chi\right)^2+\delta\left(\partial_\mu\chi\right)^2
\end{equation}
We can also write \ref{long beta eq} with these new definitions
\begin{equation}
\frac{1}{2}\left(R^2\partial_r^2\Delta-\partial_\mu^2\delta\right)=R^2\partial_r\Delta\partial_r\mu_3+2R^2\Delta\partial_r\psi\partial_r\nu-\partial_\mu\delta\partial_\mu\mu_2-2\delta\partial_\mu\psi\partial_\mu\nu
\end{equation}
Now using $$\partial_r\Delta=2$$ and $$\partial_\mu\delta=-2$$
\begin{equation}\label{intermediate 2= eq}
2=R^2\partial_r\Delta\partial_r\mu_3+2R^2\Delta\partial_r\psi\partial_r\nu-\partial_\mu\delta\partial_\mu\mu_2-2\delta\partial_\mu\psi\partial_\mu\nu
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
2=R^2\partial_r\Delta\partial_r\mu_3-\partial_\mu\delta\partial_\mu\mu_2+R^2\frac{\Delta}{2}\left(\frac{1}{2\Delta}\partial_r\Delta-\frac{1}{\chi}\partial_r\chi\right)\left(\frac{1}{2\Delta}\partial_r\Delta+\frac{1}{\chi}\partial_r\chi\right)-\frac{\delta}{2}\left(\frac{1}{2\delta}\partial_\mu\delta-\frac{1}{\chi}\partial_\mu\chi\right)\left(\frac{1}{2\delta}\partial_\mu\delta+\frac{1}{\chi}\partial_\mu\chi\right)
\end{equation}
\begin{equation}
2=R^2\partial_r\Delta\partial_r\mu_3-\partial_\mu\delta\partial_\mu\mu_2+\frac{R^2}{8\Delta}\left(\partial_r\Delta\right)^2-\frac{1}{8\delta}\left(\partial_\mu\delta\right)^2+\frac{\delta}{2\chi^2}\left(\partial_\mu\chi\right)^2-\frac{\Delta}{2\chi^2}\left(\partial_r\chi\right)^2
\end{equation}
With $$\partial_r\Delta=\frac{2}{R}\left(\frac{r}{R}-M\right)$$ and $$\partial_\mu\delta=-2\mu$$
\begin{equation}
2=2R\left(\frac{r}{R}-M\right)\partial_r\mu_3+2\mu\partial_\mu\mu_2+\frac{1}{2\Delta}\left(\frac{r}{R}-M\right)^2-\frac{1}{2\delta}\mu^2+\frac{1}{2\chi^2}\left(\delta\left(\partial_\mu\chi\right)^2-R^2\Delta\left(\partial_r\chi\right)^2\right)
\end{equation}
We now observe $$\partial_r\left(\mu_3-\mu_2\right)=\partial_r\log\left(\sqrt{\Delta}\right)=\frac{1}{R}\left(\frac{r}{R}-M\right)\Delta^{-1}$$ and $$\partial_\mu\left(\mu_2-\mu_3\right)=-\partial_\mu\log\left(\sqrt{\Delta}\right)=0$$, so
\begin{equation}
2=R\left(\frac{r}{R}-M\right)\partial_r\left(\mu_2+\mu_3\right)+R\left(\frac{r}{R}-M\right)\partial_r\left(\mu_3-\mu_2\right)+\mu\partial_\mu\left(\mu_2+\mu_3\right)+\mu\partial_\mu\left(\mu_2-\mu_3\right)+\frac{1}{2\Delta}\left(\frac{r}{R}-M\right)^2-\frac{1}{2\delta}\mu^2+\frac{1}{2\chi^2}\left(\delta\left(\partial_\mu\chi\right)^2-R^2\Delta\left(\partial_r\chi\right)^2\right)
\end{equation}
\begin{equation}
2=\left(R\left(\frac{r}{R}-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)+\frac{3}{2\Delta}\left(\frac{r}{R}-M\right)^2-\frac{1}{2\delta}\mu^2+\frac{1}{2\chi^2}\left(\delta\left(\partial_\mu\chi\right)^2-R^2\Delta\left(\partial_r\chi\right)^2\right)
\end{equation}
And simplifying further with $$\mu^2=1-\delta$$ and $$(\frac{r}{R}-M)^2=\Delta+M^2-a^2$$
\begin{equation}\label{chi^2 master eq}
2\left(R\left(\frac{r}{R}-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)-\frac{1}{\chi^2}\left(R^2\Delta\left(\partial_r\chi\right)^2-\delta\left(\partial_\mu\chi\right)^2\right)+3\frac{M^2-a^2}{\Delta}-\frac{1}{\delta}=0
\end{equation}

We next define $$f=e^{2\nu}=e^\beta\chi=\sqrt{\Delta\delta}\chi$$. Writing \ref{partial Delta and chi eq} in terms of $$f$$
\begin{equation}
0=R^2\partial_r\left(\frac{\Delta}{f}\partial_rf\right)+\partial_\mu\left(\frac{\delta}{f}\partial_\mu f\right)
\end{equation}
\begin{equation}
R^2\frac{\Delta}{f}\left(\partial_rf\right)^2+\frac{\delta}{f}\left(\partial_\mu f\right)^2=R^2\partial_r\left(\Delta\partial_rf\right)+\partial_\mu\left(\delta\partial_\mu f\right)
\end{equation}
This equation is easier to solve if we make the change of variable
\begin{equation}
f=\frac{1+\epsilon}{1-\epsilon}
\end{equation}
We know note that $$f\in\mathcal{R}$$, so $$\Im\left(\epsilon\right)=0$$.
with $$\partial_r f=\frac{2}{\left(1-\epsilon\right)^2}\partial_r\epsilon$$
\begin{equation}
\frac{4R^2}{1-\epsilon^2}\left(\Delta\left(\partial_r\epsilon\right)^2+\delta\left(\partial_\mu\epsilon\right)^2\right)=\frac{4R^2}{1-\epsilon}\left(\Delta\left(\partial_r\epsilon\right)^2+\delta\left(\partial_\mu\epsilon\right)^2\right)+2R^2\left(\partial_r\left(\Delta\partial_r\epsilon\right)+\partial_\mu\left(\delta\partial_\mu\epsilon\right)\right)
\end{equation}
\begin{equation}
-2R^2\epsilon\left(\Delta\left(\partial_r\epsilon\right)^2+\delta\left(\partial_\mu\epsilon\right)^2\right)=R^2\left(1-\epsilon^2\right)\left(\partial_r\left(\Delta\partial_r\epsilon\right)+\partial_\mu\left(\delta\partial_\mu\epsilon\right)\right)
\end{equation}
Now define $$\eta^2=\frac{\left(\frac{r}{R}-M\right)^2}{M^2-a^2}=\frac{\Delta}{M^2-a^2}+1$$, $$\partial_r=\frac{1}{R}\frac{1}{\sqrt{M^2-a^2}}\partial_\eta$$ and with $$\delta=1-\mu^2$$
\begin{equation}
-2\epsilon\left(\left(\eta^2-1\right)\left(\partial_\eta\epsilon\right)^2+\left(1-\mu^2\right)\left(\partial_\mu\epsilon\right)^2\right)=\left(1-\epsilon^2\right)\left(\partial_\eta\left(\left(\eta^2-1\right)\partial_\eta\epsilon\right)+\partial_\mu\left(\left(1-\mu^2\right)\partial_\mu\epsilon\right)\right)
\end{equation}
this equation is solved by $$\epsilon=\pm\eta$$ and $$\epsilon=\pm\mu$$.

First let's consider $$\epsilon=\mu$$, from which we have $$f=\frac{1+\mu}{1-\mu}$$. This results in the $$tt$$ component of the metric
\begin{equation}
g_{tt}=-e^{2\nu}=-f=-\frac{1+\mu}{1-\mu}
\end{equation}
In the limit of $$M\rightarrow0$$ and $$a\rightarrow0$$, we expect the metric to be Minkowskian with $$g_{tt}=-1$$, and if we use $$\epsilon=\pm\mu$$, this limit is not recovered. 

Now, let's instead use $$\epsilon=\eta$$. Simplifying, this yields
\begin{equation}
f=\frac{1-\eta}{1+\eta}=-\frac{\Delta}{\rho^2}
\end{equation}
With $$\rho=\left(\frac{r}{R}-M\right)+\sqrt{a^2-M^2}$$

Now employing \ref{chi^2 master eq}, and using $$\chi=-\sqrt{\frac{\Delta}{\delta}}\frac{1}{\rho^2}$$
\begin{equation}
-\frac{1}{\chi^2}\left(R^2\Delta\left(\partial_r\chi\right)^2-\delta\left(\partial_\mu\chi\right)^2\right)=-4\frac{\Delta}{\rho^2}-\frac{\left(\frac{r}{R}-M\right)^{2}}{\Delta}+4\frac{\left(\frac{r}{R}-M\right)}{\rho}+\frac{\mu^2}{1-\mu^2}
\end{equation}
\begin{equation}
\left(R\left(\frac{r}{R}-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)=\frac{\Delta}{\rho^2}-\frac{\left(\frac{r}{R}-M\right)^{2}}{\Delta}+1
\end{equation}
From which we obtain
\begin{equation}
\left(\mu_2+\mu_3\right)=\log\left(\frac{\rho^2}{\sqrt{\Delta}}\right)+C
\end{equation}
where $$C$$ is an arbitrary function of $$\frac{\frac{r}{R}-M}{\mu}$$.

We are now ready to assemble all components of the metric tensor
\begin{equation}
g_{tt}=-e^{2\nu}=-\chi e^\beta=\frac{\Delta}{\rho^2}
\end{equation}
\begin{equation}
g_{rr}=e^{2\mu_2}=e^{\mu_2+\mu_3}e^{\mu_2-\mu_3}=C\frac{\rho^2}{\Delta}
\end{equation}
\begin{equation}
g_{\theta\theta}=R^2e^{2\mu_3}=R^2e^{\mu_2+\mu_3}e^{\mu_3-\mu_2}=CR^2\rho^2
\end{equation}
\begin{equation}
g_{\phi\phi}=R^2e^{2\psi}=R^2e^\beta\chi^{-1}=-R^2\delta\rho^2
\end{equation}
Now with a simple change of coordinates we can relate this metric to the usual Schwarzschild metric, observing that $$\Delta=\rho^2-2\rho\sqrt{M^2-a^2}$$
\begin{equation}
ds^2=\left(1-\frac{2\sqrt{M^2-a^2}}{\rho}\right)dt^2+C\left(1-\frac{2\sqrt{M^2-a^2}}{\rho}\right)^{-1}dr^2+CR^2\rho^2d\theta^2-R^2\rho^2\sin^2(\theta)d\phi^2
\end{equation}
Now changing our coordiantes $$r\rightarrow R\rho$$ and defining an effective mass $$M\rightarrow\sqrt{M^2-a^2}R$$, and setting $$C=-1$$ to recover Minkowskian spacetime in the limit of $$M\rightarrow0$$, we obtain 
\begin{equation}
ds^2=\left(1-\frac{2M}{r}\right)dt^2-\left(1-\frac{2M}{r}\right)^{-1}dr^2-r^2d\theta^2-r^2\sin^2(\theta)d\phi^2
\end{equation}
And we have arrived at the Schwarzschild metric.

## II. The Kerr Solution
Our derivation of the Schwarzschild metric was not the simplest or most straightforward approach. We took this approach because it closely parallels the more complex derivation of the Kerr metric. In this case, our line element is identical to our spherically symmetric solution, except we allow the off-diagonal term $$g_{t\phi}$$.
\begin{equation}
ds^2=g_{tt}dt^2+Rg_{t\phi}dtd\phi+g_{rr}dr^2+R^2g_{\theta\theta}d\theta^2+R^2g_{\phi\phi}d\phi^2
\end{equation}
$$g_{t\phi}$$ will introduce a new unkown into our equations, and we write
\begin{equation}
ds^2=\left(-e^{2\nu}+\omega^2e^{2\psi}\right)dt^2-2R\omega e^{2\psi}dtd\phi^2+e^{2\mu_2}dr^2+R^2e^{2\mu_3}d\theta^2+R^2e^{2\psi}d\phi^2
\end{equation}
where $$\nu$$, $$\mu_2$$, $$\mu_3$$, $$\omega$$ and $$\psi$$ are dimensionless functions of $$\frac{r}{R}$$ and $$\theta$$. We will once again employ $$R$$ to restore dimensions.

Proceeding as we did previously, calculating $$R_{00}$$ and $$R_{33}$$
\begin{equation}
R_{00}=0\rightarrow R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu+\mu_3-\mu_2\right)\partial_r\nu+\partial_r^2\nu\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu+\mu_2-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\nu\right)-\frac{1}{2}e^{2\psi-2\nu}\left(R^2e^{\mu_3-\mu_2}\left(\partial_r\omega\right)^2+e^{\mu_2-\mu_3}\left(\partial_\theta\omega\right)^2\right)=0
\end{equation}
\begin{equation}
R_{33}=0\rightarrow R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu+\mu_3-\mu_2\right)\partial_r\psi+\partial_r^2\psi\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu+\mu_2-\mu_3\right)\partial_\theta\psi+\partial_\theta^2\psi\right)+\frac{1}{2}e^{2\psi-2\nu}\left(R^2e^{\mu_3-\mu_2}\left(\partial_r\omega\right)^2+e^{\mu_2-\mu_3}\left(\partial_\theta\omega\right)^2\right)=0
\end{equation}
We will also use $$R_{03}$$ to resolve $$\omega$$
\begin{equation}\label{omega eq}
R_{03}=0\rightarrow R^2\partial_r\left(e^{3\psi-\nu+\mu_3-\mu_2}\partial_r\omega\right)+\partial_\theta\left(e^{3\psi-\nu+\mu_2-\mu_3}\partial_\theta\omega\right)=0
\end{equation}
Proceeding with $$G_{22}$$ and $$G_{33}$$
\begin{equation}
G_{22}=e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\mu_2\right)\partial_\theta\nu+\partial_\theta\mu_2\partial_\theta\psi\right)+R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\nu-\mu_2\right)\partial_r\nu+\partial_r^2\left(\nu+\psi\right)+\partial_r\left(\psi-\mu_2\right)\partial_r\psi\right)-\frac{1}{4}e^{2\psi-2\nu}\left(R^2e^{\mu_3-\mu_2}\left(\partial_r\omega\right)^2-e^{\mu_2-\mu_3}\left(\partial_\theta\omega\right)^2\right)=0
\end{equation}
\begin{equation}
G_{33}=R^2e^{\mu_3-\mu_2}\left(\partial_r\left(\psi+\mu_3\right)\partial_r\nu+\partial_r\mu_3\partial_r\psi\right)+e^{\mu_2-\mu_3}\left(\partial_\theta\left(\psi+\nu-\mu_3\right)\partial_\theta\nu+\partial_\theta^2\left(\nu+\psi\right)+\partial_\theta\left(\psi-\mu_3\right)\partial_\theta\psi\right)+\frac{1}{4}e^{2\psi-2\nu}\left(R^2e^{\mu_3-\mu_2}\left(\partial_r\omega\right)^2-e^{\mu_2-\mu_3}\left(\partial_\theta\omega\right)^2\right)=0
\end{equation}
As we did previously, adding and subtracting $$R_{00}$$ and $$R_{33}$$ and writing $$\beta=\psi+\nu$$
\begin{equation}
0=R^2\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\beta\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\beta\right)
\end{equation}
\begin{equation}\label{add R00 R33 eq}
e^{3\psi-\nu}X=R^2\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\left(\nu-\psi\right)\right)+\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\left(\nu-\psi\right)\right)
\end{equation}
Where
\begin{equation}
X=R^2e^{\mu_3-\mu_2}\left(\partial_r\omega\right)^2+e^{\mu_2-\mu_3}\left(\partial_\theta\omega\right)^2
\end{equation}
We can also use $$R_{03}=0$$ to find
\begin{equation}\label{R03 eq}
e^{3\psi-\nu}X=R^2\partial_r\left(e^{3\psi-\nu+\mu_3-\mu_2}\omega\partial_r\omega\right)+\partial_\theta\left(e^{3\psi-\nu+\mu_2-\mu_3}\omega\partial_\theta\omega\right)
\end{equation}
Inserting \ref{R03 eq} into \ref{add R00 R33 eq}
\begin{equation}
R^2\partial_r\left(e^{3\psi-\nu+\mu_3-\mu_2}\left(e^{2\nu-2\psi}\partial_r\left(\psi-\nu\right)+\frac{1}{2}\partial_r\left(\omega^2\right)\right)\right)+\partial_\theta\left(e^{3\psi-\nu+\mu_2-\mu_3}\left(e^{2\nu-2\psi}\partial_\theta\left(\psi-\nu\right)+\frac{1}{2}\partial_\theta\left(\omega^2\right)\right)\right)=0
\end{equation}
And once again defining $$\chi=e^{\nu-\psi}$$
\begin{equation}\label{chi^2-omega^2 eq}
0=R^2\partial_r\left(e^{3\psi-\nu+\mu_3-\mu_2}\partial_r\left(\chi^2-\omega^2\right)\right)+\partial_\theta\left(e^{3\psi-\nu+\mu_2-\mu_3}\partial_\theta\left(\chi^2-\omega^2\right)\right)
\end{equation}
Comparing \ref{chi^2-omega^2 eq} with \ref{omega eq} we see that both $$\omega$$ and $$\chi^2-\omega^2$$ are determined by the same equation. Finally, taking the difference of $$G_{22}$$ and $$G_{33}$$ and using $$\beta$$, we have
\begin{equation}\label{long beta eq kerr}
R^2e^{-\beta}\left(\partial_r\left(e^{\beta+\mu_3-\mu_2}\partial_r\beta\right)-\partial_\theta\left(e^{\beta+\mu_2-\mu_3}\partial_\theta\beta\right)\right)=2R^2e^{\mu_3-\mu_2}\left(\partial_r\beta\partial_r\mu_3+\partial_r\psi\partial_r\nu\right)-2e^{\mu_2-\mu_3}\left(\partial_\theta\beta\partial_\theta\mu_2+\partial_\theta\psi\partial_\theta\nu\right)+\frac{1}{2}e^{2\psi-2\nu}\left(R^2e^{\mu_3-\mu_2}\left(\partial_r\omega\right)^2-e^{\mu_2-\mu_3}\left(\partial_\theta\omega\right)^2\right)
\end{equation}

Now, using the same null surface argument we did previously, we write
\begin{equation}
e^\beta=\sqrt{\Delta\delta}\quad e^{\mu_3-\mu_2}=\sqrt{\Delta}
\end{equation}
with $$\Delta=r^2+a^2-2Mr$$, $$\delta=\sin^2\left(\theta\right)=1-\mu^2$$. We substitute these solutions to obtain
\begin{equation}
X=R^2\sqrt{\Delta}\left(\partial_r\omega\right)^2+\frac{\delta}{\sqrt{\Delta}}\left(\partial_\mu\omega\right)^2
\end{equation}
We can rewrite \ref{omega eq} and \ref{add R00 R33 eq}
\begin{equation}
R^2\partial_r\left(e^{2\psi-2\nu}\Delta\partial_r\omega\right)+\partial_\mu\left(e^{2\psi-2\nu}\delta\partial_\mu\omega\right)=0
\end{equation}
\begin{equation}
e^{2\psi-2\nu}\left(R^2\Delta\left(\partial_r\omega\right)^2+\delta\left(\partial_\mu\omega\right)^2\right)=R^2\partial_r\left(\Delta\partial_r\left(\nu-\psi\right)\right)+\partial_\mu\left(\delta\partial_\mu\left(\nu-\psi\right)\right)
\end{equation}
which we reexpress as
\begin{equation}\label{chi eq 1 form 1}
R^2\partial_r\left(\frac{\Delta}{\chi^2}\partial_r\omega\right)+\partial_\mu\left(\frac{\delta}{\chi^2}\partial_\mu\omega\right)=0
\end{equation}
\begin{equation}\label{chi eq 1}
\rightarrow 2\left(R^2\Delta\partial_r\chi\partial_r\omega+\delta\partial_\mu\chi\partial_\mu\omega\right)=\chi\left(R^2\partial_r\left(\Delta\partial_r\omega\right)+\partial_\mu\left(\delta\partial_\mu\omega\right)\right)
\end{equation}
\begin{equation}\label{chi eq 2 form 1}
\frac{1}{\chi^2}\left(R^2\Delta\left(\partial_r\omega\right)^2+\delta\left(\partial_\mu\omega\right)^2\right)=R^2\partial_r\left(\frac{\Delta}{\chi}\partial_r\chi\right)+\partial_\mu\left(\frac{\delta}{\chi}\partial_\mu\chi\right)
\end{equation}
\begin{equation}\label{chi eq 2}
\rightarrow
R^2\Delta\left(\partial_r\omega\right)^2+\delta\left(\partial_\mu\omega\right)^2+R^2\Delta\left(\partial_r\chi\right)^2+\delta\left(\partial_\mu\chi\right)^2=\chi\left(R^2\partial_r\left(\Delta\partial_r\chi\right)+\partial_\mu\left(\delta\partial_\mu\chi\right)\right)
\end{equation}
Now we define $$\mathcal{A}=\chi+\omega$$ and $$\mathcal{B}=\chi-\omega$$, noting that $$\mathcal{A}\mathcal{B}=\chi^2-\omega^2$$ and rewrite \ref{chi eq 1} and \ref{chi eq 2}
\begin{equation}
2\left(R^2\Delta\left(\partial_r\mathcal{A}\right)^2-R^2\Delta\left(\partial_r\mathcal{B}\right)^2+\delta\left(\partial_\mu\mathcal{A}\right)^2-\delta\left(\partial_\mu\mathcal{B}\right)^2\right)=\left(\mathcal{A}+\mathcal{B}\right)\left(R^2\partial_r\left(\Delta\left(\partial_r\mathcal{A}\right)\right)-R^2\partial_r\left(\Delta\left(\partial_r\mathcal{B}\right)\right)+\partial_\mu\left(\delta\left(\partial_\mu\mathcal{A}\right)\right)-\partial_\mu\left(\delta\left(\partial_\mu\mathcal{B}\right)\right)\right)
\end{equation}
\begin{equation}
2\left(R^2\Delta\left(\partial_r\mathcal{A}\right)^2+R^2\Delta\left(\partial_r\mathcal{B}\right)^2+\delta\left(\partial_\mu\mathcal{A}\right)^2+\delta\left(\partial_\mu\mathcal{B}\right)^2\right)=\left(\mathcal{A}+\mathcal{B}\right)\left(R^2\partial_r\left(\Delta\left(\partial_r\mathcal{A}\right)\right)+R^2\partial_r\left(\Delta\left(\partial_r\mathcal{B}\right)\right)+\partial_\mu\left(\delta\left(\partial_\mu\mathcal{A}\right)\right)+\partial_\mu\left(\delta\left(\partial_\mu\mathcal{B}\right)\right)\right)
\end{equation}
and adding and subtracting these two
\begin{equation}\label{A master eq}
R^2\Delta\left(\partial_r\mathcal{A}\right)^2+\delta\left(\partial_\mu\mathcal{A}\right)^2=\frac{1}{2}\left(\mathcal{A}+\mathcal{B}\right)\left(R^2\partial_r\left(\Delta\left(\partial_r\mathcal{A}\right)\right)+\partial_\mu\left(\delta\left(\partial_\mu\mathcal{A}\right)\right)\right)
\end{equation}
\begin{equation}\label{B master eq}
R^2\Delta\left(\partial_r\mathcal{B}\right)^2+\delta\left(\partial_\mu\mathcal{B}\right)^2=\frac{1}{2}\left(\mathcal{A}+\mathcal{B}\right)\left(R^2\partial_r\left(\Delta\left(\partial_r\mathcal{B}\right)\right)+\partial_\mu\left(\delta\left(\partial_\mu\mathcal{B}\right)\right)\right)
\end{equation}
Furthermore, since we know \ref{chi eq 1 form 1} is satisfied by both $$\omega$$ and $$\chi^2-\omega^2$$ (via comparing \ref{chi^2-omega^2 eq} with \ref{omega eq}), \ref{chi eq 1} is also satisfied by $$\chi^2-\omega^2=\mathcal{A}\mathcal{B}$$
\begin{equation}
2\left(R^2\Delta\partial_r\chi\partial_r\left(\mathcal{A}\mathcal{B}\right)+\delta\partial_\mu\chi\partial_\mu\left(\mathcal{A}\mathcal{B}\right)\right)=\chi\left(R^2\partial_r\left(\Delta\partial_r\left(\mathcal{A}\mathcal{B}\right)\right)+\partial_\mu\left(\delta\partial_\mu\left(\mathcal{A}\mathcal{B}\right)\right)\right)
\end{equation}

With our definitions we now rewrite \ref{long beta eq kerr}
\begin{equation}
\frac{1}{2}\left(R^2\partial_r^2\Delta-\partial_\mu^2\delta\right)=R^2\partial_r\Delta\partial_r\mu_3+2R^2\Delta\partial_r\psi\partial_r\nu-\partial_\mu\delta\partial_\mu\mu_2-2\delta\partial_\mu\psi\partial_\mu\nu+\frac{1}{2\chi^2}\left(R^2\Delta\left(\partial_r\omega\right)^2-\delta\left(\partial_\mu\omega\right)^2\right)
\end{equation}
As we did previously, with our solutions for $$\partial_r\psi$$, $$\partial_\mu\psi$$, $$\partial_\nu\psi$$, and $$\partial_\nu\psi$$
\begin{equation}
2=R^2\partial_r\Delta\partial_r\mu_3-\partial_\mu\delta\partial_\mu\mu_2+R^2\frac{\Delta}{2}\left(\frac{1}{2\Delta}\partial_r\Delta-\frac{1}{\chi}\partial_r\chi\right)\left(\frac{1}{2\Delta}\partial_r\Delta+\frac{1}{\chi}\partial_r\chi\right)-\frac{\delta}{2}\left(\frac{1}{2\delta}\partial_\mu\delta-\frac{1}{\chi}\partial_\mu\chi\right)\left(\frac{1}{2\delta}\partial_\mu\delta+\frac{1}{\chi}\partial_\mu\chi\right)+\frac{1}{8\chi^2}\left(R^2\Delta\left(\partial_r\left(\mathcal{A}-\mathcal{B}\right)\right)^2-\delta\left(\partial_\mu\left(\mathcal{A}-\mathcal{B}\right)\right)^2\right)
\end{equation}
Again, following our past work and inserting $$\mathcal{A}$$ and $$\mathcal{B}$$
\begin{equation}
2=\left(R\left(\frac{r}{R}-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)+\frac{3}{2\Delta}\left(\frac{r}{R}-M\right)^2-\frac{1}{2\delta}\mu^2-\frac{1}{8\chi^2}\left(R^2\Delta\left(\partial_r\left(\mathcal{A}+\mathcal{B}\right)\right)^2+\delta\left(\partial_\mu\left(\mathcal{A}-\mathcal{B}\right)\right)^2\right)+\frac{1}{8\chi^2}\left(R^2\Delta\left(\partial_r\left(\mathcal{A}-\mathcal{B}\right)\right)^2-\delta\left(\partial_\mu\left(\mathcal{A}-\mathcal{B}\right)\right)^2\right)
\end{equation}
\begin{equation}
2=\left(R\left(\frac{r}{R}-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)+\frac{3}{2\Delta}\left(\frac{r}{R}-M\right)^2-\frac{1}{2\delta}\mu^2-\frac{1}{2\chi^2}\left(R^2\Delta\partial_r\mathcal{A}\partial_r\mathcal{B}-\delta\partial_\mu\mathcal{A}\partial_\mu\mathcal{B}\right)
\end{equation}
To arrive at
\begin{equation}\label{mu_2+mu_3 master eq}
2\left(R\left(\frac{r}{R}-M\right)\partial_r+\mu\partial_\mu\right)\left(\mu_2+\mu_3\right)-\frac{1}{2\chi^2}\left(R^2\Delta\partial_r\mathcal{A}\partial_r\mathcal{B}-\delta\partial_\mu\mathcal{A}\partial_\mu\mathcal{B}\right)+3\frac{M^2-a^2}{\Delta}-\frac{1}{\delta}=0
\end{equation}
Our remaining task is to solve the symmetric \label{A master eq} and \label{B master eq} after which we solve for $$\mu_2+\mu_3$$ using \ref{mu_2+mu_3 master eq}.

Now, we will define
\begin{equation}
\mathcal{W}=\frac{\mathcal{A}-\mathcal{B}}{2\mathcal{A}\mathcal{B}}=\frac{\omega}{\chi^2-\omega^2}\quad\mathcal{Y}=\mathcal{A}\mathcal{B}e^{2\psi}=\sqrt{\Delta\delta}\frac{\chi^2-\omega^2}{\chi}
\end{equation}
Now consider
\begin{equation}
R^2\partial_r\left(\frac{\mathcal{Y}^2}{\delta}\partial_r\mathcal{W}\right)+\partial_\mu\left(\frac{\mathcal{Y}^2}{\Delta}\partial_\mu\mathcal{W}\right)\label{W function eq 1}
\end{equation}
\begin{equation}
=R^2\partial_r\left(\frac{\Delta}{\chi^2}\left(\mathcal{A}\mathcal{B}\right)^2\left(\frac{1}{\mathcal{A}\mathcal{B}}\partial_r\omega-\frac{\omega}{\left(\mathcal{A}\mathcal{B}\right)^2}\partial_r\left(\mathcal{A}\mathcal{B}\right)\right)\right)+\partial_\mu\left(\frac{\delta}{\chi^2}\left(\mathcal{A}\mathcal{B}\right)^2\left(\frac{1}{\mathcal{A}\mathcal{B}}\partial_\mu\omega-\frac{\omega}{\left(\mathcal{A}\mathcal{B}\right)^2}\partial_\mu\left(\mathcal{A}\mathcal{B}\right)\right)\right)
\end{equation}
\begin{equation}
=R^2\partial_r\left(\frac{\Delta}{\chi^2}\left(\left(\mathcal{A}\mathcal{B}\right)\partial_r\omega-\omega\partial_r\left(\mathcal{A}\mathcal{B}\right)\right)\right)+\partial_\mu\left(\frac{\delta}{\chi^2}\left(\left(\mathcal{A}\mathcal{B}\right)\partial_\mu\omega-\omega\partial_\mu\left(\mathcal{A}\mathcal{B}\right)\right)\right)
\end{equation}
\begin{equation}
=\left(\chi^2-\omega^2\right)\left(R^2\partial_r\left(\frac{\Delta}{\chi^2}\partial_r\omega\right)+\partial_\mu\left(\frac{\delta}{\chi^2}\partial_\mu\omega\right)\right)-\omega\left(R^2\partial_r\left(\frac{\Delta}{\chi^2}\partial_r\left(\chi^2-\omega^2\right)\right)+\partial_\mu\left(\frac{\delta}{\chi^2}\partial_\mu\left(\chi^2-\omega^2\right)\right)\right)=0
\end{equation}
We have used \ref{omega eq} and \ref{chi^2-omega^2 eq}. This implies that we can derive $$\mathcal{W}$$ from a function $$\mathcal{G}$$ with
\begin{equation}
\partial_r\mathcal{G}=\frac{1}{R}\frac{\mathcal{Y}^2}{\Delta}\partial_\mu\mathcal{W}\quad\partial_\mu\mathcal{G}=-R\frac{\mathcal{Y}^2}{\delta}\partial_r\mathcal{W}
\end{equation}
And $$\mathcal{G}$$ obviously satisfies
\begin{equation}\label{potential G function 1}
R^2\partial_r\left(\frac{\Delta}{\mathcal{Y}^2}\partial_r\mathcal{G}\right)+\partial_\mu\left(\frac{\delta}{\mathcal{Y}^2}\partial_\mu\mathcal{G}\right)=0
\end{equation}
Now, consider
\begin{equation}
R^2\partial_r\left(\frac{\Delta}{\mathcal{Y}}\partial_r\mathcal{Y}\right)+\partial_\mu\left(\frac{\delta}{\mathcal{Y}}\partial_\mu\mathcal{Y}\right)
\end{equation}
\begin{equation}
=R^2\partial_r\left(\frac{\Delta}{\mathcal{Y}}\left(\frac{\sqrt{\Delta\delta}}{\chi}\partial_r\left(\mathcal{A}\mathcal{B}\right)+\mathcal{A}\mathcal{B}\partial_r\left(\frac{\sqrt{\Delta\delta}}{\chi}\right)\right)\right)+\partial_\mu\left(\frac{\delta}{\mathcal{Y}}\left(\frac{\sqrt{\Delta\delta}}{\chi}\partial_\mu\left(\mathcal{A}\mathcal{B}\right)+\mathcal{A}\mathcal{B}\partial_\mu\left(\frac{\sqrt{\Delta\delta}}{\chi}\right)\right)\right)
\end{equation}
\begin{equation}
=R^2\partial_r\left(\frac{\sqrt{\Delta}\chi}{\mathcal{A}\mathcal{B}}\left(\frac{\sqrt{\Delta}}{\chi}\partial_r\left(\mathcal{A}\mathcal{B}\right)+\mathcal{A}\mathcal{B}\partial_r\left(\frac{\sqrt{\Delta}}{\chi}\right)\right)\right)+\partial_\mu\left(\frac{\sqrt{\delta}\chi}{\mathcal{A}\mathcal{B}}\left(\frac{\sqrt{\delta}}{\chi}\partial_\mu\left(\mathcal{A}\mathcal{B}\right)+\mathcal{A}\mathcal{B}\partial_\mu\left(\frac{\sqrt{\delta}}{\chi}\right)\right)\right)
\end{equation}
\begin{equation}
=R^2\partial_r\left(\frac{\Delta}{\mathcal{A}\mathcal{B}}\partial_r\left(\mathcal{A}\mathcal{B}\right)\right)+\partial_\mu\left(\frac{\delta}{\mathcal{A}\mathcal{B}}\partial_\mu\left(\mathcal{A}\mathcal{B}\right)\right)+R^2\partial_r\left(\sqrt{\Delta}\chi\partial_r\left(\frac{\sqrt{\Delta}}{\chi}\right)\right)+\partial_\mu\left(\sqrt{\delta}\chi\partial_\mu\left(\frac{\sqrt{\delta}}{\chi}\right)\right)
\end{equation}
\begin{equation}
=R^2\partial_r\left(\frac{\Delta}{\mathcal{A}\mathcal{B}}\partial_r\left(\mathcal{A}\mathcal{B}\right)\right)+\partial_\mu\left(\frac{\delta}{\mathcal{A}\mathcal{B}}\partial_\mu\left(\mathcal{A}\mathcal{B}\right)\right)-R^2\partial_r\left(\frac{\sqrt{\Delta}}{\chi}\partial_r\left(\sqrt{\Delta}\chi\right)\right)-\partial_\mu\left(\frac{\sqrt{\delta}}{\chi}\partial_\mu\left(\sqrt{\delta}\chi\right)\right)
\end{equation}
