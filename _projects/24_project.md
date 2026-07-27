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
-\partial_i p\left(\mathbf{x}\right) +\mu\partial^2 u_i\left(\mathbf{x}\right) = -F_i\delta\left(\mathbf{x}\right)\quad\partial_iu_i=0.
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
u_i = \frac{F _j}{8\pi\mu}\mathcal{G} _{ij}, \quad p = \frac{F_i}{8\pi \mu}\mathcal{P} _i,
\end{equation}
where $$\mathcal{G} _{ij}$$ is the Oseen Tensor and $$\mathcal{P}_i$$ is the corresponding pressure field tensor, given by,
\begin{equation}
\mathcal{G} _{ij} = \frac{1}{r}\delta _{ij}+\frac{1}{r^3}x_ix_j,
\end{equation}
\begin{equation}
\mathcal{P} _i = 2\mu\frac{x _i}{r^3}.
\end{equation}
Now we may also construct the stress field tensor,
\begin{equation}
\sigma _{ij}=\frac{F_k}{8\pi \mu}\left(-\mathcal{P} _k\delta _{ij} + \mu\left(\partial_i\mathcal{G} _{jk}+\partial_j\mathcal{G} _{ik}\right)\right) = F_k\Sigma _{ijk},
\end{equation}
with,
\begin{equation}
8\pi\mu\Sigma _{ijk} = -\mathcal{P} _k\delta _{ij} + \mu\left(\partial_i\mathcal{G} _{jk}+\partial_j\mathcal{G} _{ik}\right) =  -\mu\frac{6}{r^5}x_ix_jx_k.
\end{equation}
We can actually remove the force term to rewrite Eq. \ref{eq: delta function stokes} in the more general form, placing a singularity at $$\mathbf{\xi}$$,
\begin{equation}\label{eq: delta function stokes tensor representation 1}
-\partial_i \mathcal{P} _k\left(\mathbf{x}-\mathbf{\xi}\right) +\mu\partial^2 \mathcal{G} _{ik}\left(\mathbf{x}-\mathbf{\xi}\right) = 8\pi\mu\partial _j\Sigma _{ijk}\left(\mathbf{x} - \mathbf{\xi}\right) = -8\pi\mu \delta _{ik} \delta\left(\mathbf{x}-\mathbf{\xi}\right).
\end{equation}
\begin{equation}\label{eq: delta function stokes tensor representation 2}
\partial_i\mathcal{G} _{ij}\left(\mathbf{x} - \mathbf{\xi}\right)=0.
\end{equation}

### The Integral Representation with Green's Functions
We derived the Green's functions to power a representation of the velocity field as a surface integral. First, we will need the reciprocal theorem. 

Consider a closed region of fluid $$V$$ enclosed by a surface $$S$$. Two velocity fields $$u_i^1$$ and $$u_i^2$$ satisfy the Stokes Equations with different boundary conditions on the surface $$S$$. Now notice,
\begin{equation}
\sigma^1_{ij}e^2_{ij}=2\mu e^1_{ij}e^2_{ij}=\sigma^2_{ij}e^1 _{ij}.
\end{equation}
But consider,
\begin{equation}
\sigma^1 _{ij}e^2 _{ij}=\sigma^1 _{ij}\partial_j u^2_i = \partial _j\left(\sigma^1 _{ij}u^2_i\right)-u^2_i\partial _j\sigma^1 _{ij}=\partial _j\left(\sigma^2_{ij}u^1_i\right)-u^1 _i\partial _j\sigma^2 _{ij}.
\end{equation}
And integrating over the region $$V$$ and applying the divergence theorem,
\begin{equation}\label{eq: Reciprocal theorem}
\oint _S dS\ \sigma^1 _{ij}u^2_i n_j - \int_V dV\ u^2 _i\partial _j\sigma^1_{ij} = \oint _S dS\ \sigma^2 _{ij}u^1_i n_j - \int_V dV\ u^1 _i\partial _j\sigma^2 _{ij}.
\end{equation}
Eq. \ref{eq: Reciprocal theorem} is known as the Reciprocal theorem.

We can also apply the Reciprocal theorem to the Green's function representation. Let u^1_i correspond to the solution of the Stokes Equations in the presence of a point forcing at $$\mathbf{x}$$ and let $$u^2$$ be replaced by $$u$$, the velocity field in the region of interest. Eq. \ref{eq: Reciprocal theorem} becomes,
\begin{equation}
\oint _S dS\left(\mathbf{\xi}\right)\ F_k\Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right)u_i\left(\mathbf{\xi}\right) n_j\left(\mathbf{\xi}\right)+\int_V dV\left(\mathbf{\xi}\right)\ u _i\left(\mathbf{\xi}\right) F_i\delta\left(\mathbf{\xi}-\mathbf{x}\right) = \oint _S dS\left(\mathbf{\xi}\right)\ \sigma _{ij}\left(\mathbf{\xi}\right)\frac{F_k}{8\pi \mu}\mathcal{G} _{ik}\left(\mathbf{\xi}-\mathbf{x}\right)n_j\left(\mathbf{\xi}\right) - \int_V dV\left(\mathbf{\xi}\right)\ \frac{F_k}{8\pi \mu}\mathcal{G} _{ik}\left(\mathbf{\xi}-\mathbf{x}\right)\partial _j\sigma _{ij}\left(\mathbf{\xi}\right).
\end{equation}
As this holds for any $$F_k$$ forcing, we can do away with this index, and assuming the $$u$$ field is force-free such that $$\partial _j\sigma _{ij}=0$$,
\begin{equation}
\oint _S dS\left(\mathbf{\xi}\right)\ \sigma _{ij}\left(\mathbf{\xi}\right)\mathcal{G} _{ik}\left(\mathbf{\xi}-\mathbf{x}\right)n_j\left(\mathbf{\xi}\right) = 8\pi\mu\oint _S dS\left(\mathbf{\xi}\right)\ \Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right)u_i\left(\mathbf{\xi}\right) n_j\left(\mathbf{\xi}\right)+8\pi\mu\int_V dV\left(\mathbf{\xi}\right)\ u _k\left(\mathbf{\xi}\right) \delta\left(\mathbf{\xi}-\mathbf{x}\right).
\end{equation}



and will come in very handy in the integral representations that follow.




### The Multipole Expansion
The notes here are based on Kim and Karrila's _Microhydrodynamics_.




### Sources
