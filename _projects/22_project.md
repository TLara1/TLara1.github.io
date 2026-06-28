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

## The Failures of the Schrödinger Equation
The usual Schrödinger equation for a wavefunction $$\psi(\mathbf{x}\right)$$ is,
\begin{equation}
i\partial_t\psi=H\left[\psi\right]=-\partial_i\partial^i\psi+V\left(\mathbf{x}\right)\psi.
\end{equation}
We know our physics should be true in any frame of reference, that is to say, the Schrödinger equation should apply after we perform a Lorentz transform, denoting the transformed coordinates $$\mathbf{x}'$$, and the transformed wavefunction as $$\psi'\left(\mathbf{x}'\right)$$, it should be true that $$i\partial_{t'}\psi'=H'\left[\psi'\right]$$. As we will see, this is not the case.

Consider a Lorentz transform along the $$x$$-direction, the $$x$$ and $$t$$ coordinates change as,
\begin{equation}
t\rightarrow t' = \gamma t - \gamma v x,\quad x\rightarrow x' = \gamma x - \gamma v t,
\end{equation}
where $$\gamma=\left(1-v^2\right)^{-1/2}$$ is the Lorentz factor.

The wavefunction $$\psi$$ describes events at points in spacetime. Under a change of coordinates, there is no reason to expect $$\psi$$ to transform as a scalar; we therefore consider the most general transform,
\begin{equation}
\psi(\mathbf{x}'\right)=f(\mathbf{x}\right)\psi(\mathbf{x}\right),
\end{equation}
and look for a function $$f(\mathbf{x}\right)$$ such that the Schrödinger equation is invarient.

For the left-hand side of the Schrödinger equation,
\begin{equation}\label{eq: transformed Schrodinger LHS}
i\partial_{t'}\psi'=i\partial_{t'}\left( f\psi\right)=i\gamma \left(f\partial_t\psi+ v f\partial_x\psi+\psi\partial_t f+ v\psi\partial_x f\right).
\end{equation}
For the right-hand side, ignoring the potential to assess the validity of the free equation,
\begin{equation}\label{eq: transformed Schrodinger RHS}
-\partial^2_{x'}\psi'=- f \partial^2_{x'}\psi - 2\partial_{x'} f \partial_{x'}\psi - \psi \partial^2_{x'}f 
\end{equation}
\begin{equation}
=-\gamma^2 f \left(\partial_x^2\psi + 2 v \partial_x\partial_t\psi +  v^2\partial_t^2\psi\right) -\gamma^2 \psi \left(\partial_x^2 f + 2 v \partial_x\partial_t f +  v^2\partial_t^2 f \right) - \gamma^2\left(\partial_x\psi + v \partial_t\psi \right) \left(\partial_x f + v \partial_t f \right).
\end{equation}

Combining Eq. \ref{eq: transformed Schrodinger LHS} and Eq. \ref{eq: transformed Schrodinger RHS}, we see there is instantly a problem since the right-hand side contains new second-order derivatives of the form $$\partial_t\partial_x\psi$$ and $$\partial_t^2\psi$$. Reinserting the original Schrödinger equation results in
\begin{equation}
\text{terms with }\left[\psi, \partial_x\psi,\partial_x^2\psi\right] = \text{terms with }\left[\psi, \partial_x\psi,\partial_x^2\psi, \partial_x^3\psi,\partial_x^4\psi\right].
\end{equation}
Our relation must hold for any wavefunction $$\psi$$. Because the covariant transform function $$f$$ cannot depend on the wavefunction itself, there is no way we can find an $$f$$ to remove the higher-order derivative terms. So, we conclude that the Schrödinger equation is not Lorentz invariant or even Lorentz covariant. It is covariant under Galilean transforms, but we will leave that as an exercise to the reader. 

## Matrix-ifying the Schrödinger Equation

We could've avoided all of the math of the previous section by simply noting that the derivatives on each side of the Schrödinger equation are not of the same order, so a Lorentz transform would never work out. For Lorentz invariance, we require the order of the spatial and temporal derivatives to match. For instance, consider the Klein-Gordon equation,
\begin{equation}\label{eq: klein gordon equation}
\partial_\mu\partial^\mu\phi + m^2\phi = \partial_t^2\phi - \partial_i\partial^i\phi + m^2\phi = 0,
\end{equation}
a calculation as we performed above should convince you that this equation **is** Lorentz invariant and fully relativistic. The Dirac equation essentially aims to rewrite the Schrödinger equation with only first-order spatial derivatives. 

Let's first consider the following for our Hamiltonian with first-order spatial derivatives,
\begin{equation}
H = -i\alpha^i\partial_i + \beta m,
\end{equation}
Now we square the Schrödinger equation to find,
\begin{equation}\label{eq: squared shrodinger}
-\partial_t^2\psi = \left(-i\alpha^i\partial_i + \beta m\right)^2\psi.
\end{equation}
Inserting the Klein-Gordon equation in Eq. \ref{eq: squared shrodinger}, we find that $$\alpha$$ and $$\beta$$ should satisfy,
\begin{equation}
-\alpha^i\alpha^j\partial_i\partial_j\psi + \beta^2m^2\psi - i\left(\beta\alpha^i+\alpha^i\beta\right)\partial_i\psi=- \partial_i\partial^i\psi + m^2\psi.
\end{equation}
This gives the following conditions for $$\alpha$$ and $$\beta$$,
\begin{equation}
\alpha_i\alpha_j+\alpha_j\alpha_i=0\ i\neq j,
\end{equation}
\begin{equation}
\alpha_i^2=1,
\end{equation}
\begin{equation}
\beta^2=1,
\end{equation}
\begin{equation}
\beta\alpha^i+\alpha^i\beta = 0
\end{equation}
\begin{equation}
\alpha_i^\dagger=\alpha_i,
\end{equation}
\begin{equation}
\beta^\dagger=\beta,
\end{equation}
where the last two conditions follow from the Hermiticity of the Hamiltonian. But we have a huge problem, since $$i=1,2,3$$, this is 






























We see that $$i\partial_{t'}\psi'\neq H'\left[\psi'\right]$$ and the Schrödinger equation is not Lorentz invariant. Now, 

\begin{equation}
i\partial_t\psi-i v \partial_x\psi = - \partial_x^2\psi + 2 v \partial_x\partial_t\psi -  v^2\partial_t^2\psi +V\psi.
\end{equation}

\begin{equation}
-i v \partial_x\psi =  2 v \partial_x\partial_t\psi -  v^2\partial_t^2\psi .
\end{equation}







### Sources
I primarily followed my own course notes from 8.323, Relativistic Quantum Field Theory I, taught by Professor Hong Liu during the 2025 Spring semester.
