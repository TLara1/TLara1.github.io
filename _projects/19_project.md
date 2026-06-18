---
layout: page
title: On The Navier-Stokes Equations - 6/26
description:
img: 
importance: 1
category: Maths
related_publications: false
toc:
  beginning: true
---

## Introduction
These days, I am, ostensibly, someone who does fluids. I suppose there is not much non-$$\hbar$$ physics that is not somehow related to fluids. I am by no means complaining, fluids are great, but the little physicist in me has always been bothered by the rather offhanded way many texts "derive" the Navier-Stokes Equations, which are so important to the study of fluid mechanics. Here, I seek to introduce a more foundational approach, as motivated by first principles as possible, to arrive at the constitutive equations for continuum fluid.

Because I am a physicist at heart, I use index notation throughout, summing over repeated indices.

## The Continuum Approximation
The desired description of fluid motion is much larger than any molecular length scale of the fluid; we desire a description at a <em>macroscopic</em> level. By adopting the so-called <em>continuum hypothesis</em>, we assume that we can describe fluid motion on a much coarser scale than on the molecular scale that is still physically equivalent in the sense that we could obtain the former by some sophisticated averaging process of the latter. It is important to note that we never actually compute macroscopic averages of molecular variables, but this serves only to remind us that any variations in our macroscopic variables must occur on scales much larger than the scales associated with the molecular microstructures of the fluid. It must be possible to choose an averaging volume that is arbitrarily small relative to the macroscale while remaining much larger than the microscale. 

With this idea in mind, we go on to derive the governing physics using the classical conservation of mass and energy plus Newton's second and third laws of mechanics.

## Conservation of Mass
Consider an arbitrarily chosen volume element of a fixed position and shape. Essentially, a "chunk" of space filled with fluid. At each point on the surface of this volume, there is a mass flux of fluid, $$\rho u^i\hat{n}_i$$, where $$u^i$$ is the local fluid velocity. Chosing $$\hat{n}_i$$ as the unit normal to the surface pointing outwards, this flux is negative when fluid enters the volume and positive when it exits. Conservation of mass requires that the total mass in the volume is equal to the imbalance of mass flux in and out of the surface,
\begin{equation}
\int_V dV\ \partial_t\rho=-\int _{\partial V} dA\ \rho u^i\hat{n}_i,
\end{equation}
where $$V$$ denotes the volume element and $$\partial V$$ denotes its surface. We may apply the divergence theorem and note that the integrand must be zero to be satisfied for an arbitrarily chosen volume element. This results in,
\begin{equation}\label{eq: continuity equation}
\partial_t\rho+\partial_i\left(\rho u^i\right)=0.
\end{equation}
Eq. \ref{eq: continuity equation} is the **continuity equation**, which we recognize as a consequence of the conservation of mass. 

It is also convenient to define the convective time derivative of a scalar quantity, $$D_t B$$. $$B$$ may change with respect to time at a fixed point at a rate $$\partial_t B$$ and because the physical material point moves through space along with the fluid. It follows that the convected time derivative of a scalar $$B$$ is expressible in terms of both the partial derivatives of $$B$$ with respect to space and time,
\begin{equation}
D_t B=\partial_t B + \partial_t x^i \partial_i B = \partial_t B + u^i \partial_i B.
\end{equation}

We may use this convective derivative to perform an alternative derivation of Eq. \ref{eq: continuity equation}. Consider instead of a volume element with <em>fixed</em> position, a volume element that moves with the fluid, denoted by $$V_m(t)$$. This is a material volume. The set of material points contained within this volume does not change over time since the volume moves along with these points. Therefore, the local flux of mass through all points on the surface of the material volume must be zero at all times. This results in the statement,
\begin{equation}\label{eq: continuity equation integral convective form}
D_t\left[ \int_{V_m(t)} dV\ \rho\right]=0,
\end{equation}
as a consequence of the conservation of mass. Now we derive the **Reynolds Transport Theorem** for a scalar quantity $$B\left(\mathbf{x}(t),t\right)$$ associated with a moving fluid. Every point $$\mathbf{x}(t)$$ within the material control volume has a position independent of the spatial coordinate $$x^i$$, so the convective derivative should be considered as acting only over time,
\begin{equation}
D_t\left[ \int_{V_m(t)} dV\ B\left(\mathbf{x}(t),t\right) \right]
\end{equation}
\begin{equation}
D_t\left[ \int_{V_m(t)} dV\ B\left(\mathbf{x}(t),t\right) \right]=\lim_{\delta t\rightarrow 0} \left(\frac{1}{\delta t}\left[ \int_{V_m(t+\delta t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t\right)\right]\right).
\end{equation}




Adding and subtracting $$\int_{V_m(t)} dV\ B\left(t+\delta t\right)$$, 
\begin{equation}
D_t\left[ \int_{V_m(t)} dV\ B\right]=\lim_{\delta t\rightarrow 0} \left(\frac{1}{\delta t}\left[ \int_{V_m(t+\delta t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t+\delta t\right)\right]+\frac{1}{\delta t}\left[\int_{V_m(t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t\right)\right]\right).
\end{equation}
The second term is nothing more than,
\begin{equation}
\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[\int_{V_m(t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t\right)\right]\right)=\int_{V_m(t)} dV\ \partial_t B\right).
\end{equation}
We now rewrite the first term as,
\begin{equation}
\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[\int_{V_m(t+\delta t)-V_m(t)} dV\ B\left(t+\delta t\right)\right]\right).
\end{equation}
To evaluate, observe that any surface element $$dA(t)$$ of $$V _m(t)$$ will move a distance $$u^i\hat{n}_i\delta t$$ over the time interval $$\delta t$$. So for small time, $$dV\rightarrow dA u^i\hat{n} _i\delta t$$, and our volume intergral over $$V _m(t+\delta t)-V _m(t)$$ can be converted into an integral over the surface of $$V _m(t)$$.,
\begin{equation}
\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[\int_{V_m(t+\delta t)-V_m(t)} dV\ B\left(t+\delta t\right)\right]\right)=\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[\int_{A_m(t)} dA\ B\left(t+\delta t\right)u^i\hat{n} _i\delta t\right]\right)=\int_{A_m(t)} dA\ B u^i\hat{n}_i.
\end{equation}
And via the divergence theorem, applied to the surface integral, we obtain the transport theorem,
\begin{equation}\label{eq: Reynolds transport theorem}
D_t\left[\int_{V_m(t)} dV\ B\left(\mathbf{x}(t),t\right)\right]=\int_{V_m(t)}dV\ \left[\partial_t B + \partial_i\left(B u^i\right)\right].
\end{equation}
We can immediately see that Eq. \ref{eq: continuity equation integral convective form} combined with Eq. \ref{eq: Reynolds transport theorem} yields the continuity equation Eq. \ref{eq: continuity equation} once again.

## The Momentum Equation
In this section, we consider Newton's second law of motion applied to the same material control volume. This law states that the temporal rate of change of linear momentum of a given body is equal to the sum of forces acting on that body. Applying this law directly to the material control fluid volume $$V_m(t)$$ with our convective derivative, we obtain,
\begin{equation}
D_t\left[\int_{V_m(t)} dV\ \rho u^i \right] =\left(\text{sum of forces acting on }V_m(t)\right)^i.
\end{equation}
We should distinguish between the two types of forces acting on the control volume. First, there are <em>body forces</em> that act everywhere in the fluid. Two such forces could be gravity or the force from an electromagnetic field. A second type of force is <em>surface forces</em> that act on the surface of the material control volume. With these forces in mind, we write the more mathematical statement,
\begin{equation}
D_t\left[\int_{V_m(t)} dV\ \rho u^i \right] =\int_{V_m(t)} dV\ f^i + \int_{A_m(t)} dA\ t^i,
\end{equation}
using Eq. \ref{eq: Reynolds transport theorem},
\begin{equation}\label{eq: continuity equation integral form}
\int_{V_m(t)} dV\ \left[\partial_t\left(\rho u^i\right)+\partial_j\left(\rho u^ju^i\right)-f^i\right]  =\int_{A_m(t)} dA\ t^i.
\end{equation}

We now discuss the traction vector $$t^i$$ in more depth. Because the left-hand side of Eq. \ref{eq: continuity equation integral form} is a volume integral, we expect the result to go with the cube of the characteristic volume length $$\ell^3$$, compared to the right-hand side, a surface integral going with the square of the characteristic length $$\ell^2$$. So as we shrink the size of the arbitrary volume to $$0$$ and reduce the characteristic length $$\ell\rightarrow0$$, we see that the traction vector $$t^i$$ must vanish. Physically, this requires that surface forces must be in local equilibrium for an arbitrarily small volume.





### Sources

