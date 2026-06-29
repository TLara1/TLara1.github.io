---
layout: page
title: On the Renormalization of Quantum Electrodynamics - 7/26
description:
img: 
importance: 1
category: Physics
related_publications: false
toc:
  beginning: true
---

## Introduction
Oh dear. This is a terrible idea. I shudder at the thought of all the notation I will need to get right here. Wish me luck, please proceed with caution.

I am, unfortunately, no longer much of a theoretical physicist. I took three semesters of Quantum Field Theory (QFT) and decided it was not for me. But there is a beauty in the calculations of QFT, the slow methodical alignment of a malestrom of algebra and indices. I doubt these notes will serve me much in the future, but I wish to conserve some fraction of what I learned in QFT in a more permanent manner. 

Here, we will compute the first-order renormalization of the theory of Quantum Electrodynamics (QED). That is to say, we will identify the four counterterms necessary to remove divergences from 1-loop level QED diagrams. This will mostly involve resolving some very nasty-looking integrals, but after doing these calculations once, they can be done a thousand times. 

Note here that we will only look at the tip of the QFT iceberg. Things become **severely** more complicated at higher orders of loop calculation, and everything I will present is fairly straightforward. For the sake of not complicating things too much, I will not go too too in-depth here, leaving the more sophisticated details to those who are more qualified than me.

## Notation and Convention
We use the standard non-dimensionalization setting $$c=\hbar=1$$. We use the mostly negative metric convention,
\begin{equation}
ds^2=\eta^{\mu\nu}x_\mu x_\nu = dt^2-dx^2-dy^2-dz^2,
\end{equation}
apologies if this was not the convention you used in your physics education. 

We use Gamma matrices, $$\gamma^\mu$$ with $$\mu=0,1,2,3$$ satisfying the anticommutation relation,
\begin{equation}\label{eq: gamma anticommutation relation}
\left\lbrace\gamma^\mu,\gamma^\nu\right\rbrace=\eta^{\mu\nu}.
\end{equation}
Here we have suppressed spinor indices and will continue to do so. Keep in mind that $$\gamma^mu$$ is a four-by-four matrix in spinor space. 
A useful property that follows from Eq. \ref{eq: gamma anticommutation relation} is,
\begin{equation}
\left(\gamma^\mu\right)^\dagger=\gamma^0\gamma^\mu\gamma^0.
\end{equation}
We also define the adjoint $$\bar{ }$$ operation as,
\begin{equation}
\bar{\psi}^\mu=\psi^\dagger\gamma^0,
\end{equation}
where $$\psi$$ is a four-component spinor.

Onward and upward.

## The QED Lagrangian and Feynman Rules. 
The Lagrangian for QED describing the interactions between a spin-1/2 spinor field $$\psi\left(\mathbf{X}\right)$$ and a gauge field $$A_\mu\left(\mathbf{x}\right)$$ is,
\begin{equation}
\mathcal{L} _\text{QED}=\bar{\psi}\left(i\not D-m\right)\psi-\frac{1}{4}F^{\mu\nu}F _{\mu\nu}.
\end{equation}




### Sources
