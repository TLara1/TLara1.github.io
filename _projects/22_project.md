---
layout: page
title: On the Dirac Equation - 7/26
description:
img: 
importance: 2
category: Physics
related_publications: false
toc:
  beginning: true
---

## Introduction
I was halfway through writing my notes on quantum electrodynamics when I realized I wanted to discuss the Dirac Equation in more depth. So here we are. 

The main idea is that the Schrödinger equation is well and good for non-relativistic quantum mechanics, but since it is not Lorentz invariant, it is inadequate for a relativistic theory. This is troubling unless your name is Paul Dirac and the year is 1928, in which case you decide to invent new math and change the trajectory of the next century of physics research.

As usual, we use $$c=\hbar=1$$ for simplicity.

## Matrix-ifying Schrödinger
The usual Schrödinger equation for a wavefunction $$\psi(\mathbf{x}\right)$$ is,
\begin{equation}
i\partial_t\psi=H\left[\psi\right]=-\partial_i\partial^i\psi+V\left(\mathbf{x}\right)\psi.
\end{equation}
We know our physics should be true in any frame of reference, that is to say, the Schrödinger equation should apply after we perform a Lorentz transform, denoting the transformed coordinates $$\mathbf{x}'$$, and the transformed wavefunction as $$\psi'\left(\mathbf{x}'\right)$$, it should be true that $$i\partial_{t'}\psi'=H'\left[\psi'\right]$$. As we will see, this is not the case.

Consider a Lorentz transform along the $$x$$-direction, the $$x$$ and $$t$$ coordinates change as,
\begin{equation}
t\rightarrow t' = \gamma t - \gamma v x,\quad x\rightarrow x' = \gamma x - \gamma v t,
\end{equation}
where $$\gamma=\left(1-v^2\right)^{-1/2}$$ is the Lorentz factor. In the non-relativistic limit, $$v\ll 1$$, we obtain an ordinary Galilean transform. Under this transform,

The wavefunction $$\psi$$ describes events at points in spacetime. Since it is a scalar, it does not care about our coordinate representation. So, it must be true that the transformed wavefunction at the transformed coordinates is equal to the original wavefunction at the original coordinates, $$\psi'\left(\mathbf{x}'\right)=\psi\left(\mathbf{x}\right)$$. All we are saying is that changing how we choose coordinates to represent events in spacetime should not affect a function of those events. 

For the left-hand side of the Schrödinger equation,
\begin{equation}
i\partial_{t'}\psi'=i\partial_{t'}\psi=i\gamma^{-1}\partial_t\psi-i\gamma^{-1}v^{-1}\partial_x\psi.
\end{equation}
For the right-hand side,
\begin{equation}
-\partial^2_{x'}\psi'+V\psi'=-\partial_{x'}\left(\gamma^{-1}\partial_x\psi - \gamma^{-1}v^{-1}\partial_t\psi\right)+V\psi=-\left(\gamma^{-2}\partial_x^2\psi -2\gamma^{-2}v^{-1}\partial_x\partial_t\psi + \gamma^{-2}v^{-2}\partial_t^2\psi\right)+V\psi.
\end{equation}








### Sources
I primarily followed my own course notes from 8.323, Relativistic Quantum Field Theory I, taught by Professor Hong Liu during the 2025 Spring semester.
