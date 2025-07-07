---
layout: page
title: On the Relativistic Euler Equations
description:
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
0 = T^{\mu\nu}_{;\nu}h _{\gamma\mu}
\end{equation}

\begin{equation}
0 = h_{\gamma\mu}\left(\left(\rho u^\mu u^\nu\right) _{;\nu}+P _{;\nu} h^{\mu\nu} + P h^{\mu\nu} _{;\nu} \right)
\end{equation}

Using $$h^{\mu\nu} _{;\nu} =\left(g^{\mu\nu}+u^\mu u^\nu\right) _{;\nu}=\left(u^\mu u^\nu\right) _{;\nu}$$:

\begin{equation}
0 = h_{\gamma\mu}\left(\rho_{;\nu}u^\mu u^\nu + \left(\rho+P\right)\left(u^\mu u^\nu\right) _{;\nu}+P _{;\nu} h^{\mu\nu}\right)
\end{equation}

\begin{equation}
h_{\gamma\mu}\rho_{;\nu}u^\mu u^\nu+\left(\rho+P\right)h_{\gamma\mu}\left(u^\mu u^\nu\right) _{;\nu} = -P _{;\nu} h _{\gamma\mu} h^{\mu\nu}
\end{equation}

Because $$h_{\gamma\mu} u^\mu = u_\gamma + u_\gamma u_\mu u^\mu =  u_\gamma -  u_\gamma =0$$:

\begin{equation} \label{rel euler eq}
\left(\rho+P\right)u^\nu u^\mu_{;\nu} = -P _{;\nu} h^{\mu\nu}
\end{equation}

These are the relativistic Euler Equations.

## Reduction to Non-Relativistic Equations

In a flat spacetime, $$ h^{\mu\nu} = \eta^{\mu\nu}+u^\mu u^\nu$$, and the 4-velocity reduces to: $$u^\nu=\left(1,v^i\right)$$. Furthermore, we can safely assume $$\rho \ggg P$$, so the left hand side of \eqref{rel euler eq} becomes:

\begin{equation}
  \rho u^\nu u^\mu_{;\nu} = \rho\left(v^i_{,0} + v^j v^i_{,j}\right)
\end{equation}

As for the right hand side, approximating $$v^i v^j = 0$$:

\begin{equation}
  P _{;\nu} u^\mu u^\nu = P _{,0} + v^i P _{,0}
\end{equation}
So:
\begin{equation}
-P _{;\nu} h^{\mu\nu} = -v^i P _{,0} +\delta^{ij} P _{,j}
\end{equation}
Taking $$P _{,0}$$ to be of the same order as $$v^i$$, we can set $$v^i P _{,0}=0$$ and find:

\begin{equation}
v _{i,0} + v^j v _{i,j} = -\frac{1}{\rho}P _{,i}
\end{equation}

Or in direct notation for a more familiar form:

\begin{equation}
  \partial_t\vec{v}+\vec{v}\cdot\vec{\nabla}\vec{v}=-\frac{1}{\rho}\vec{\nabla}P
\end{equation}

 Which are the Newtonian Euler Equations. 





