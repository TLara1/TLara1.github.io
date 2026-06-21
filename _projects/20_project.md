---
layout: page
title: On the Langevin and Fokker-Planck Equations - 6/26
description:
img: 
importance: 6
category: Physics
related_publications: false
toc:
  beginning: true
---

## Introduction
Statistical Mechanics is cool. It's also shockingly useful. It's one of those areas of physics that ends up being helpful for a bunch of other areas and for lots of flavours of applied maths. 

Here we discuss the Langevin (do not ask me to pronounce that word) and then the Fokker-Planck Equations, obtaining the fun result that a system immersed in a fluid that is at equilibrium also tends towards equilibrium. 

## Movement of a Fluid-Immersed Colloid
Consider a colloid of mass $$M$$ with position $$x$$ and momentum $$P$$ immersed in a fluid composed of particles with positions $$q$$ and momenta $p$$. For simplicity, we will treat this problem in one dimension, but our results easily generalise to higher dimensions. In this context, a colloid is essentially just a large particle relative to the particles composing the fluid, where "large" means a length scale of at least three orders of magnitude larger than the fluid particles.

Our Hamiltonian has four sectors. First, the standard description of the colloid motion, an interaction term between the colloid and the fluid, a fluid particle interaction term, and an interaction term between fluid particles,
\begin{equation}
H=\frac{P^2}{2M}+V_{ext}(x)+\sum_iV_{FC}\left(x-q_i\right)+\sum_i\left[\frac{p_i^2}{2m}+V_{ext}\left(q_i\right)\right]+\sum_{i\neq j}V_{FF}\left(q_i-q_j\right).
\end{equation}

This is an extremely general Hamiltonian that is rather unapproachable. We simplify by first assuming that the fluid is equilibrated, such that we may ignore the impact of the external potential on the fluid particles and remove the fluid-fluid interaction terms for the same reason. Here, we have assumed a separation of scales, in that the time it takes the fluid to equilibrate is much shorter than the time describing any of the dynamics of the colloid. We will discuss this equilibrium condition more later.

That leaves the colloid-fluid interactions. In practice, this interaction is rather complicated, but we will assume it can be approximated as a harmonic oscillator. Effectively, we can imagine all the fluid particles attached to the colloid with little springs, interacting with the colloid and oscillating over time. Setting $$m=1$$ for convenience and assuming $$M\gg1$$, the Hamiltonian becomes,
\begin{equation}
H=\frac{P^2}{2M}+V_{ext}(x)+\sum_i\left[\frac{p_i^2}{2}+\frac{\omega_i^2}{2}\left(q_i-x\right)^2\right].
\end{equation}
We can extract equations of motion from this Hamiltonian for the colloid,
\begin{equation}
M\dot{x}=P,\quad\dot{P}=-\partial_xV(x)+\sum_i\omega_i^2\left(q_i-x\right),
\end{equation}
and for the particles,
\begin{equation}
\dot{q}_i=p_i,\quad\dot{p}_i=-\omega_i^2\left(q_i-x\right).
\end{equation}
We will solve the motion of the particles and insert this into the motion of the colloid.

The colloid motion can be expressed as a harmonic oscillator plus a constant driving term,
\begin{equation}\label{eq: q harmonic oscillator equation}
\ddot{q}_i(t)=-\omega_i^2q_i(t)+\omega_i^2 x(t).
\end{equation}
The homogenous solution is straightforward, with a cosine term and a sine term,
\begin{equation}
q_i^H(t)=A_i\cos\left(\omega_i t\right)+B_i\sin\left(\omega_i t\right).
\end{equation}
For the particular solution, we use the Green's function solution,
\begin{equation}
q_i^P(t)=\int_0^tds\ f_i(t-s)x(s).
\end{equation}
Inserting this solution into Eq. \ref{eq: q harmonic oscillator equation}, we find,
\begin{equation}
\ddot{q}_i^P(t)+\omega_i^2q_i^P(t)=f_i(0)\dot{x}(t)+\partial_xf_i(0)x(t)+\int_0^tds\ \left[ \partial_x^2f_i(t-s)-\omega_i^2f_i(t-s) \right]x(s)=\omega_i^2x(t).
\end{equation}
Solving for the Green's function, we see,
\begin{equation}
f_i(t)=\omega_i\sin\left(\omega_i t\right).
\end{equation}
And combining the homogeneous and particular solutions to solve for $$q_i(t)$$,
\begin{equation}
q_i(t)=q_i(0)\cos\left(\omega_i t\right)+\frac{p_i(0)}{\omega_i}\sin\left(\omega_i t\right)+\int_0^tds\ \omega_i\sin\left(\omega_i\left(t-s\right)\right)x(s).
\end{equation}
Via the integral product rule, we note,
\begin{equation}
\int_0^tds\ \omega_i\sin\left(\omega_i\left(t-s\right)\right)x(s)=x(t)-\cos\left(\omega_i\left(t\right)\right)x(0)-\int_0^tds\ \cos\left(\omega_i\left(t-s\right)\right)\dot{x}(s).
\end{equation}

Now computing the colloid motion, first we find,
\begin{equation}
x(t)-q_i(t)=\int_0^tds\ \cos\left(\omega_i\left(t-s\right)\right)\dot{x}(s)+\left(x(0)-q_i(0)\right)\cos\left(\omega_i t\right)-\frac{p_i(0)}{\omega_i}\sin\left(\omega_i t\right).
\end{equation}
We return to our momentum equation of motion for the colloid,
\begin{equation}
\dot{P}(t)=-\partial_xV(x)-\int_0^tds\ \left[\sum_i\omega_i^2\cos\left(\omega_i\left(t-s\right)\right)\dot{x}(s)\right]
\end{equation}
\begin{equation}
+\sum_i\left[\omega_ip_i(0)\sin\left(\omega_i t\right)+\omega_i^2\left(q_i(0)-x(0)\right)\cos\left(\omega_i t\right)\right].\nonumber
\end{equation}
We rewrite in terms of a memory kernel, $$K(t-s)$$ and fluctations depending on the initial condition $$\xi(t)$$,
\begin{equation}\label{eq: kernel form langevin}
\dot{P}(t)=-\partial_xV(x)-\int_0^tds\ K(t-s)\dot{x}(s)+\xi(t),
\end{equation}
with,
\begin{equation}\label{eq: memory kernel definition}
K(t-s)=\sum_i\omega_i^2\cos\left(\omega_i\left(t-s\right)\right),\quad\xi(t)=\sum_i\left[\omega_ip_i(0)\sin\left(\omega_i t\right)+\omega_i^2\left(q_i(0)-x(0)\right)\cos\left(\omega_i t\right)\right].
\end{equation}

This should begin to look at least a little familiar. Now we take a slight deviation to discuss our assumption of the fluid being at equilibrium.

### Simplifying the Fluctuations
We assumed that the fluid is at equilibrium, so at time $$t=0$$ the probability distribution of the fluid position and momenta follows the Boltzmann distribution,
\begin{equation}
\mathcal{P}\left(\{q_i(0),p_i(0)\}\right)\sim\exp\left[-\beta H_{F}\right]=\frac{1}{Z}\exp\left[-\beta\sum_i\left(\frac{p_i(0)^2}{2}+\frac{\omega_i}{2}\left(q_i(0)-x(0)\right)^2\right)\right],
\end{equation}
where $$\beta$$ is the Boltzmann weight. We use $$\sim$$ since we exclude the normalization factors, which are not significant in this calculation. Because the exponential is separable, the global probability distribution is a product of the probability distributions for each position and momentum,
\begin{equation}
\mathcal{P}\left(\{q_i(0),p_i(0)\}\right)\sim\prod_i\mathcal{P}\left(q_i(0)\right)\mathcal{P}\left(p_i(0)\right),
\end{equation}
where
\begin{equation}
\mathcal{P}\left(q_i(0)\right)\sim\exp\left[-\beta\frac{\omega_i^2}{2}\left(q_i(0)-x(0)\right)^2\right],\quad \mathcal{P}\left(p_i(0)\right)\sim\exp\left[-\beta\frac{p_i(0)^2}{2}\right].
\end{equation}

Now the cool bit. Return to our fluctuation term, $$\xi(t)$$. From our probability distributions, we see that $$\xi(t)$$ is the sum of Gaussian Random Variables (GRVs), so $$\xi(t)$$ must also be a GRV. Since $$\xi(t)$$ is linear in $$p_i(0)$$ and $$q_i(0)-x(0)$$, and the mean of those distributions is zero, the mean of $$\xi(t)$$ is identically zero,
\begin{equation}
\langle\xi(t)\rangle=0.
\end{equation}
The covariance is more interesting, consider
\begin{equation}\label{eq: xi covariance}
\langle\xi(t)\xi(t')\rangle=\langle\left(\sum_i\left[\omega_ip_i(0)\sin\left(\omega_i t\right)+\omega_i^2\left(q_i(0)-x(0)\right)\cos\left(\omega_i t\right)\right]\right)\left(\sum_j\left[t\rightarrow t'\right]\right)\rangle,
\end{equation}
where $$\left[t\rightarrow t'\right]$$ schematically refers the same bracketed term with $$t$$ swapped to $$t'$$. This looks spooky but is really not too bad. Firstly, because the momenta for each particle are independent, 
\begin{equation}
\langle p_i(0)p_j(0)\rangle=\langle p_i(0)\rangle\langle p_j(0)\rangle\quad\text{if }i\neq j,
\end{equation}
\begin{equation}
\langle p_i(0)p_i(0)\rangle=\frac{1}{\beta}.
\end{equation}
Similarly, for the positions,
\begin{equation}
\langle \left(q_i(0)-x(0)\right)\left(q_j(0)-x(0)\right)\rangle=\langle q_i(0)-x(0)\rangle\langle q_j(0)-x(0)\rangle\quad\text{if }i\neq j,
\end{equation}
\begin{equation}
\langle \left(q_i(0)-x(0)\right)\left(q_i(0)-x(0)\right)\rangle=\frac{1}{\omega_i^2\beta}.
\end{equation}
So, Eq. \ref{eq: xi covariance} simplifies to,
\begin{equation}
\langle\xi(t)\xi(t')\rangle=\sum_i\frac{\omega_i^2}{\beta}\left[\sin\left(\omega_i t\right)\sin\left(\omega_i t'\right)+\cos\left(\omega_i t\right)\cos\left(\omega_i t'\right)\right].
\end{equation}
This reduces nicely to our memory kernel, Eq. \ref{eq: memory kernel definition}, 
\begin{equation}\label{eq: xi covariance}
\langle\xi(t)\xi(t')\rangle=\sum_i\frac{\omega_i^2}{\beta}\cos\left(\omega_i\left(t-t'\right)\right)=\frac{1}{\beta}K(t-t').
\end{equation}
We have seen that we can express the fluctuations $$\xi(t)$$ as a Gaussian Random Variable with a covariance given by the memory kernel $$K(t-t')$$.

### The Langevin Equation
The final key is in recalling our assumption that the bath relaxation time is much shorter than the timescale associated with the colloid. This allows us to simplify the memory kernel into a delta function, $$K(t-s)\sim\delta(t-s)$$. Physically, we are saying that because the fluid relaxes quickly to equilibrium relative to the colloid, the "memory" contributions of the fluid are negligible, and we can take its impacts to be instantaneous. Letting,
\begin{equation}
K(t-t')=2\gamma\delta\left(t-t'\right),
\end{equation}
the memory term becomes,
\begin{equation}
\int_0^tds\ K(t-s)\dot{x}(s)=\gamma\dot{x}(t).
\end{equation}
After consulting Eq. \ref{eq: kernel form langevin}, we arrive at the Langevin equation,
\begin{equation}\label{eq: langevin equation}
M\ddot{x}=-\partial_xV(x)-\gamma\dot{x}+\sqrt{\frac{2\gamma}{\beta}}\eta(t),
\end{equation}
where $$\eta(t)$$ is a Gaussian random variable with zero mean and delta covariance,
\begin{equation}
\langle\eta(t)\rangle=0,\quad\langle\eta(t)\eta(t')\rangle=\delta(t-t').
\end{equation}
This is neat! We have shown that the motion of a colloid immersed in a fluid follows the usual potential gradient plus drag from moving through the fluid plus random thermal fluctuations. However, we will soon see that \ref{eq: langevin equation} is actually disastrous for doing classical calculus, and we will need a whole new machinery to operate on variables that evolve stochastically.

## Itô Calculus
Let's begin by considering the motion of a variable driven only by random fluctuations,
\begin{equation}\label{eq: ito example variable}
\dot{x}(t)=\eta(t),
\end{equation}
where $$\eta(t)$$ is a GRV as described earlier. We can solve Eq. \ref{eq: ito example variable} formally to find,
\begin{equation}\label{eq: ito example variable}
x(t)=x(0)+\int_0^tds\ \eta(s).
\end{equation}
Then, taking the time derivative of $$x(t)$$,
\begin{equation}
\dot{x}(t)=\lim_{\delta t\rightarrow0}\left[\frac{x\left(t+\delta t\right)-x(t)}{\delta t}\right]=\lim_{\delta t\rightarrow0}\left[\frac{1}{\delta t}\int_{t}^{t+\delta t}ds\ \eta(s)\right]
\end{equation}



### Sources
This derivation largely follows from the lecture notes of my Statistical Dynamics II, 8.08, class taught by Professor Julien Tailleur during the 2026 IAP period.
