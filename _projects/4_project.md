---
layout: page
title: On the Relativistic Euler Equations
description: another without an image
img:
importance: 3
category: Physics
toc:
  beginning: true
---
## Introduction

The relativistic form of the Euler Equations are used to describe relativistic fluids. These equations appear quite naturally from the continuity of the stress-energy tensor, and in the appropriate limit, reduce to the non-relativistic version.

## Derivation
The continuity equation of the stress-energy tensor is given by:

\begin{equation}\label{continuity eq}
  T^{\mu\nu}_{;\nu}=0
\end{equation}

For a perfect fluid, the stress-energy tensor has the form:

\begin{equation}
  T_{\mu\nu}=\rho u_\mu u_\nu +P h_{\mu\nu}
\end{equation}

Where $$h_{\mu\nu} = g_{\mu\nu} + u_\mu u_\nu$$ and $$u_\mu$$ is a 4-velocity element of the fluid. 

From \eqref{continuity eq}:

\begin{equation}
0 = T^{\mu\nu}_{;\nu}h^\gamma_\mu
\end{equation}
\begin{equation}
0 = h^\gamma_\mu\left(\rho u^\mu u^\nu\right) _{;\nu} +h^\gamma _\mu\left(P h^{\mu\nu}\right) _{;\nu}
\end{equation}

\begin{equation}
0 = g^\gamma _\nu\left(\rho u^\mu u^\nu\right) _{;\nu} + u^\gamma u _\mu \left(\rho u^\mu u^\nu\right) _{;\nu}+ g^\gamma _\nu\left(P h^{\mu\nu}\right) _{;\nu} + u^\gamma u _\mu \left(P h^{\mu\nu}\right) _{;\nu}
\end{equation}


## Reduction to Non-Relativistic Equations
