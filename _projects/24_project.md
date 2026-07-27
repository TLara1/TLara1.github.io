---
layout: page
title: On the Effective Viscosity of a Spherical Suspension - 8/26
description:
img: 
importance: 84
category: Maths
related_publications: false
toc:
  beginning: true
---

## Introduction


## Singularity System for Spheres

### The Stokes Equations
We begin with the Stokes equations,
\begin{equation}
-\partial_i p\left(\mathbf{x}\right) +\mu\partial^2 u_i\left(\mathbf{x}\right) = -f_i\left(\mathbf{x}\right),\quad\partial_iu_i\left(\mathbf{x}\right)=0.
\end{equation}
$$u_i\left(\mathbf{x}\right)$$ is the velocity field, $$p\left(\mathbf{x}\right)$$ is the pressure field, and $$f_i$$ is a non-conservative force distribution. $$\mu$$ is the fluid viscosity. The equation can also be written as the divergence of a stress tensor,
\begin{equation}
\partial_j\sigma_{ij}\left(\mathbf{x}\right) = -f_i\left(\mathbf{x}\right),\quad\sigma_{ij}\left(\mathbf{x}\right)=-p\left(\mathbf{x}\right)\delta_{ij}+2\mu e_{ij}\left(\mathbf{x}\right),
\end{equation}
where $$e_{ij}$$ are the components of the symmetric rate of deformation tensor,
\begin{equation}
e_{ij}\left(\mathbf{x}\right)=\frac{1}{2}\left(\partial_i u_j\left(\mathbf{x}\right) + \partial_j u_i\left(\mathbf{x}\right).
\end{equation}

### The Green's Function for Stokes Flow
We wish to solve the Stokes Equations in the presence of a Dirac delta function forcing,
\begin{equation}\label{eq: delta function stokes}
-\partial_i p +\mu\partial^2 u_i = -F_i\delta\left(\mathbf{x}\right)\quad\partial_iu_i=0.
\end{equation}
to obtain a Green's function solution for our flow. This is most straightforward to do in wavenumber space. Taking a Fourier transform of Eq. \ref{eq: delta function stokes}, the equation is evaluated in $$k$$-space,
\begin{equation}
-i k_i \tilde{p} -\mu k^2 \tilde{u}_i = -F_i\quad k_i\tilde{u}_i=0.
\end{equation}
It is not difficult to obtain the solution of the linear system,
\begin{equation}
\tilde{u}_i = \frac{F_j}{\mu k^2}\left(\delta _{ij}-\frac{k _ik _j}{k^2}\right), \quad \tilde{p} = -\frac{i k_i F_i}{k^2}.
\end{equation}
Reverse Fourier-transforming, we return to position space with,
\begin{equation}
u_i = \frac{F _j}{8\pi}\mathcal{G} _{ij}, \quad p = \frac{F_i}{8\pi \mu}\mathcal{P} _i,
\end{equation}
where $$\mathcal{G} _{ij}$$ is the Oseen Tensor and $$\mathcal{P}_i$$ is the corresponding pressure field tensor, given by,
\begin{equation}
\mathcal{G} _{ij} = \frac{1}{r}\delta _{ij}+\frac{1}{r^3}x_ix_j,
\end{equation}
\begin{equation}
\mathcal{P} _i = 2\mu\frac{x_i}{r^3}.
\end{equation}

### The Integral Representation with Green's Functions
We derived the Green's functions to power a representation of the velocity field as a surface integral. First, we will need the reciprocal theorem. 

Consider a closed region of fluid $$V$$ enclosed by a surface $$S$$. Two velocity fields $$u_i^1$$ and $$u_i^2$$ satisfy the Stokes Equations with different boundary conditions on the surface $$S$$. Now notice,
\begin{equation}
\sigma^1_{ij}e^2_{ij}=2\mu e^1_{ij}e^2_{ij}=\sigma^2_{ij}e^1_{ij}.
\end{equation}
But consider,
\begin{equation}
\sigma^1_{ij}e^2_{ij}=\sigma^1_{ij}\partial_j u^2_i = \partial_j\left(\sigma^1_{ij}u^2_i\right)-u^2_i\partial_j\sigma^1_{ij}=\partial_j\left(\sigma^2_{ij}u^1_i\right)-u^1_i\partial_j\sigma^2_{ij}.
\end{equation}
And integrating over the region $$V$$ and applying the divergence theorem,
\begin{equation}\label{eq: Reciprocal theorem}
\oint_S dS\ \sigma^1_{ij}u^2_i n_j - \int_V dV\ u^2_i\partial_j\sigma^1_{ij} = \oint_S dS\ \sigma^2_{ij}u^1_i n_j - \int_V dV\ u^1_i\partial_j\sigma^2_{ij}.
\end{equation}
Eq. \ref{eq: Reciprocal theorem} is known as the Reciprocal theorem and will come in very handy in the integral representations that follow.



### The Multipole Expansion
The notes here are based on Kim and Karrila's _Microhydrodynamics_.




### Sources
