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

I am, unfortunately, no longer much of a theoretical physicist. I took three semesters of Quantum Field Theory (QFT) and decided it was not for me. But there is a beauty in the calculations of QFT, the slow methodical alignment of a maelstrom of algebra and indices. I doubt these notes will serve me much in the future, but I wish to conserve some fraction of what I learned in QFT in a more permanent manner. 

Here, we will compute the first-order renormalization of the theory of Quantum Electrodynamics (QED). That is to say, we will identify the four counterterms necessary to remove divergences from 1-loop level QED diagrams. This will mostly involve resolving some very nasty-looking integrals, but after doing these calculations once, they can be done a thousand times. I will not present every detail, leaving some things untouched. Otherwise, these notes would quickly spiral into an entire semester's worth of content. 

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
where $$\psi$$ is a four-component spinor. We use the $$\not$$ notation to denote a combination with the gamma matrices,
\begin{equation}
\not{p}=\gamma^\mu p_\mu.
\end{equation}

Onward and upward.

## The QED Lagrangian and Feynman Rules. 
The Lagrangian for QED describing the interactions between a spin-1/2 spinor field $$\psi\left(\mathbf{X}\right)$$ and a gauge field $$A_\mu\left(\mathbf{x}\right)$$ is,
\begin{equation}\label{eq: QED Lagrangian}
\mathcal{L} _\text{QED}=\bar{\psi}\left(i\not D-m\right)\psi-\frac{1}{4}F^{\mu\nu}F _{\mu\nu}-\frac{1}{2\xi}\left(\partial _\mu A^\mu\right)^2,
\end{equation}
where $$D _\mu$$ is the covarient derivative, 
\begin{equation}
D _\mu = \partial _\mu+i e A _\mu,
\end{equation}
$$e$$ is known as the coupling constant. $$F^{\mu\nu}$$ is the field strength tensor defined as,
\begin{equation}
F^{\mu\nu}=\partial^\mu A^\nu - \partial^\nu A^\mu.
\end{equation}
Finally, the last term in Eq. \ref{eq: QED Lagrangian} is a gauge-coupling term that arises from gauge symmetry and the Fadeev-Popov procedure. The constant $$\xi$$ is a gauge constant, whose value does not influence the physics. 

The equations of motion, obtained from the Euler-Lagrange equations, are for the spinor field,
\begin{equation}
\left(i\not \partial-m\right)\psi=e\not A\psi,
\end{equation}
and for the gauge field,
\begin{equation}
\partial_\nu F^{\nu\mu}+\frac{1}{\xi}\partial^\mu\left(\partial_\nu A^\nu\right) =e\bar{\psi}\gamma^\mu\psi.
\end{equation}


The QED action comes from integrating the Lagrangian; after application of the product rule, we find,
\begin{equation}
S_\text{QED}=\int dx^4\ \mathcal{L} _\text{QED}=\int dx^4\ \bar{\psi} \left(i\not\partial- m\right)\psi +\frac{1}{2} A^\mu\left( \eta _{\mu\nu}\partial^2  - \left( 1 - \frac{1}{\epsilon}\right) \partial _\mu \partial _\nu  \right)A^\nu - e \bar{\psi}\not A \psi.
\end{equation}
From this action, it is fairly straightforward to obtain the Feynman rules for the fermionic and photonic propagators in momentum space, a procedure that I will not discuss here. For external propagators, the procedure involves solving the free-space equations of motion. Each external line has two polarizations noted by the indices $$r$$ and $$s$$.

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/QED_diagrams/QED_feynman_rules.png" title="QED_feynman_rules" class="img-fluid rounded z-depth-0" width="auto" height="270" %}
</div>

It can be shown that the external propagators satisfy the relations,
\begin{equation}
\not p u = m u,\quad \not p v= -m v,
\end{equation}
\begin{equation}
\epsilon^\mu p_\mu = 0,
\end{equation}
\begin{equation}
\sum_{s} u \bar{u}=\not{p}+m,\quad\sum_{r} v \bar{v}=\not{p}-m,
\end{equation}
\begin{equation}
\sum_{s} \epsilon^\mu \left(\epsilon^*\right)^\nu = -\eta^{\mu\nu} + \left(1-\xi\right)\frac{p^\mup^nu}{p^2}.
\end{equation}

These relations will come in handy when resolving our diagrams. 

## The Photonic Propagator at One Loop
In this section, we are interested in the two-point photonic propagator $$D_{\mu\nu}$$, which in general, will have a diagram resembling: 

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/QED_diagrams/D_munu_photon_propagator.png" title="D_munu_photon_propagator" class="img-fluid rounded z-depth-0" width="auto" height="270" %}
</div>

The "stuff" in the diagram represents some general interaction contained within the two external legs. This general interaction can be decomposed as a sum of the tree-level diagram and 1-particle irreducible (1PI) diagrams, where the (1PI) diagrams are those that cannot be split in two by cutting a single line. To first loop order, the contribution to $$D_{\mu\nu}$$ consists of the tree-level diagram and a single 1PI ferminoic loop. 

Via the Ward-Takahashi identity, which is essentially Noether's Theorem applied to path integrals, it can be shown that the two-point photonic propagator satisfies,
\begin{equation}
\frac{i}{\xi}q^2q^\mu D_{\mu\nu}=q_\nu.
\end{equation}
For convenience, denote the tensor and the projector,
\begin{equation}
t_{\mu\nu}=\eta_{\mu\nu}-\left(1-\xi\right)\frac{q_\mu q_\nu}{q^2},\quad t _{T\ \mu\nu}=\eta_{\mu\nu}-\frac{q_\mu q_\nu}{q^2},
\end{equation}
noting that,
\begin{equation}
t^\alpha{T\ \mu}t_{\alpha\nu}=t_{T\ \mu\nu},\quad t _{\mu\nu}q^\mu = \xi q _\nu,\quad t _{T\ \mu\nu}q^\mu=0.
\end{equation}
At tree-level, the propagator takes the form,
\begin{equation}
 D^\text{tree} _{\mu\nu}= -\frac{i}{q^2}t _{\mu\nu},
\end{equation}
from which we identify,
\begin{equation}
\frac{i}{\xi}q^2q^\mu D^\text{tree} _{\mu\nu}=q _\nu.
\end{equation}
Therefore, corrections beyond first-order should be proportional to $$t _{T\ \mu\nu}$$ which is orthogonal to $$q^\nu$$. And with this in mind, we write the 1PI diagram for an internal fermion loop as $$i q^2 \Pi\left(q\right) t _{T\ \mu\nu}$$, where $$\Pi\left(q\right)$$ is a function of the momentum to be determined.





### Sources
