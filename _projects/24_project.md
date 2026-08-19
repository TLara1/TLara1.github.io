---
layout: page
title: On Slender Body Theory, Jeffery Orbits, and the Rheology of Dilute Spheroid Suspensions
description:
img: 
importance: 84
category: Maths
related_publications: false
toc:
  beginning: true
---

## Introduction


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
\begin{equation}
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

We consider the velocity prescribed on the spherical surface as a superposition of translational, rotational, and symmetric $$\left(E_{ij}=E_{ji}\right)$$ straining modes,
\begin{equation}
u^p_i = U_i + \epsilon_{ijk}\Omega_jx_k + E_{ij}x_j.
\end{equation}
Generally, we may also explore higher-order components, but these are calculated in much the same way and will end up corresponding to higher-order modes of the multipole expansion, which are of less interest to us. The sphere also sits in an ambient flow, with the far-field velocity taking the form,
\begin{equation}
u^\infty_i = U^\infty_i + \epsilon_{ijk}\Omega^\infty_jx_k + E^\infty_{ij}x_j.
\end{equation}
The boundary conditions describe the velocity at the sphere's surface,
\begin{equation}
u_i\left(r=a\right)=u^p_i
\end{equation}
where $a$ is the radius of the sphere, and the velocity far from the sphere takes the far-field unperturbed values,
\begin{equation}
u_i\left(r\rightarrow\infty)=u^\infty_i.
\end{equation}
Note that we have assumed we know the velocity of the sphere within the moving fluid. Suppose instead we know the velocity of the sphere in a quesient fluid and are intested in the dynamics in the presence of $$u^\infty_i$$. This could be the case if we are studying, for instance, a swimming body. In this case, if the body would translate with an intrinsic velocity $$u^s_i$$ in the absence of $$u^\infty_i$$, we simply replace $$u^p_i\rightarrow u^s_i+u^\infty_i$$.

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
\begin{equation}
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
We require one last element, that being the inverse relations. Suppose we are given the ambient flow and particle motion; how do we determine the moments?

We begin again with the reciprocal theorem, Eq. \ref{eq: Reciprocal theorem}, 
\begin{equation}\label{eq: flaxen reciprocal theorem}
\oint _{S_p} dS\ \sigma^1 _{ij}u^2_i \hat{n}_j + \int_V dV\ u^2 _i\partial _j\sigma^1 _{ij} = \oint _{S_p} dS\ \sigma^2 _{ij}u^1 _i \hat{n} _j + \int_V dV\ u^1 _i\partial _j\sigma^2 _{ij},
\end{equation}

where $$\hat{n}_i$$ is the vector pointing out of the particle into the fluid. Now let $$u^1 _i$$ be the solution for a spherical particle translating with velocity $$U_i$$ in a quiescent fluid. Note that this means that $$\partial _j\sigma _{ij}^1=0$$. For the second velocity field, $$u^2 _i$$ be the velocity field generated by a point force $$F _i\delta\left(\mathbf{x}-\mathbf{y}\right)$$ where $$\mathbf{y}$$ lies outside of the particle and the particle is stationary. Then on $$S _p$$, $$u_i^2=0$$, and $$\partial _j\sigma _{ij}^2=-F _i\delta\left(\mathbf{x}-\mathbf{y}\right)$$. Inserting these fields into Eq. \ref{eq: flaxen reciprocal theorem},

\begin{equation}
F^2_i U_i  - F_iu^1 _i\left(\mathbf{y}\right) = 0,
\end{equation}

where $$F^2_i$$ is the force on the particle,

\begin{equation}
F^2_i = \oint _{S_p} dS\ \sigma^2 _{ij} \hat{n} _j.
\end{equation}

We can write $$u^1_i$$ from our singularity solution,

\begin{equation}
u^1 _i = U _j \mathcal{F}\left[ \frac{\mathcal{G} _{ij}\left( \mathbf{x}-\mathbf{\xi} \right) }{8\pi\mu} \right],
\end{equation}
\begin{equation}
\mathcal{F}\left[f\right]=6\pi\mu a\left( 1+\frac{a^2 }{6}\partial^2 \right)f,
\end{equation}

where $$\mathcal{F}$$ is a linear functional and $$\mathbf{\xi}$$ is the centre of the sphere, from which we identify,

\begin{equation}
F^2_i = F_j \mathcal{F} \left[ \frac{\mathcal{G} _{ij}\left(\mathbf{y}-\mathbf{\xi}\right)}{8\pi\mu} \right].
\end{equation}

But the element in the functional is nothing more than the ambient $$u_i^2$$ field evaluated at the sphere centre, so the force on the translating sphere is,
\begin{equation}
F_i = 6\pi\mu a\left( 1+\frac{a^2 }{6}\partial^2 \right)u_i^\infty\left(\mathbf{\xi}\right).
\end{equation}
By a similar argument, one can find the rotlet and stresslet,
\begin{equation}
T_i = 4\pi\mu a^3 \epsilon_{ijk}\partial_ju_k^\infty\| _{\mathbf{\xi}},
\end{equation}

\begin{equation}\label{eq: stresslet flaxen relation}
S_{ij} = \frac{20}{3}\pi\mu a^3\left( 1+\frac{a^2 }{10}\partial^2 \right)\frac{1}{2}\left(\partial_iu_j^\infty+\partial_ju_i^\infty\right)\| _{\mathbf{\xi}}.
\end{equation}

TODO REDO FAXEN SECTION

### Example Motion for Rigid Body Swimming

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
The notes here are based on Kim and Karrila's _Microhydrodynamics_.

