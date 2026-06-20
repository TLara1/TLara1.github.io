---
layout: page
title: On the Langevin and Fokker-Planck Equations - 6/26
description:
img: 
importance: 6
category: Physics
related_publications: false
toc:
  beginning: true
---

## Introduction
Statistical Mechanics is cool. It's also shockingly useful. It's one of those areas of physics that ends up being helpful for a bunch of other areas and for lots of flavours of applied maths. 

Here we discuss the Langevin and then the Fokker-Planck Equations, obtaining the fun result that a system immersed in a fluid that is at equilibrium also tends towards equilibrium. 

## Colloid-Fluid Interaction Hamiltonian
Consider a colloid of mass $$M$$ with position $$x$$ and momentum $$P$$ immersed in a fluid composed of particles with positions $$q$$ and momentema $$p$$. For simplicity, we will treat this problem in one dimension, but our results easily generalise to higher dimensions. In this context, a colloid is essentially just a large partcile relative to the particles composing the fluid, where "large" means a lengthscale of at least three orders of magnitude larger than the fluid particles.

Our Hamiltonian has four sectors. First, the standerd description of the colloid motion, an interaction term between the colloid and the fluid, a fluid particle interaction term, and an interaction term between fluid particles,
\begin{equation}
H=\frac{P^2}{2M}+V_{ext}(x)+\sum_iV_{FC}\left(x-q_i\right)+\sum_i\left[\frac{p_i^2}{2m}+V_{ext}\left(q_i\right)\right]+\sum_{i\neqj}V_{FF}\left(q_i-q_j\right).
\end{equation}

This is an extremely general Hamiltonian that is rather unapproachable. We simplify by first assuming that the fluid is equilibrated such that we may ignore the impact of the external potential on the fluid particles and remove the fluid-fluid interaction terms for the same reason. Here we have assumed a seperation of scales, in that the time it takes the fluid to equilibriate is much smaller than the time describing any of the dynamics of the colloid. 

That leaves the colloid-fluid interactions. In practice, this interaction is rather complicated, but we will assume it can be approximated as a harmonic oscillator. Effectively, we can imagine all the fluid particles attached to the colloid with little springs, interacting with the colloid and oscillating over time. Setting $$m=1$$ for convenience and assuming $$M\gg1$$,



### Sources
This derivation largely follows from the lecture notes of my Stastical Dynamics II, 8.08, class taught by Professor Julien Tailleur during the 2026 IAP period.
