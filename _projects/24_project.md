---
layout: page
title: On Slender Body Theory, Jeffery Orbits, and the Rheology of Dilute Spheroid Suspensions - 8/26
description:
img: 
importance: 84
category: Maths
related_publications: false
toc:
  beginning: true
---

## Introduction
I spent a good amount of this summer combing through Kim and Karilla's Microhydrodynamics. 

## Singularity Systems
The Green's function is our most fundamental tool for studying solutions to the Stokes Equations. Once we develop the singularity solution and integral representations, we may proceed to spherical and spheroid solutions.

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
e_{ij}\left(\mathbf{x}\right)=\frac{1}{2}\left(\partial_i u_j\left(\mathbf{x}\right) + \partial_j u_i\left(\mathbf{x}\right)\right).
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
\sigma^1 _{ij} e^2 _{ij} = 2\mu e^1 _{ij}e^2 _{ij} = \sigma^2 _{ij} e^1 _{ij}.
\end{equation}
But consider,
\begin{equation}
\sigma^1 _{ij}e^2 _{ij}=\sigma^1 _{ij}\partial _j u^2_i = \partial _j\left(\sigma^1 _{ij}u^2_i\right)-u^2 _i\partial _j\sigma^1 _{ij}=\partial _j\left(\sigma^2 _{ij}u^1_i\right)-u^1 _i\partial _j\sigma^2 _{ij}.
\end{equation}
And integrating over the region $$V$$ and applying the divergence theorem, where $$n_i$$ is a unit vecotr pointing out of the fluid-filled region $$V$$,
\begin{equation}\label{eq: Reciprocal theorem}
\oint _S dS\ \sigma^1 _{ij}u^2_i n_j - \int_V dV\ u^2 _i\partial _j\sigma^1 _{ij} = \oint _S dS\ \sigma^2 _{ij}u^1_i n_j - \int_V dV\ u^1 _i\partial _j\sigma^2 _{ij}.
\end{equation}
Eq. \ref{eq: Reciprocal theorem} is known as the Reciprocal theorem.

We can also apply the Reciprocal theorem to the Green's function representation. Let $$u^1_i$$ correspond to the solution of the Stokes Equations in the presence of a point forcing at $$\mathbf{x}$$ and let $$u^2$$ be replaced by $$u$$, the velocity field in the region of interest. Eq. \ref{eq: Reciprocal theorem} becomes,
\begin{equation}
\oint _S dS\left(\mathbf{\xi}\right)\ F_k\Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right)u_i\left(\mathbf{\xi}\right) n_j\left(\mathbf{\xi}\right)+\int_V dV\left(\mathbf{\xi}\right)\ u _i\left(\mathbf{\xi}\right) F_i\delta\left(\mathbf{\xi}-\mathbf{x}\right)\nonumber
\end{equation}
\begin{equation}
= \oint _S dS\left(\mathbf{\xi}\right)\ \sigma _{ij}\left(\mathbf{\xi}\right)\frac{F_k}{8\pi \mu}\mathcal{G} _{ik}\left(\mathbf{\xi}-\mathbf{x}\right)n_j\left(\mathbf{\xi}\right) - \int_V dV\left(\mathbf{\xi}\right)\ \frac{F_k}{8\pi \mu}\mathcal{G} _{ik}\left(\mathbf{\xi}-\mathbf{x}\right)\partial _j\sigma _{ij}\left(\mathbf{\xi}\right).
\end{equation}

As this holds for any $$F_k$$ forcing, we can do away with this index, and assuming the $$u$$ field is force-free such that $$\partial _j\sigma _{ij}=0$$,
\begin{equation}
\frac{1}{8\pi\mu}\oint _S dS\left(\mathbf{\xi}\right)\ \sigma _{ij}\left(\mathbf{\xi}\right)\mathcal{G} _{ik}\left(\mathbf{\xi}-\mathbf{x}\right)n_j\left(\mathbf{\xi}\right) =\oint _S dS\left(\mathbf{\xi}\right)\ \Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right)u_i\left(\mathbf{\xi}\right) n_j\left(\mathbf{\xi}\right)+\int_V dV\left(\mathbf{\xi}\right)\ u _k\left(\mathbf{\xi}\right) \delta\left(\mathbf{\xi}-\mathbf{x}\right).
\end{equation}
Now we can exchange the order of $$\mathbf{x}$$ and $$\mathbf{\xi}$$ using $$\mathcal{G} _{ij}\left(-\mathbf{x}\right)=\mathcal{G} _{ij}\left(\mathbf{x}\right)$$ and $$\Sigma _{ijk}\left(-\mathbf{x}\right)=-\Sigma _{ijk}\left(\mathbf{x}\right)$$. For the velocity field inside the region $$V$$, the $$\delta$$ function integral turns into $$u_k\left(\mathbf{x}\right)$$, while outside this region, it evaluate to $$0$$, giving the following surface integral representation for the velocity,
\begin{equation}\label{eq: surface integral velocity representation 1}
\text{if}\ \mathbf{x}\in V,\quad u_k\left(\mathbf{x}\right)=\frac{1}{8\pi\mu}\oint _S dS\left(\mathbf{\xi}\right)\ \sigma _{ij}\left(\mathbf{\xi}\right)\mathcal{G} _{ik}\left(\mathbf{x}-\mathbf{\xi}\right)n_j\left(\mathbf{\xi}\right) + \oint _S dS\left(\mathbf{\xi}\right)\ \Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right)u_i\left(\mathbf{\xi}\right) n_j\left(\mathbf{\xi}\right),
\end{equation}
\begin{equation}\label{eq: surface integral velocity representation 2}
\text{if}\ \mathbf{x}\notin V,\quad 0=\frac{1}{8\pi\mu}\oint _S dS\left(\mathbf{\xi}\right)\ \sigma _{ij}\left(\mathbf{\xi}\right)\mathcal{G} _{ik}\left(\mathbf{x}-\mathbf{\xi}\right)n_j\left(\mathbf{\xi}\right) + \oint _S dS\left(\mathbf{\xi}\right)\ \Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right)u_i\left(\mathbf{\xi}\right) n_j\left(\mathbf{\xi}\right).
\end{equation}

This is helpful, but we are also interested in the case of a particle immersed in a fluid region. Consider now a fluid region $$V_f$$ bounded by a particle surface $$S_p$$ and a far-away surface $$S_\infty$$. The particle undergoes some rigid-body motion such that $$u_i=u^p_i$$ on the surface of and inside the particle, and far away from the particle there is ambient flow $$u_i=u^\infty_i$$ on $$S_\infty$$. We are interested in evaluating the disturbance field $$u^D_i=u_i-u^\infty_i$$ in the region $$V_f$$. With Eq. \ref{eq: surface integral velocity representation 1} and Eq. \ref{eq: surface integral velocity representation 2}, we see,
\begin{equation}
\text{if}\ \mathbf{x}\in V_f,\quad u^D_k\left(\mathbf{x}\right)=-\frac{1}{8\pi\mu}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \sigma^D _{ij}\left(\mathbf{\xi}\right)\mathcal{G} _{ik}\left(\mathbf{x}-\mathbf{\xi}\right)\hat{n}_j\left(\mathbf{\xi}\right)-\oint _{S _p} dS\left(\mathbf{\xi}\right)\ \left(u^p_i-u^\infty_i\right)\Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right) \hat{n}_j\left(\mathbf{\xi}\right)\nonumber
\end{equation}
\begin{equation}\label{eq: integral represntation outside particle}
-\frac{1}{8\pi\mu}\oint _{S _\infty} dS\left(\mathbf{\xi}\right)\ \sigma^D _{ij}\left(\mathbf{\xi}\right)\mathcal{G} _{ik}\left(\mathbf{x}-\mathbf{\xi}\right)\hat{n}_j\left(\mathbf{\xi}\right) 
-\oint _{S _\infty} dS\left(\mathbf{\xi}\right)\ u^D_i\Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right) \hat{n}_j\left(\mathbf{\xi}\right),
\end{equation}
where $$\hat{n}_i$$ points **into** the fluid region in the direction opposite to $$n_i$$. The integrals over $$S _\infty$$ vanish as the edge of the boundary approaches infinity if $$u^D_i\rightarrow0$$ and $$r\sigma^D _{ij}\rightarrow0$$ as $$r\rightarrow\infty$$ as $$\mathcal{G} _{ij}\sim r^{-1}$$ and $$\Sigma _{ijk}\sim r^{-2}$$ and $$dS\sim r^2$$. The first condition holds, $$u^D_i\rightarrow0$$, as we expect the influence of the particle to vanish far from its surface and by the definition of $$u_i^\infty$$. We similarly expect $$\sigma^D _{ij}\sim r^{-2}$$ since the gradient of the disturbance field goes with, $$\partial_i u^D_j\rightarrow r^{-2}$$.

Now apply the same integral representation to the region inside the particle where the velocity 
\begin{equation}
\text{if}\ \mathbf{x}\in V _p, \quad u_k^p- u^\infty_k = \frac{1}{8\pi\mu}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \left(\sigma^p _{ij}-\sigma^\infty _{ij}\left(\mathbf{\xi}\right)\right)\mathcal{G} _{ik}\left(\mathbf{x}-\mathbf{\xi}\right)\hat{n}_j\left(\mathbf{\xi}\right)\nonumber
\end{equation}
\begin{equation}\label{eq: integral represntation inside particle}
+\oint _{S _p} dS\left(\mathbf{\xi}\right)\ \left(u^p_i-u^\infty_i\right)\Sigma _{ijk}\left(\mathbf{\xi}-\mathbf{x}\right) \hat{n}_j\left(\mathbf{\xi}\right).
\end{equation}


The surface traction integral, $$\sigma^p _{ij}$$ vanishes, since its net contribution is a constant pressure term in the case of a rigid body and the integral over the solenoidal Green's function vanishes. 

We add Eq. \ref{eq: integral represntation outside particle} and Eq. \ref{eq: integral represntation inside particle} to obtain a representation of the velocity field everywhere. Integrals over $$S_\infty$$ are also removed since they vanish as discussed above,
\begin{equation}\label{eq: greens function integral rep}
u_k\left(\mathbf{x}\right) = u_k^\infty -\frac{1}{8\pi\mu}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \sigma _{ij}\left(\mathbf{\xi}\right)\mathcal{G} _{ik}\left(\mathbf{x}-\mathbf{\xi}\right)\hat{n}_j\left(\mathbf{\xi}\right).
\end{equation}
So the disturbance field everywhere in the fluid domain can be expressed as a surface integral with a Green's function kernel over the stress at the particle surface. 

### The Multipole Expansion
Now we may expand the integral representation in the far field, the limit of $$|\mathbf{x}|\gg|\mathbf{\xi}|$$ so that $$\mathcal{G} _{ij}\left(\mathbf{x}-\mathbf{\xi}\right)\approx\mathcal{G} _{ij}\left(\mathbf{x}\right)$$. Formally, expanding the Green's function around $$\mathbf{\xi}=0$$,

\begin{equation}
\mathcal{G} _{ij}\left(\mathbf{x}-\mathbf{\xi}\right)=\sum _{n=0}^\infty\frac{ \left(-1\right)^n }{n!}\left(\xi _k\partial _k\right)^n\mathcal{G} _{ij}\left(\mathbf{x}\right).
\end{equation}

Inserting this into the velocity integral,

\begin{equation}
u_k\left(\mathbf{x}\right) -u_k^\infty =  -\frac{1}{8\pi\mu}\sum _{n=0}^\infty\frac{ \left(-1\right)^n }{n!}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \left(\sigma _{ij} \hat{n}_j\left(\mathbf{\xi}\right) \xi _{k_1}\xi _{k_2}...\xi _{k_n}\right)\partial _{k_1}\partial _{k_2}...\partial _{k_n}\mathcal{G} _{ik}\left(\mathbf{x}\right),
\end{equation}

\begin{equation}
u _k\left(\mathbf{x} \right) -u _k^\infty =  -F _i\frac{\mathcal{G} _{ik}\left(\mathbf{x}\right)}{8\pi\mu} +D _{ij}\frac{\partial_j\mathcal{G} _{ik}\left(\mathbf{x}\right)}{8\pi\mu} + ...,
\end{equation}

with,
\begin{equation}
F _i = \oint _{S_p} dS \left(\mathbf{\xi}\right)\ \sigma _{ij} \hat{n}_j \left( \mathbf{\xi} \right),
\end{equation}

\begin{equation}
D _{ij} = \oint _{S_p} dS\left(\mathbf{\xi}\right)\ \sigma _{il} \hat{n}_l\left(\mathbf{\xi}\right)\xi _j .
\end{equation}

$$F _i$$ is known as the _stokeslet_, the next effect is the dipole $$D _{ij}$$ that decays with $$r^{-2}$$. Because the isotropic portion of $$D _{ij}$$ has no dynamic significance since $$\partial_i\mathcal{G} _{ij}=0$$, we can split the term into a symmetric _stresslet_ and an antisymmetric _rotlet_,
\begin{equation}
D _{ij} -\frac{1}{3}D _{kk}\delta _{ij} = S _{ij} + T _{ij},
\end{equation}
\begin{equation}
S _{ij} = \frac{1}{2}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \left(\sigma _{il}\xi _j + \sigma _{jl} \xi _i\right)\hat{n}_l\left(\mathbf{\xi}\right) - \frac{1}{3}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \sigma _{lm}\xi _l \hat{n}_m\left(\mathbf{\xi}\right)\delta _{ij},
\end{equation}
\begin{equation}
T _{ij} = \frac{1}{2}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \left(\sigma _{il}\xi _j - \sigma _{jl} \xi _i\right)\hat{n}_l\left(\mathbf{\xi}\right).
\end{equation}
We may also identify the relation of the rotlet with the torque pseudovector,
\begin{equation}
-\epsilon _{ijk}T _{jk} = -\epsilon _{ijk}\oint _{S_p} dS\left(\mathbf{\xi}\right)\ \sigma _{jl} \xi _k \hat{n}_l\left(\mathbf{\xi}\right) = T _i,
\end{equation}
and,
\begin{equation}
T _{jk}=-\frac{1}{2}\epsilon _{jkl}T _l.
\end{equation}
Next, we will use the multipole expansion to identify the velocity field around a spherical particle

### The Singularity System for Spheres
First, we calculate a few derivatives of the Oseen tensor, which will come in handy,
\begin{equation}
\mathcal{G} _{ij} = \frac{1}{r}\delta _{ij}+\frac{1}{r^3}x_ix_j,
\end{equation}
\begin{equation}
\partial_k\mathcal{G} _{ij} = \frac{1}{r^3}\left(-\delta _{ij}x_k+\delta _{ik}x_j+\delta _{jk}x_i\right)-\frac{3}{r^5}x _ix _jx _k,
\end{equation}
\begin{equation}
\partial^2\mathcal{G} _{ij} = \frac{2}{r^3}\delta _{ij}-\frac{6}{r^5}x_ix_j,
\end{equation}
\begin{equation}
\partial_k\partial^2\mathcal{G} _{ij} = -\frac{6}{r^5}\left(\delta _{ij}x_k+\delta _{ik}x_j+\delta _{jk}x_i\right)+\frac{30}{r^7}x _ix _jx _k.
\end{equation}
\begin{equation}
\partial^2\partial^2\mathcal{G} _{ij} = 0.
\end{equation}
This last identity is expected since the velocity field is biharmonic by definition.

We consider the velocity prescribed on the spherical surface located at the origin as a superposition of translational, rotational, and symmetric $$\left(E_{ij}=E_{ji}\right)$$ straining modes,
\begin{equation}
u^p_i = U_i + \epsilon_{ijk}\Omega_jx_k + E_{ij}x_j.
\end{equation}
Generally, we may also explore higher-order components, but these are calculated in much the same way and will end up corresponding to higher-order modes of the multipole expansion, which are of less interest to us. The sphere also sits in an ambient flow, with the far-field velocity taking the form,
\begin{equation}
u^\infty_i = U^\infty_i + \epsilon_{ijk}\Omega^\infty_jx_k + E^\infty_{ij}x_j,
\end{equation}
where $$U^\infty_i$$, $$\Omega^\infty_j$$, and $$E^\infty_{ij}$$ are constant. The boundary conditions describe the velocity at the sphere's surface,
\begin{equation}
u_i\left(r=a\right)=u^p_i
\end{equation}
where $a$ is the radius of the sphere, and the velocity far from the sphere takes the far-field unperturbed values,
\begin{equation}
u_i\left(r\rightarrow\infty\right)=u^\infty_i.
\end{equation}
Note that we have assumed we know the velocity of the sphere within the moving fluid. Suppose instead we know the velocity of the sphere in a quiescent fluid and are interested in the dynamics in the presence of $$u^\infty_i$$. This could be the case if we are studying, for instance, a swimming body. In this case, if the body would translate with an intrinsic velocity $$u^s_i$$ in the absence of $$u^\infty_i$$, we simply replace $$u^p_i\rightarrow u^s_i+u^\infty_i$$.

Considering first the translation case. Notice at $$r=a$$,
\begin{equation}
\left(1+\frac{a^2}{6}\partial^2\right)\mathcal{G} _{ij}\left(r=a\right) = \frac{4}{3a}\delta _{ij},
\end{equation}
from which the velocity is represented as,
\begin{equation}
u_i\left(\mathbf{x}\right)=-6\pi\mu a\left(U^\infty_j-U_j\right)\left(1+\frac{a^2}{6}\partial^2\right)\frac{\mathcal{G} _{ij}\left(\mathbf{x}\right)}{8\pi\mu} + U^\infty_i,
\end{equation}
for a translating sphere, the multipole expansion has only these two terms, and only two derivative terms of the Green's function are necessary.

Now for the rotating case. At $$r=a$$, 
\begin{equation}
\epsilon_{jkl}\epsilon_{nml}\partial_m\mathcal{G} _{in}\left(r=a\right) = \partial_k\mathcal{G} _{ij}\left(r=a\right)-\partial_j\mathcal{G} _{ik}\left(r=a\right) = \frac{2}{a^3}\left(\delta _{ik}x_j-\delta _{ij}x_k\right) = \frac{2}{a^3}\epsilon _{jkl}\epsilon _{ilm}x_m.
\end{equation}
So set the velocity field,
\begin{equation}
u_i\left(\mathbf{x}\right)=4\mu\pi a^3\epsilon _{ljk}\frac{\partial_l\mathcal{G} _{ik}\left(\mathbf{x}\right)}{8\pi\mu}\left(\Omega_j-\Omega^\infty_j\right) + \epsilon _{ijk}\Omega^\infty _jx _k
\end{equation}

And lastly, for the strained case. At $$r=a$$,
\begin{equation}
\left(1+\frac{a^2}{10}\partial^2\right)\left(\partial_k\mathcal{G} _{ij}\left(r=a\right)+\partial_j\mathcal{G} _{ik}\left(r=a\right)\right) = -\frac{6}{5a^3}\left(\delta _{ij}x_k+\delta _{ik}x_j-\frac{2}{3}\delta _{jk}x_i\right),
\end{equation}
As $$E _{ij}=E _{ji}$$ and $$E _{kk}=0$$,
\begin{equation}
E _{jk}\left(1+\frac{a^2}{10}\partial^2\right)\partial_k\mathcal{G} _{ij}\left(r=a\right) = \frac{1}{2}E _{jk}\left(1+\frac{a^2}{10}\partial^2\right)\left(\partial_k\mathcal{G} _{ij}\left(r=a\right)+\partial_j\mathcal{G} _{ik}\left(r=a\right)\right) = -\frac{6}{5a^3}E _{ik}x_k,
\end{equation}
and we identify the velocity field as,
\begin{equation}
u_i\left(\mathbf{x}\right)= \frac{20}{3}\pi\mu a^3 \left(E _{jk}^\infty-E _{jk}\right) \left(1+\frac{a^2}{10}\partial^2\right)\frac{\partial_k\mathcal{G} _{ij}\left(\mathbf{x}\right)}{8\pi\mu} + E^\infty _{ij}x _j.
\end{equation}

In summary, we may express our velocity field as a sum of the translational, rotational, and straining modes,
\begin{equation}
u_i\left(\mathbf{x}\right)= \left[-F_j\left(1+\frac{a^2}{6}\partial^2\right) + S_{jk}\left(1+\frac{a^2}{10}\partial^2\right)\partial_k -\frac{1}{2} \epsilon_{jkl}T _k\partial_l\right]\frac{\mathcal{G} _{ij}\left(\mathbf{x}\right)}{8\pi\mu} + u^\infty _i,
\end{equation}
\begin{equation}\label{eq: force translating particle const background}
F_i = 6\pi\mu a\left(U^\infty _i -U _i\right),
\end{equation}

\begin{equation}
S_{jk} = \frac{20}{3}\pi\mu a^3 \left(E _{jk}^\infty-E _{jk}\right),
\end{equation}
\begin{equation}
T _k = 8\mu\pi a^3\left( \Omega^\infty_k-\Omega_k\right).
\end{equation}
$$F _i$$, $$S _{jk}$$, $$T _k$$ are the hydrodynamic force, stress, and torque associated with the particle's motion, as in this is the force exerted by the fluid onto the particle. Simply reverse the signs for the force experienced by the fluid.

### Faxén Laws
We require one last element, that being the inverse relations. We know how to find the flow given the background fluid motion and the behaviour of the sphere, but suppose we are instead given a non-constant background flow $$u^\infty_i\left(\mathbf{x}\right)$$, how do we determine the moments $$F_i\left(\mathbf{x}\right)$$, $$T_i\left(\mathbf{x}\right)$$, and $$S_{ij}\left(\mathbf{x}\right)$$?

We first consider purely translational motion, starting again with the reciprocal theorem, Eq. \ref{eq: Reciprocal theorem}, 
\begin{equation}\label{eq: flaxen reciprocal theorem}
\oint _{S_p} dS\ \sigma^1 _{ij}u^2_i \hat{n}_j + \int_V dV\ u^2 _i\partial _j\sigma^1 _{ij} = \oint _{S_p} dS\ \sigma^2 _{ij}u^1 _i \hat{n} _j + \int_V dV\ u^1 _i\partial _j\sigma^2 _{ij},
\end{equation}
where $$\hat{n}_i$$ is the vector pointing out of the particle into the fluid. Now let $$u^1 _i$$ be the solution for a spherical particle translating with velocity $$U_i$$ in a quiescent fluid. Note that this means that $$\partial _j\sigma _{ij}^1=0$$ since the auxiliary flow satisfies the homogeneous Stokes momentum equation in the fluid. For the second velocity field, $$u^2 _i$$, choose the velocity field generated by a point force $$P _i\delta\left(\mathbf{x}-\mathbf{y}\right)$$ where $$\mathbf{y}$$ lies outside of the particle and the particle is stationary. Because the second particle is stationary, we have $$u_i^2=0$$ on the particle surface, and $$\partial _j\sigma _{ij}^2=-P _i\delta\left(\mathbf{x}-\mathbf{y}\right)$$ from the point force. Inserting these fields into Eq. \ref{eq: flaxen reciprocal theorem},

\begin{equation}
F^2_i U_i  - P_iu^1 _i\left(\mathbf{y}\right) = 0,
\end{equation}

where $$F^2_i$$ is the hydrodynamic force on the second particle,

\begin{equation}
F^2_i = \oint _{S_p} dS\ \sigma^2 _{ij} \hat{n} _j.
\end{equation}

We can write $$u^1_i$$ with our singularity solution,

\begin{equation}
u^1 _i = U _j \mathcal{F}\left[ \frac{\mathcal{G} _{ij}\left( \mathbf{x}-\mathbf{\xi} \right) }{8\pi\mu} \right],
\end{equation}
\begin{equation}
\mathcal{F}\left[f\right]=6\pi\mu a\left( 1+\frac{a^2 }{6}\partial^2 \right)f,
\end{equation}

where $$\mathcal{F}$$ is a linear functional and $$\mathbf{\xi}$$ is the centre of the sphere, from which we identify

\begin{equation}
F^2_i = P_j \mathcal{F} \left[ \frac{\mathcal{G} _{ij}\left(\mathbf{y}-\mathbf{\xi}\right)}{8\pi\mu} \right].
\end{equation}

But the element in the functional is nothing more than the ambient $$u_i^2$$ field evaluated at the sphere centre, 
\begin{equation}
P_j \mathcal{F} \left[ \frac{\mathcal{G} _{ij}\left(\mathbf{y}-\mathbf{\xi}\right)}{8\pi\mu} \right] = \mathcal{F} \left[u^2_i\left(\mathbf{x}\right)\right]_{\mathbf{x}=\mathbf{\xi}}.
\end{equation}
Consider now an ambient flow field $$u_i^\infty\left(\mathbf{x}\right)$$. This flow field can be generated using our Green's function integral representation, Eq. \ref{eq: greens function integral rep}. So if the second particle sits in an ambient field $$u_i^\infty\left(\mathbf{x}\right)$$ constructed from a superposition of Green's functions, we may identify the force on the second particle as,

\begin{equation}\label{eq: force flaxen relation}
F_i = \mathcal{F} \left[ u_i^\infty\left(\mathbf{x}\right) \right]_{\mathbf{x}=\mathbf{\xi}} = 6\pi\mu a\left( 1+\frac{a^2 }{6}\partial^2 \right)u_i^\infty\left(\mathbf{x}\right)\| _{\mathbf{\xi}}.
\end{equation}

The force on the stationary particle is obtained using the same functional that gave us our multipole expansions. Notice that if the ambient flow is constant, $$u_i^\infty\left(\mathbf{x}\right)=U^\infty_i$$, we recover Eq. \ref{eq: force translating particle const background}.

By a similar argument with the reciprocal theorem, one can find the rotlet and stresslet,
\begin{equation}
T_i = 4\pi\mu a^3 \epsilon_{ijk}\partial_ju_k^\infty\| _{\mathbf{\xi}},
\end{equation}

\begin{equation}\label{eq: stresslet flaxen relation}
S_{ij} = \frac{20}{3}\pi\mu a^3\left( 1+\frac{a^2 }{10}\partial^2 \right)\frac{1}{2}\left(\partial_iu_j^\infty+\partial_ju_i^\infty\right)\| _{\mathbf{\xi}}.
\end{equation}

### Example Motion for Rigid Body Swimming
This is somewhat supplementary, but helpful in understanding our Faxén and multipole relations. Suppose we have a spherical swimmer in a flow $$u_i^\infty\left(\mathbf{x}\right)$$. In the absence of the flow, the swimmer would undergo rigid body motion with velocity $$U^s_i$$ and angular velocity $$\Omega^s_i$$, so that the velocity of the flow at the sphere's surface is given by,
\begin{equation}
u_i\left(r=a\right)=U^s_i+\epsilon_{ijk}\Omega^s_jr_k+u_i^\infty\left(r=a\right).
\end{equation}
We are interested in the resulting translational and rotational velocity of our swimmer in the flow, denoted by $$U^p_i$$ and $$\Omega^p_i$$. From our Faxén relation, Eq. \ref{eq: force flaxen relation}, the hydrodynamic force on the sphere is, 
\begin{equation}
F^\text{hydro}_i = 6\pi\mu a\left( 1+\frac{a^2 }{6}\partial^2 \right)\left(u_i^\infty\left(\mathbf{x}\right)-U^p_i\right)\| _{\mathbf{\xi}}.
\end{equation}
The sphere also experiences a propulsive swimming force $$F_i^\text{swim}$$, producing the translational swimming with velocity $$U^s_i$$. This force is found with Eq. \ref{eq: force translating particle const background},
\begin{equation}
F^\text{swim}_i = 6\pi\mu a U^s_i,
\end{equation}
where the sign has changed since $$F_i^\text{swim}$$ is the force required by the sphere to move through a quiescent fluid. The sphere's internal propulsive force must balance with the next hydrodynamic force, as there is no net force experienced by the swimming particle, resulting in,
\begin{equation}
F^\text{swim}_i + F^\text{hydro}_i = 0.
\end{equation}
From this, it is not difficult to identify the velocity of the sphere,
\begin{equation}
U^p_i = \left( 1+\frac{a^2 }{6}\partial^2 \right)\left(u_i^\infty\left(\mathbf{x}\right)\right)\| _{\mathbf{\xi}} + U^s_i.
\end{equation}
The angular velocity is similarly identified,
\begin{equation}
\Omega^p_i = \frac{1}{2}\epsilon _{ijk}\partial_j u_k^\infty\| _{\mathbf{\xi}} + \Omega^s_i.
\end{equation}

Supposing the position of the sphere center is given by $$X_i$$ and its orientation unit vector is $$p_i$$,
\begin{equation}
\dot{X}_i = U^p_i = \left( 1+\frac{a^2 }{6}\partial^2 \right)\left(u_i^\infty\left(\mathbf{x}\right)\right)\| _{\mathbf{X}} + U^s_i,
\end{equation}
\begin{equation}
\dot{p}_i = \epsilon _{ijk}\Omega^p_jp_k = \frac{1}{2}\epsilon _{ijk}\epsilon _{jlm}\partial_l u_m^\infty\| _{\mathbf{X}}p_k + \epsilon _{ijk}\Omega^s_jp_k.
\end{equation}

## The Singularity System for Ellipsoids
Now we are interested in the same procedure we did for spheres but for a triaxial ellipsoid. Let the surface of the ellipsoid be given by,
\begin{equation}
\frac{x^2}{a^2}+\frac{y^2}{b^2}+\frac{z^2}{c^2}=1,
\end{equation}
with $$a\geq b\geq c$$. We will present a solution base don the multipole expansion, as we did for spheres. 

First we define a few important quantities,
\begin{equation}
a_E=\sqrt{a^2-c^2},
\end{equation}
\begin{equation}
b_E=\sqrt{b^2-c^2},
\end{equation}
\begin{equation}
q\left(\mathbf{x}\right)=sqrt{1-\frac{x^2}{a_E^2}-\frac{y^2}{b_E^2}}.
\end{equation}

### Singularity System
Define the function,
\begin{equation}
H_n\left(\mathbf{x}\right)=\int_E dA\left(\mathbf{x'}\right)\ \frac{ q\left(\mathbf{x}'\right)^{2n-1}}{2\pi a_E b_E}\frac{1}{|\mathbf{x}-\mathbf{x}'|}.
\end{equation}
Because $$\partial_x^2\frac{1}{|\mathbf{x}-\mathbf{x}'|}=0$$ is harmonic, $$\partial_x^2 H_n\left(\mathbf{x}\right)=0$$ is also harmonic outside the region of integration by linearity. $$\int_E$$ is an integral over the surface of the ellipse. Now denote the similar function, $$H_n\left(\mathbf{x};u\right)$$ denoites that the particle size has been rescaled by $$u$$, $$a$$, $$b$$, and $$c$$, and replaced by $$au$$, $$bu$$, and $$cu$$, clearly $$H_n\left(\mathbf{x}\right)=H_n\left(\mathbf{x};1\right)$$. We show that $$H_{n+1}\left(\mathbf{x};1\right)$$ is related to an integral over $$u$$ of $$H_n\left(\mathbf{x};u\right)$$. Consider,
\begin{equation}\label{eq: H_n u transform}
u^{2n+2}H_n\left(\mathbf{x};u\right)=\int_{E_u} dA\left(\mathbf{x'}\right)\ \frac{u^{2n}}{2\pi a_E b_E}\left(1-\frac{x^2}{u^2a_E^2}+\frac{y^2}{u^2b_E^2}\right)^{n-\frac{1}{2}}\frac{1}{|\mathbf{x}-\mathbf{x}'|},
\end{equation}
\begin{equation}\label
=\int_{E_u} dA\left(\mathbf{x'}\right)\ \frac{u}{2\pi a_E b_E}\left(u^2-\frac{x^2}{a_E^2}-\frac{y^2}{b_E^2}\right)^{n-\frac{1}{2}}\frac{1}{|\mathbf{x}-\mathbf{x}'|},
\end{equation}
where we integrate over the scaled ellipsoid $$E_u$$. The integral over $$E_u$$ is over the region where,
\begin{equation}
\sqrt{1-\frac{x^2}{u^2a_E^2}-\frac{y^2}{u^2b_E^2}}\in\mathbb{R},
\end{equation}
since $$E_u$$ should be the region where the integrand is real. We can rewrite this condition as,
\begin{equation}
w\left(x,y\right)^2=\frac{x^2}{u^2a_E^2}+\frac{y^2}{u^2b_E^2}\leq u^2\leftrightarrow\left(x,y\right)\in E_u,
\end{equation}
which defines the region of integration $$E_u$$. Now consider the integral,
\begin{equation}
\int_0^1 du\ \int_{E_u} dA\left(\mathbf{x'}\right)\ = \int_{E} dA\left(\mathbf{x'}\right)\ \int_w^1 du\,
\end{equation}
where we swapped the order of integration to integrate over $$u$$ first. Performing this trick with Eq. \ref{eq: H_n u transform},
\begin{equation}
\int_0^1 du\ u^{2n+2}H_n\left(\mathbf{x};u\right)=\int_0^1 du\ \int_{E_u} dA\left(\mathbf{x'}\right)\ \frac{u}{2\pi a_E b_E}\left(u^2-w^2\right)^{n-\frac{1}{2}}\frac{1}{|\mathbf{x}-\mathbf{x}'|}=\int_{E} dA\left(\mathbf{x'}\right)\ \int_w^1 du\ \frac{u}{2\pi a_E b_E}\left(u^2-w^2\right)^{n-\frac{1}{2}}\frac{1}{|\mathbf{x}-\mathbf{x}'|},
\end{equation}

\begin{equation}
= \int_{E} dA\left(\mathbf{x'}\right)\ \frac{1}{2\pi a_E b_E}\frac{1}{2n+1}\left(1-w^2\right)^{n+\frac{1}{2}}\frac{1}{|\mathbf{x}-\mathbf{x}'|}= \int_{E} dA\left(\mathbf{x'}\right)\ \frac{1}{2\pi a_E b_E}\frac{q\left(\mathbf{x}'\right)^{2n+1}}{2n+1}\frac{1}{|\mathbf{x}-\mathbf{x}'|},
\end{equation}
so we may relate,
\begin{equation}
\left(2n+1\right)\int_0^1 du\ u^{2n+2}H_n\left(\mathbf{x};u\right)=H_{n+1}\left(\mathbf{x};1\right).
\end{equation}
This is neat and will be helpful. 

Now consider the seemingly unrelated function,
\begin{equation}
G_n\left(\mathbf{x}\right)=\int_{\lambda\left(\mathbf{x}\right)}^\infty dt\ \delta\left(t\right)^{-1}p\left(x,y,z,t)^n,
\end{equation}
where,
\begin{equation}
\delta\left(t\right)=\sqrt{\left(a^2+t\right)\left(b^2+t\right)\left(c^2+t\right)},
\end{equation}
\begin{equation}
p\left(x,y,z,t)=\frac{x^2}{a^2+t}+\frac{y^2}{b^2+t}+\frac{z^2}{c^2+t}-1,
\end{equation}
and $$\lambda\left(\mathbf{x}\right)$$ is the positive root of $$p\left(x,y,z,t)=0$$. We may establish a similar relation between $$G_n\left(\mathbf{x};u\right)$$ and $$G_{n+1}\left(\mathbf{x};1\right)$$ as we did for $$H_n$$. Consider,
\begin{equation}
int_0^1 du\ u^{2n+2}G_n\left(\mathbf{x};u\right)=\int_0^1 du\ \int_{\lambda\left(\mathbf{x};u\right)}^\infty dt\ \delta\left(t;u\right)^{-1}u^{2n+2}\left(\frac{x^2}{u^2a^2+t}+\frac{y^2}{u^2b^2+t}+\frac{z^2}{u^2c^2+t}-1\right)^n.
\end{equation}
Now change variables with $$\tau=u^{-2} t$$, and $$v\left(u\right)=\lambda\left(u\right)/u^2$$,
\begin{equation}\label{eq: G unchanged order integral}
=\int_0^1 du\ \int_{v\left(u\right)}^\infty d\tau\ \delta\left(\tau\right)^{-1}u\left( \frac{x^2}{a^2+\tau }+\frac{y^2}{b^2+\tau }+\frac{z^2}{ c^2+\tau }-u^2 \right)^n.
\end{equation}
Now we change the order of integration. We know,
\begin{equation}
u^2v\left(u\right)=\lambda\left(u\right)\rightarrow \frac{x^2}{u^2a^2+u^2v}+\frac{y^2}{u^2b^2+u^2v}+\frac{z^2}{u^2c^2+u^2v}=1\rightarrow \frac{x^2}{a^2+u^2v}+\frac{y^2}{b^2+v}+\frac{z^2}{c^2+v}=u^2.
\end{equation}
Therefore the inverse function of $$v\left(u\right)$$, $$v^{-1}$$ which is defined by, $$v^{-1}\left(v\left(u\right)\right)=u$$, is given by,
\begin{equation}
v^{-1}\left(v\right)=\sqrt{ frac{x^2}{a^2+v}+\frac{y^2}{b^2+v}+\frac{z^2}{c^2+v} }.
\end{equation}
With this, the region of integration in Eq. \ref{eq: G unchanged order integral} is,
\begin{equation}
0\leq u\leq 1\quad v\left(u\right)\leq\tau\leq\infty \leftrightarrow v\left(1\right)\leq\tau\leq\infty\quad v^{-1}\left(\tau\right)\leq u \leq 1,
\end{equation}
and we may rewrite,
\begin{equation}
int_0^1 du\ u^{2n+2}G_n\left(\mathbf{x};u\right)=\int_\lambda^\infty d\tau\ \int_{v^{-1}\left(\tau\right)}^1 du\ \delta\left(\tau\right)^{-1}u\left( \left(v^{-1}\left(\tau\right)\right)^2-u^2 \right)^n,
\end{equation}
\begin{equation}
=-\frac{1}{2\left(n+1\right)}\int_\lambda^\infty d\tau\ \int_{v^{-1}\left(\tau\right)}^1 du\ \delta\left(\tau\right)^{-1} \left( \left(v^{-1}\left(\tau\right)\right)^2-u^2 \right)^{n+1}.
\end{equation}
so,
\begin{equation}
-2\left(n+1\right)int_0^1 du\ u^{2n+2}G_n\left(\mathbf{x};u\right)=G_{n+1}\left(\mathbf{x};1\right).
\end{equation}

Finally, we relate $$H_n$$ with $$G_n$$ via induction. Consider $$G_0$$,
\begin{equation}
G_0\left(\mathbf{x}\right)=\int_{\lambda\left(\mathbf{x}\right)}^\infty dt\ \delta\left(t\right)^{-1}.
\end{equation}
We show $$G_0$$ is harmonic.
\begin{equation}
\partial_\lambda G_0 = -\frac{1}{\Delta\left(\lambda)}\rightarrow\partial_i G_0 = -\frac{1}{\Delta\left(\lambda)}\partial_i\lambda.
\end{equation}
\begin{equation}
\partial^2 G_0 = -\frac{\partial^2\lambda}{\Delta\left(\lambda)}+\frac{\partial_\lambda\Delta\left(\lambda)}{\Delta\left(\lambda)^2}|\partial_i\lambda|^2.
\end{equation}
Evaluating using the definition of $$\lambda\left(\mathbf{x}\right)$$,
\begin{equation}
\partial_i\left(\frac{x^2}{a_1^2+\lambda}+\frac{y^2}{a_2^2+\lambda}+\frac{z^2}{a_3^2+\lambda}\right)=0\rightarrow\partial_i\lambda=\frac{2x_i}{a_i^2+\lambda}\frac{1}{S\left(\lambda\right)},
\end{equation}
with,
\begin{equation}
S\left(\lambda\right)=\frac{x^2}{\left(a^2+\lambda\right)^2}+\frac{y^2}{\left( b^2+\lambda \right)^2}+\frac{z^2}{\left(c^2+\lambda \right)^2},
\end{equation}
where $$a_i=a,b,c$$. This also gives us,
\begin{equation}
|\partial_i\lambda\end{equation}|^2=\frac{4}{S}
\end{equation}
Now for the second derivative, take another derivative, for instance along $$x$$,
\begin{equation}
\partial_x^2\lambda=\frac{2}{a_1^2+\lambda}\frac{1}{S\left(\lambda\right)}-\frac{4x^2}{\left(a_1^2+\lambda\right)^3}\frac{1}{S\left(\lambda\right)^2}-\frac{2x}{a_1^2+\lambda}\frac{1}{S\left(\lambda\right)^2}\left( \frac{2x}{\left(a_1^2+\lambda\right)^2}-\frac{4x}{a_1^2+\lambda}\frac{T\left(\lambda\right)}{S\left(\lambda\right)}\right),
\end{equation}
with,
\begin{equation}
T\left(\lambda\right)=\frac{x^2}{\left(a^2+\lambda\right)^3}+\frac{y^2}{\left( b^2+\lambda \right)^3}+\frac{z^2}{\left(c^2+\lambda \right)^3}.
\end{equation}
So the laplaciacion of $$\lambda$$ is,
\begin{equation}
\partial^2\lambda=\left(\frac{1}{a_1^2+\lambda}+\frac{1}{a_2^2+\lambda}+\frac{1}{a_3^2+\lambda}\right)\frac{2}{S\left(\lambda\right)}-\frac{4T\left(\lambda\right)}{S\left(\lambda\right)^2}-\frac{4T\left(\lambda\right)}{S\left(\lambda\right)^2}+\frac{8T\left(\lambda\right)}{S\left(\lambda\right)^2},
\end{equation}
\begin{equation}
=\left(\frac{1}{a_1^2+\lambda}+\frac{1}{a_2^2+\lambda}+\frac{1}{a_3^2+\lambda}\right)\frac{2}{S\left(\lambda\right)}.
\end{equation}
With,
\begin{equation}
\frac{\partial_\lambda\Delta\left(\lambda)}{\Delta\left(\lambda)}=\frac{1}{2}\left(\frac{1}{a_1^2+\lambda}+\frac{1}{a_2^2+\lambda}+\frac{1}{a_3^2+\lambda}\right),
\end{equation}
we see,
\begin{equation}
\partial^2\lambda=\frac{\partial_\lambda\Delta\left(\lambda)}{\Delta\left(\lambda)}|\partial_i\lambda\end{equation}|^2,
\end{equation}
from which we find that
\begin{equation}
\partial^2 G_0 = -\frac{\partial^2\lambda}{\Delta\left(\lambda)}+\frac{\partial_\lambda\Delta\left(\lambda)}{\Delta\left(\lambda)^2}|\partial_i\lambda|^2 = 0,
\end{equation}
and $$G_0$$ is biharmonic as we hoped. 

Because $$G_0$$ is biharmonic, we may express it in the region outside of the ellipsoid as,












## Method of Reflections for Widely Separated Spheres
We can solve for the flow in the presence of a single sphere; can we resolve the problem with multiple spheres? Yes, more or less. The idea behind the method of reflections is to expand the velocity field in terms of the ratio $$\alpha=a/R$$, where $$a$$ is the sphere's radius and $$R$$ is the separation between the spheres. We assume this ratio is small such that the expansion can be truncated at a given order and provide an accurate approximation of the multiple-sphere velocity field.

We consider two spheres centred at $$\mathbf{x}_1$$ and $$\mathbf{x}_2$$ with the same radius $$a$$ (for simplicity; in general, the sphere radii can differ). We take the spheres to be nonrotating and translating with velocities $$U^1_i$$ and $$U^2_i$$. The zeroth-order solution is simply the Stokes solution for the disturbance caused by the isolated spheres,
\begin{equation}
u_i^{(0)}\left(\mathbf{x}\right)  = u_i^{1\ (0)}\left(\mathbf{x}\right) + u_i^{2\ (0)}\left(\mathbf{x}\right) + u^\infty _i,
\end{equation}
and the ambient $$u^\infty _i=U^\infty_i$$ is purely translation. The zeroeth-order contribution from sphere $$a$$ is,
\begin{equation}
u_i^{a\ (0)}\left(\mathbf{x}\right) = -F_j^{a\ (0)} \left(1+\frac{a^2}{6}\partial^2\right) \frac{\mathcal{G} _{ij}\left(\mathbf{x} - \mathbf{x}^a\right)}{8\pi\mu} ,
\end{equation}
\begin{equation}
F_j^{a\ (0)} = 6\pi\mu a\left(U^\infty _j -U^a _j\right).
\end{equation}
We can equivalently treat the case of rotated and strained spheres using our spherical singularity expansion.

The zeroeth-order field is not quite correct since the boundary conditions at the translating spheres are not satisfied. For each translating sphere, the velocity field at the sphere surface should be the translating velocity,

\begin{equation}
u_i\left(\mathbf{x} = \mathbf{x}^a\right) = U_i^a,
\end{equation}
In our zeroth-order expansion, the boundary condition is not satisfied due to the influence of the partner particle. For instance, at the first sphere,
\begin{equation}
u_i^{1\ (0)}\left(\mathbf{x} = \mathbf{x}^1\right) = U_i^1 + u_i^{2\ (0)}\left(\mathbf{x} = \mathbf{x}^1\right) + u^\infty _i.
\end{equation}
Our second-order corrections are the reflection fields designed to cancel the contribution from the opposing sphere. For the first particle, the first-order correction is a velocity field such that
\begin{equation}
u_i^{1\ (1)}\left(\mathbf{x} = \mathbf{x}^1\right) = - u_i^{2\ (0)}\left(\mathbf{x} = \mathbf{x}^1\right),
\end{equation}
such that the combined velocity field,
\begin{equation}
u_i^{(1)}  = u_i^{1\ (0)} + u_i^{2\ (0)} + u_i^{1\ (1)} + u_i^{2\ (1)}
\end{equation}
has a boundary error that is of a higher order than the previous velocity field. This scheme can be generalized as the particle fields "reflect" on each other. For the n-th order first sphere velocity field, we find a velocity field satisfying,
\begin{equation}
u_i^{1\ (n)}\left(\mathbf{x} = \mathbf{x}^1\right) = - u_i^{2\ (n-1)}\left(\mathbf{x} = \mathbf{x}^1\right).
\end{equation}

With our spherical singularity solution and Faxén Laws, finding reflected fields is not too difficult. For the $$a$$-th sphere, with $$b$$ indices representing the opposite sphere,

\begin{equation}
u_i^{a\ (1)}\left(\mathbf{x}\right) = -\left[ -F _j^{a\ (1)}\left(1+\frac{a^2}{6}\partial^2\right) + S^{a\ (1)} _{jk}\left(1+\frac{a^2}{10}\partial^2\right)\partial _k -\frac{1}{2} \epsilon _{jkl} T^{a\ (1)} _k\partial _l\right]\frac{\mathcal{G} _{ij}\left(\mathbf{x}-\mathbf{x}^a\right)}{8\pi\mu}.
\end{equation}

The force, stress, and torque are obtained with the Faxén relations for the first sphere,
\begin{equation}
F_i^{1\ (1)} = 6\pi\mu a\left( 1+\frac{a^2 }{6}\partial^2 \right)u_i^{2\ (0)}\| _{ \mathbf{x}=\mathbf{x}^1 },
\end{equation}
\begin{equation}
=-F_j^{2\ (0)}\left[  \frac{3}{4}\left(\delta _{ij}+d _id _j\right)\alpha +  \frac{1}{2}\left(\delta _{ij}-3d _id _j\right)\alpha^3 \right],
\end{equation}
\begin{equation}
T_i^{1\ (1)} =  4\pi\mu a^3 \epsilon _{ijk}\partial_ju_k^{2\ (0)}\| _{ \mathbf{x}=\mathbf{x}^1 },
\end{equation}
\begin{equation}
= - a \alpha^2 \epsilon _{ijk}F_j^{2\ (0)}d_k,
\end{equation}
\begin{equation}
S _{ij}^{1\ (1)} = \frac{20}{3}\pi\mu a^3\left( 1+\frac{a^2 }{10}\partial^2 \right)\frac{1}{2}\left(\partial_iu_j^{2\ (0)}+\partial_ju_i^{2\ (0)}\right)\| _{ \mathbf{x}=\mathbf{x}^1 },
\end{equation}
\begin{equation}
 = -a F_k^{2\ (0)}\left[ \frac{5}{6}\left(\delta _{ij}d_k - 3d _id _jd _k\right)\alpha^2 + \frac{4}{3}\left(-\delta _{ij}d_k-2\delta _{ik}d_j+5d _id _jd _k\right)\right].
\end{equation}
Recall that $$\alpha=a/R$$ is our small expansion parameter. $$R$$ is the distance between the two spheres, $$R=|\mathbf{x}^1-\mathbf{x}^2|$$ and $$d_i=\left(x^1_i-x_i^2\right)/R$$ is a unit vector pointing between them. One can repeat this process for the second sphere and equivalently for all higher moments to expand the velocity field as a series in terms of $$\alpha$$. For computations, it is often more practical to proceed in wavenumber space where one may express the reflection operation as a matrix transform.

We can perform an identical expansion for the cases of an initial torque or stress. In particular, a particle in an ambient stress field is relevant for our later viscosity calculation; this is the case in which,
\begin{equation}
u_i\left(\mathbf{x} =  \mathbf{x} ^a\right) = E^a_{ij}x_j
\end{equation}
so the zeroeth-order contribution is,
\begin{equation}
u_i\left(\mathbf{x}\right)^a = S^{a\ (0)} _{jk}\left(1+\frac{a^2 }{10}\partial^2\right)\partial_k\frac{\mathcal{G} _{ij}\left(\mathbf{x} - \mathbf{x}^a\right)}{8\pi\mu},
\end{equation}
\begin{equation}
S^{a\ (0)} _{jk} = \frac{20}{3}\pi\mu a^3\left(E^\infty _{jk}- E^a _{jk}\right).
\end{equation}
The first-order stresslet contribution to the first sphere is,
\begin{equation}
S _{ij}^{1\ (1)} = \frac{20}{3}\pi\mu a^3\left( 1+\frac{a^2 }{10}\partial^2 \right)\frac{1}{2}\left(\partial_iu_j^{2\ (0)}+\partial_ju_i^{2\ (0)}\right)\| _{ \mathbf{x}=\mathbf{x}^1 },
\end{equation}
\begin{equation}
= \frac{5}{12} S^{2\ (0)} _{kl} a^3\left( 1+\frac{a^2 }{10}\partial^2 \right)\left(1+\frac{a^2 }{10}\partial^2\right)\partial_l\left(\partial_i\mathcal{G} _{jk}\left(R\right)+\partial_j\mathcal{G} _{ik}\left(R\right)\right)
\end{equation}
\begin{equation}
= \frac{5}{12} S^{2\ (0)} _{kl} a^3\left[\partial_i\partial_l\mathcal{G} _{jk}\left(R\right)+\partial_j\partial_l\mathcal{G} _{ik}\left(R\right) + \frac{a^2}{5}\left( \partial_i\partial_l\partial^2\mathcal{G} _{jk}\left(R\right)+\partial_j\partial_l\partial^2\mathcal{G} _{ik}\left(R\right)\right) \right],
\end{equation}
\begin{equation}
= \frac{5}{12} S^{2\ (0)} _{kl} a^3\left[\left( \frac{2}{R^3}\delta _{ij}\delta _{kl} -\frac{6}{R^3}\delta _{ij}d_kd_l-\frac{6}{R^3}\left(\delta _{kl}d _id _j + \delta _{jl}d _id _k + \delta _{il}d _jd _k\right)+\frac{30}{R^3}d _id _jd _kd _l
\right) \right.
\end{equation}
\begin{equation}
\left. + \frac{a^2}{5}\left( -\frac{12}{R^5}\left(\delta _{ij}\delta _{lk}+\delta _{ik}\delta _{jl}+\delta _{jk}\delta _{il}\right)+\frac{60}{R^5}\left(\delta _{ij}d_k+\delta _{ik}d_j+\delta _{jk}d_i\right)d_l+\frac{60}{R^5}\left(\delta _{il}d _kd _j + \delta _{jl}d _id _k + \delta _{kl}d_id _j\right)-\frac{420}{R^5}d _id _jd _kd _l\right) \right],
\end{equation}
dropping a few terms on the basis that $$S^{2\ (0)} _{kl}=S^{2\ (0)} _{lk}$$ and $$S^{2\ (0)} _{kk}=0$$,
\begin{equation}\label{eq: S11 stresslet reflection}
S _{ij}^{1\ (1)} = \frac{5}{2} S^{2\ (0)} _{kl} \alpha^3\left[\left( -\delta _{ij}d_kd_l- \delta _{jl}d _id _k - \delta _{il}d _jd _k +5d _id _jd _kd _l \right) + \frac{\alpha^2}{5}\left( -4\delta _{ik}\delta _{jl}+10\left(\delta _{ij}d_k+2\delta _{ik}d_j+2\delta _{jk}d_i\right)d_l-70d _id _jd _kd _l\right) \right].
\end{equation}
This looks a little scary, but we will be able to simplify further. 


## The Effective Viscosity for a Suspension of Widely Separated Spheres
We are finally able to approach the problem of interest. The idea is as follows. Suppose we have a suspension of spherical particles in a fluid. The suspension is dilute such that the particle number density is low, and from far enough away we can treat the suspension as an ordinary fluid. This suspension fluid will not have the same viscosity as the un-suspension-ified fluid due to the particles within. Our objective is to use what we know about the interactions of particles and fluids to compute the effective viscosity of this fluid as a power series in the particle number density, which is a small number. 

Formally, consider a fluid within a volume $$V$$ containing a suspension of spherical particles with volume fraction $$\phi$$. Let there be $$N$$ particles with radius $$a$$, such that the volume fraction is,
\begin{equation}
\phi\frac{4}{3}\pi N\frac{a^3}{V}\ll 1.
\end{equation}
In addition to considering a dilute suspension, we consider the limit of a widely separated suspension such that the average particle separation scale is small,
\begin{equation}
\langle\alpha\rangle = \frac{a}{\langle R\rangle}\ll 1.
\end{equation}
This follows from our assumption of a dilute suspension. As
\begin{equation}
\langle R \rangle \sim \left(\frac{V}{N}\right)^{\frac{1}{3}}\sim\phi^{-\frac{1}{3}}\rightarrow\alpha\sim\phi^{\frac{1}{3}},
\end{equation}
and we can use our method of reflections to expand the inter-particle interactions as a power series in $$\alpha\sim\phi^{\frac{1}{3}}$$. 

Our objective is to compute the effective fluid viscosity $$\mu^\text{eff}$$ as a power series in $$\phi$$. The effective viscosity is such that the bulk average stress looks Newtonian,
\begin{equation}
\langle\sigma_{ij}\rangle = -\langle p\rangle \delta_{ij} + 2\mu^\text{eff}\langle e_{ij}\rangle.
\end{equation}
The average stress is computed by integrating over the domain $$V$$,
\begin{equation}
\langle\sigma_{ij}\rangle = \frac{1}{V}\int_{V} dV\ \sigma_{ij} = -\langle p\rangle \delta_{ij} + 2\mu \langle e_{ij}\rangle + \frac{1}{V}\int_{\sum V_n}dV\ \sigma_{ij},
\end{equation}
where we have separated the stress tensor over the fluid portion with the fluid viscosity $$\mu$$ plus a contribution from averaging over all particles, where $$\sum V_n$$ represents the region occupied by our suspended particles. Define this as the particle stress contribution so,
\begin{equation}
\sigma_{ij}^\text{particle} = \frac{1}{V}\sum_n\int_{V_n}dV\ \sigma_{ij} = \frac{1}{V}\sum_n\int_{V_n}dV\ \partial_k\left(\sigma_{ik}x_j\right) - \frac{1}{V}\sum_n\int_{V_n}dV\ x_j\partial_k\sigma_{ik}
\end{equation}
\begin{equation}
= \frac{1}{V}\sum_n\oint_{S_n}dS\ \sigma_{ik}x_j\hat{n}_k = \frac{1}{V}\sum _n S _{ij}^{(n)}  = \frac{N}{V}\langle S _{ij}\rangle.
\end{equation}
where $$\langle S _{ij}\rangle$$ is the average stresslet over all $$N$$ particles and we have used the fact that $$\partial _k\sigma _{ik}=0$$ in the absence of external forcings. So all we really need to do is calculate the average stresslet, $$\langle S _{ij}\rangle$$, over all particles in the suspension. We write this average as a series,
\begin{equation}
\langle S _{ij}\rangle = \langle S _{ij}^0\rangle + \langle S _{ij}^1\rangle + ...
\end{equation}
Each order represents a higher order of particle-particle interactions. $$\langle S _{ij}^0 \rangle$$ are the stresslet effects from isolated particles, $$\langle S _{ij}^1 \rangle$$ are the stresslet effects from the first particle-particle reflection interactions, $$\langle S _{ij}^2$$ are the effects from the second reflection, and so on.

### Linear Corrections 
At order $$\phi^0$$, the particle interactions are not considered, and the stresslet is obtained from the Faxén relation, Eq. \ref{eq: stresslet flaxen relation},
\begin{equation}
\langle S _{ij}^0\rangle = \frac{20}{3}\pi\mu a^3 \left(1 + \frac{a^2}{10}\partial^2\right)\langle e _{ij}\rangle.
\end{equation}
And to linear order, the particle stress is,
\begin{equation}
\frac{N}{V}\langle S _{ij}^0\rangle = \frac{20}{3}\pi\mu a^3 \frac{N}{V}\left(1 + \frac{a^2}{10}\partial^2\right)\langle e _{ij}\rangle = 5\mu\phi\langle e _{ij}\rangle + \mathcal{O}\left(\alpha^2\phi\right),
\end{equation}
we drop the higher-order correction since we know $$\alpha\sim\phi^{\frac{1}{3}}$$, we will return to these corrections later. To linear order in $$\phi$$, we obtain the effective viscosity,
\begin{equation}
\langle\sigma _{ij}\rangle = -\langle p\rangle \delta _{ij} + 2\mu\left(1+\frac{5}{2}\phi+\mathcal{O}\left(\phi^{5/3}\right)\right)\langle e _{ij}\rangle.
\end{equation}

### Quadratic Corrections 
At linear order in $$\phi$$, computing $$\langle S _{ij}^1\rangle$$ is more involved since we need to consider the particle-particle interactions. Let $$\mathcal{P}\left(\mathbf{x}_2|\mathbf{x}_1\right)$$ be the probability distribution of encountering a particle at $$\mathbf{x}_2$$ given a particle exists at $$\mathbf{x} _1$$. We normalize this probability distribution such that,
\begin{equation}
\int _{R\geq 2a} dV\left(\mathbf{x}_2\right)\ \mathcal{P}\left(\mathbf{x}_2|\mathbf{x}_1\right) = N - 1,
\end{equation}
where the volume integral is from $$R=2a$$ since particles cannot touch each other. The distribution is normalized to $$N-1$$ to account for the missing particle not being counted at $$\mathbf{x}_1$$. So $$\langle S _{ij}^1\rangle$$ is obtained by,
\begin{equation}
\langle S _{ij}^1\rangle = \int _{R\geq 2a} dV\left(\mathbf{x}_2\right)\ \mathcal{P}\left(\mathbf{x}_2|\mathbf{x}_1\right) S^\text{interaction} _{ij}\left(\mathbf{x}_1,\mathbf{x}_2\right),
\end{equation}
where $$S^\text{interaction} _{ij}$$ is the interaction stresslet between two particles, computed only from the interaction terms. To calculate $$S^\text{interaction} _{ij}$$, we return to the method of reflections. For the two-sphere case, $$S^\text{interaction} _{ij}$$ is given by the reflection stresslet, $$S _{ij}^{1\ (1)}$$, Eq. \ref{eq: S11 stresslet reflection}. 
\begin{equation}
S^\text{interaction} _{ij} = S _{ij}^{1\ (1)} = \frac{5}{2} S^{2\ (0)} _{kl} \alpha^3\left[\left( -\delta _{ij}d_kd_l- \delta _{jl}d _id _k - \delta _{il}d _jd _k +5d _id _jd _kd _l \right) + \frac{\alpha^2}{5}\left( -4\delta _{ik}\delta _{jl}+10\left(\delta _{ij}d_k+2\delta _{ik}d_j+2\delta _{jk}d_i\right)d_l-70d _id _jd _kd _l\right) \right],
\end{equation}
and we are left with computing the integral,
\begin{equation}\label{eq: integral phi^2 correction}
\frac{5}{2} S^{2\ (0)} _{kl} a^3 \int _{R\geq 2a} dV\left(\mathbf{x}\right)\ \mathcal{P}\left(\mathbf{x}|\mathbf{0}\right) R^{-3} \left[\left( -\delta _{ij}d_kd_l- \delta _{jl}d _id _k - \delta _{il}d _jd _k +5d _id _jd _kd _l \right) + \frac{a^2}{5}R^{-2}\left( -4\delta _{ik}\delta _{jl}+10\left(\delta _{ij}d_k+2\delta _{ik}d_j+2\delta _{jk}d_i\right)d_l-70d _id _jd _kd _l\right) \right].
\end{equation}
We have set $$\mathbf{x}_1=\mathbf{0}$$ for convenience. 

We have a few integrals to do, but we should first set the probability distribution $$\mathcal{P}$$. This describes how particles are arranged around each other. A most flatfooted approach is assuming an isotropic particle distribution such that the probability density is constant and,
\begin{equation}
\mathcal{P}\left(\mathbf{x}\right)=0\quad\text{if}\ R\leq2a,
\end{equation}
\begin{equation}
\mathcal{P}\left(\mathbf{x}\right)=\frac{N-1}{V}\quad\text{if}\ R>2a.
\end{equation}
This is saying that the probability of encountering a particle is the same everywhere, which is a decent first-order approximation for our dilute suspension. We will study this assumption closer later.

We will calculate the integral of Eq. \ref{eq: integral phi^2 correction} in this case. A few useful identities to deal with the angular integrals,
\begin{equation}
 \int d\Omega\ d_kd_l = \frac{4}{3}\pi\delta _{kl}
\end{equation}
\begin{equation}
 \int d\Omega\ d _id _jd _kd _l = \frac{4}{15}\pi \left(\delta _{ij}\delta _{kl} + \delta _{ik}\delta _{jl} + \delta _{il}\delta _{kj}\right).
\end{equation}

Performing the angular integration portion of our integral,
\begin{equation}
\int d\Omega\ \left(-\delta _{ij}d_kd_l- \delta _{jl}d _id _k - \delta _{il}d _jd _k +5d _id _jd _kd _l\right) = 0
\end{equation}
\begin{equation}
\int d\Omega\ \left( -4\delta _{ik}\delta _{jl}+10\left(\delta _{ij}d_k+2\delta _{ik}d_j+2\delta _{jk}d_i\right)d_l-70d _id _jd _kd _l\right) = 0
\right]

\end{equation}



-16\delta _{ik}\delta _{jl}+\frac{160}{3}\delta _{jl}\delta _{ik}-\frac{112}{3}\delta _{il}\delta _{kj}



14 * 4/3








Using the angular integrals and the fact that $$S^{2\ (0)} _{kk} = 0$$, we find
\begin{equation}
S^{2\ (0)} _{kl} \int _{R\geq 2a} dV R^{-5}\left( -\delta _{ij}x_kx_l- \delta _{jl}x _ix _k - \delta _{il}x _jx _k +5R^{-2}x _ix _jx _kx _l \right) = 0,
\end{equation}
\begin{equation}
S^{2\ (0)} _{kl} \int _{R\geq 2a} dV R^{-7}\left( -4R^2\delta _{ik}\delta _{jl}+10\left(\delta _{ij}x_k+2\delta _{ik}x_j+2\delta _{jk}x_i\right)x_l-70R^{-2}x _ix _jx _kx _l \right)  = S^{2\ (0)} _{kl} \int _{r\geq 2a}dr\ \pi r^{-3}\left[ -16\delta _{ik}\delta _{jl} +\frac{40}{3}\left(\delta _{ij}\delta _{kl} + 2\delta _{ik}\delta _{jl} + 2\delta _{jk}\delta _{il}\right) - \frac{56}{3} \left(\delta _{ij}\delta _{kl} + \delta _{ik}\delta _{jl} + \delta _{il}\delta _{kj}\right) \right] = 

\frac{10}{3}\pi S^{2\ (0)} _{ij}\frac{1}{8a^2}


x_k+2\delta _{ik}x_j+2\delta _{jk}x_i\right)







-16\pi\delta _{ik}\delta _{jl} +32\pi\left(\delta _{ik}\delta _{jl}+\delta _{jk}\delta _{il}\right) - \frac{56}{3}\pi \left( \delta _{ik}\delta _{jl} + \delta _{il}\delta _{kj}\right)\right] = 30\pi S^{2\ (0)} _{ij}\frac{1}{8a^2}.
\end{equation}
We have set the region size $$V$$ to be large. All in all, we obtain,
\begin{equation}
\langle S _{ij}^1\rangle  = \frac{15}{8}\pi S^{2\ (0)} _{ij}  a^3 \frac{N-1}{V} = \frac{25}{2}\pi^2\mu a^6 \frac{N-1}{V} \langle e _{ij}\rangle = 

\end{equation}

\frac{25 * 3* 3}{2 * 4 * 4} \phi \mu \frac{4}{3} \pi a^3

\frac{75}{4 * 4}





### Sources
The notes here are based on Kim and Karrila's _Microhydrodynamics Principles and Selected Applications_ and Eric Lauga's _Fluid Dynamics of Cell Motility_, both great books with rather boring titles.

