---
layout: page
title: On the Navier-Stokes Equations - 6/26
description:
img: 
importance: 90
category: Maths
related_publications: false
toc:
  beginning: true
---

## Introduction
These days, I am, ostensibly, someone who does fluids. I suppose there is not much non-$$\hbar$$ physics that is not somehow related to fluids. I am by no means complaining, fluids are great, but the little physicist in me has always been bothered by the rather offhanded way many texts "derive" the Navier-Stokes Equations, which are so important to the study of fluid mechanics. Here, I seek to introduce a more foundational approach, as motivated by first principles as possible, to arrive at the constitutive equations for continuum fluid.

Because I am a physicist at heart, I use index notation throughout, summing over repeated indices.

## The Continuum Approximation
The desired description of fluid motion is much larger than any molecular length scale of the fluid; we desire a description at a <em>macroscopic</em> level. By adopting the so-called <em>continuum hypothesis</em>, we assume that we can describe fluid motion on a much coarser scale than on the molecular scale that is still physically equivalent in the sense that we could obtain the former by some sophisticated averaging process of the latter. It is important to note that we never actually compute macroscopic averages of molecular variables, but this serves only to remind us that any variations in our macroscopic variables must occur on scales much larger than those associated with the fluid's molecular microstructures. It must be possible to choose an averaging volume that is arbitrarily small relative to the macroscale while remaining much larger than the microscale. 

With this idea in mind, we go on to derive the governing physics using the classical conservation of mass and energy plus Newton's second and third laws of mechanics.

## Conservation of Mass
Consider an arbitrarily chosen volume element of a fixed position and shape. Essentially, a "chunk" of space filled with fluid. At each point on the surface of this volume, there is a mass flux of fluid, $$\rho u^i\hat{n}_i$$, where $$u^i$$ is the local fluid velocity. Choosing $$\hat{n}_i$$ as the unit normal to the surface pointing outwards, this flux is negative when fluid enters the volume and positive when it exits. Conservation of mass requires that the total mass in the volume is equal to the imbalance of mass flux in and out of the surface,
\begin{equation}
\int_V dV\ \partial_t\rho=-\int _{A} dA\ \rho u^i\hat{n}_i,
\end{equation}
where $$V$$ denotes the volume element and $$A$$ denotes its surface. We may apply the divergence theorem and note that the integrand must be zero to be satisfied for an arbitrarily chosen volume element. This results in,
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
D_t\left[ \int_{V_m(t)} dV\ B\left(\mathbf{x}(t),t\right) \right]=\lim_{\delta t\rightarrow 0} \left(\frac{1}{\delta t}\left[ \int_{V_m(t+\delta t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t\right)\right]\right).
\end{equation}

Adding and subtracting $$\int_{V_m(t)} dV\ B\left(t+\delta t\right)$$, 
\begin{equation}
D_t\left[ \int_{V_m(t)} dV\ B\right]=\lim_{\delta t\rightarrow 0} \left(\frac{1}{\delta t}\left[ \int_{V_m(t+\delta t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t+\delta t\right)\right]\right)
\end{equation}
\begin{equation}
+\lim_{\delta t\rightarrow 0} \left(\frac{1}{\delta t}\left[\int_{V_m(t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t\right)\right]\right). \nonumber
\end{equation}

The second term is nothing more than,
\begin{equation}
\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[\int_{V_m(t)} dV\ B\left(t+\delta t\right)-\int_{V_m(t)} dV\ B\left(t\right)\right]\right)=\int_{V_m(t)} dV\ \partial_t B,
\end{equation}

and we rewrite the first term as,
\begin{equation}
\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[\int_{V_m(t+\delta t)-V_m(t)} dV\ B\left(t+\delta t\right)\right]\right).
\end{equation}
To evaluate, observe that any surface element $$dA(t)$$ of $$V _m(t)$$ will move a distance $$u^i\hat{n}_i\delta t$$ over the time interval $$\delta t$$. So for small time, $$dV\rightarrow dA u^i\hat{n} _i\delta t$$, and our volume intergral over $$V _m(t+\delta t)-V _m(t)$$ can be converted into an integral over the surface of $$V _m(t)$$,

\begin{equation}
\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[ \int_{V_m(t+\delta t)-V_m(t)} dV\ B\left(t+\delta t\right) \right]\right)=\lim_{\delta t\rightarrow 0}\left(\frac{1}{\delta t}\left[ \int_{A_m(t)} dA\ B\left(t+\delta t\right)u^i\hat{n}_i\delta t  \right]\right)
\end{equation}

\begin{equation}
=\int _{A _m(t)} dA\ B u^i\hat{n} _i.\nonumber
\end{equation}


And via the divergence theorem, applied to the surface integral, we obtain the transport theorem,

\begin{equation}\label{eq: Reynolds transport theorem}
D_t\left[\int_{V_m(t)} dV\ B\left(\mathbf{x}(t),t\right)\right]=\int_{V_m(t)}dV\ \left[\partial_t B + \partial_i\left(B u^i\right)\right].
\end{equation}

We can immediately see that Eq. \ref{eq: continuity equation integral convective form} combined with Eq. \ref{eq: Reynolds transport theorem} yields the continuity equation Eq. \ref{eq: continuity equation} once again. It is also convenient to write Eq. \ref{eq: continuity equation} in terms of the convective derivative,
\begin{equation}\label{eq: continuity equation convective derivative form}
D_t \rho + \rho\partial_iu^i=0.
\end{equation}
From this, we see that if we approximate the material derivative of the density to be zero, $$D_t\rho=0$$, the continuity equation reduces to the incompressibility assumption, $$\partial_iu^i=0$$ for fluids.


## The Momentum Equation

### Linear Momentum
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

So it is clear that the traction vector should depend not only on position and time, but also on the local orientation of the surface to satisfy local force equilibrium. Consider a tetrahedron with three faces perpendicular to each of the coordinate directions $$\hat{\mathbf{e}}_(i)$$ and a fourth face perpendicular to the normal direction $$\hat{\mathbf{n}}$$. Denote the component of a stress vector on a surface with normal $$\hat{\mathbf{n}}$$ as $$t^i\left(\hat{\mathbf{n}}\right)$$. As a consequence of surface-stress equilibrium, as we shrink the volume of our tetrahedron, the traction integrated over the surface normal to $$\hat{\mathbf{n}}$$ should be balanced by the sum of the tractions integrated over the other three faces, 

\begin{equation}\label{eq: mean traction balance}
\left<t^i\left(\hat{\mathbf{n}}\right)\right>\Delta A_n = \left<t^i\left(\hat{\mathbf{e}} _{(1)}\right)\right>\Delta A _1 + \left<t^i\left(\hat{\mathbf{e}} _{(2)}\right)\right>\Delta A _2 + \left<t^i\left(\hat{\mathbf{e}} _{(3)}\right)\right>\Delta A _3.
\end{equation}

$$\left<\ \right>$$ represent mean values over a surface and $$\Delta A_i$$ is the projected area of the normal face area $$\Delta A_n$$ onto the plane perpendicular to the $$\hat{\mathbf{e}}_(i)$$ axis. Thus,

\begin{equation}\label{eq: tetrahedron surface area normal}
\Delta A_i = \left(\hat{n}_j\hat{\mathbf{e}} _{(i)}^j\right)\Delta A_n,
\end{equation}

where $$\hat{\mathbf{e}}_{(i)}^j$$ should be understood as the $$j$$-th component of the $$i$$-th coordinate basis vector. Combining Eq. \ref{eq: mean traction balance} with Eq. \ref{eq: tetrahedron surface area normal} and collapsing the area of the tetrahedron to zero,
\begin{equation}
t^i\left(\hat{\mathbf{n}}\right)=\hat{n} _j\left[\hat{\mathbf{e}} _{(1)}^jt^i\left(\hat{\mathbf{e}} _{(1)}\right)+\hat{\mathbf{e}} _{(2)}^jt^i\left(\hat{\mathbf{e}} _{(2)}\right)+\hat{\mathbf{e}} _{(3)}^jt^i\left(\hat{\mathbf{e}} _{(3)}\right)\right].
\end{equation}

With this form in mind, we define the stress tensor, $$\sigma^{ij}=\hat{\mathbf{e}} _{(1)}^jt^i\left(\hat{\mathbf{e}} _{(1)}\right)+\hat{\mathbf{e}} _{(2)}^jt^i\left(\hat{\mathbf{e}} _{(2)}\right)+\hat{\mathbf{e}} _{(3)}^jt^i\left(\hat{\mathbf{e}} _{(3)}\right)$$, such that the traction vector in along a surface normal to the direction $$\hat{\mathbf{n}}$$ is given by,
\begin{equation}
t^i\left(\hat{\mathbf{n}}\right)=\hat{n} _j\sigma^{ij}.
\end{equation}

Again with the divergence theorem, applying what we have learned to Eq. \ref{eq: continuity equation integral form}
\begin{equation}
\int_{V_m(t)} dV\ \left[\partial_t\left(\rho u^i\right)+\partial_j\left(\rho u^ju^i\right)-f^i-\partial_j\sigma^{ij}\right]  = 0.
\end{equation}
Applying the continuity equation, Eq. \ref{eq: continuity equation}, and realizing that the integrand must be zero for an arbitrary volume, 
\begin{equation}\label{eq: Cauchy momentum equation}
\rho\left(\partial_tu^i+u^j\partial_ju^i\right)=f^i+\partial_j\sigma^{ij}.
\end{equation}
Eq. \ref{eq: Cauchy momentum equation} is known as **Cauchy's Momentum Equation**, which is nothing more than Newton's second law applied to a moving fluid.

We have made progress, but still have a good ways to go. The introduction of $$\sigma^{ij}$$ actually complicates the problem further by adding $$9$$ more unknown components of the tensor, while Eq. \ref{eq: Cauchy momentum equation} only gives three more equations.

### Angular Momentum
To constrain the stress tensor, we consider the generalization of Newton's second law to angular momentum. The range of change of the angular momentum inside the control volume must be equal to the sum of torques acting on said volume,
\begin{equation}
D_t\left[\int_{V_m(t)} dV\ \rho\epsilon^i_{jk}x^j u^k \right] =\left(\text{sum of torques acting on }V_m(t)\right)^i,
\end{equation}
where $$\epsilon^i_{jk}$$ is the Levi-Cevita symbol. The sources of torque arise from external body forces and from the surface traction,
\begin{equation}\label{eq: angular momentum conservation integral form}
D_t\left[\int_{V_m(t)} dV\ \rho\epsilon^i_{jk}x^j u^k \right] =\int_{V_m(t)} dV\ \epsilon^i_{jk}x^jf^k + \int_{A_m(t)} dA\ \epsilon^i_{jk}x^j \hat{n} _l \sigma^{kl}.
\end{equation}

We have used $$t^k=\hat{n} _l \sigma^{kl}$$. Applying the divergence theorem,

\begin{equation}
\int_{A_m(t)} dA\ \epsilon^i _{jk}x^j\hat{n} _l \sigma^{kl} = \int _{V _m(t)} dV\ \left[ \epsilon^i _{lk} \sigma^{kl} + \epsilon^i _{jk} x^j\partial _l\sigma^{kl} \right].
\end{equation}

Inserting this result into Eq. \ref{eq: angular momentum conservation integral form}, and using Eq. {eq: Cauchy momentum equation}, we find

\begin{equation}
\int_{V_m(t)} dV\ \epsilon^i_{lk}\sigma^{kl} = 0.
\end{equation}
From this, we conclude that the stress tensor $$\sigma^{ij}$$ must be symmetric, $$\sigma^{ij}=\sigma^{ji}$$  to balance angular momentum. This reduces the number of unknowns in the stress tensor from nine to six, progress, but we have more to do.

## Conservation of Energy
We again begin by considering a material volume moving with the fluid, considering the change in its energy over time. There are two components to the total energy, the <em>kinetic energy</em> associated with the macroscopic velocity $$\mathbf{u}$$ and the <em>internal energy</em> associated with the intensity of random molecular motion relative to the mean velocity. From this Perspective, the total energy of an arbitrary control volume is,
\begin{equation}
\mathcal{E}=\int_{V_m(t)} dV\ \left[\frac{1}{2}\rho u^iu_i + \rho e\right],
\end{equation}
where $$e$$ is the internal energy per unit mass.

The rate of change of the total energy with time is determined by the principle of energy conservation,

\begin{equation}\label{eq: energy conservation schematic form}
D_t\mathcal{E}=D_t\left[\int_{V_m(t)} dV\ \left[\frac{1}{2}\rho u^iu_i + \rho e\right]\right] =\left(\text{rate of work done on }V_m(t)\right)
\end{equation}
\begin{equation}
-\left(\text{rate of internal energy flux across }A_m(t)\right).\nonumber
\end{equation}

We already investigated the forces acting on $$V_m(t)$$; the first term on the right-hand side has a body force and a tangential component,
\begin{equation}
\left(\text{rate of work done on }V_m(t)\right) = \int_{V_m(t)} dV\ u_if^i + \int _{A _m(t)} dA\ u _i\hat{n} _j\sigma^{ij}.
\end{equation}

For the second term, we define a <em>surface flux vector</em> $$\mathbf{q}$$ which describes the net flux of internal energy across the surface transferred by random particle motion. We adopt the convention that a flux of heat into the material control is positive. Rewriting Eq. {eq: energy conservation schematic form} mathematically,
\begin{equation}
D_t\left[\int_{V_m(t)} dV\ \left[\frac{1}{2}\rho u^iu_i + \rho e\right]\right] = \int_{V_m(t)} dV\ u_if^i + \int _{A_m(t)} dA\ u_i\hat{n} _j\sigma^{ij} - \int _{A_m(t)} dA\ \hat{n} _iq^i.
\end{equation}
Proceeding as usual, employing the divergence theorem, the Reynolds transport theorem, mass conservation, and setting the integrand to $$0$$, we find,
\begin{equation}\label{eq: total energy balance}
\rho D_t\left[\frac{1}{2} u^iu_i +  e\right]=\partial_i\left(u_j\sigma^{ij}\right)+u_if^i-\partial_iq^i.
\end{equation}
Luckily, we already have a relationship for the mechanical energy balance through Eq. \ref{eq: Cauchy momentum equation},
\begin{equation}
\frac{1}{2}\rho D_t\left[u^iu_i\right]=u_if^i+u_i\partial_j\sigma^{ij}.
\end{equation}
Inserting this relationship into Eq. \ref{eq: total energy balance}, and recalling the symmetry of the stress tensor, we obtain an equation for the thermal energy balance,

\begin{equation}\label{eq: thermal energy balance}
\rho D_t e = \sigma^{ij}E_{ij}-\partial_iq^i,
\end{equation}
We have defined the rate-of-strain tensor, $$E_{ij}=\frac{1}{2}\left(\partial_iu_j+\partial_ju_i\right)$$.

It is easiest to express the thermal energy balance in terms of the specific enthalpy $$h$$, defined as,
\begin{equation}\label{eq: enthalpy definition}
h=e+p/\rho,
\end{equation}
where $$p$$ is the fluid pressure. It follows that, with the continuity equation,
\begin{equation}
\rho D_t e = \rho D_t h - D_t p + \frac{p}{\rho} D_t\rho =  \rho D_t h - D_t p - p\partial_i u^i.
\end{equation}
Expressing thermal energy balance in terms of $$h$$,
\begin{equation}\label{eq: enthalpy balance equation}
\rho D_t h = D_t p + p\partial_i u^i + \sigma^{ij}E_{ij}-\partial_iq^i.
\end{equation}

### A Brief Interlude to Thermodynamics
Enthalpy is helpful, but we can use equilibrium thermodynamic relationships to relate this quantity to the more relevant variables of temperature $$\theta$$ and pressure $$p$$. From the definition of enthalpy, Eq. \ref{eq: enthalpy definition},
\begin{equation}
dh = de + pdv + vdp,
\end{equation}
where $$v=1/\rho$$ is the specific volume. Via the first law of thermodynamics, 
\begin{equation}\label{eq: first law of thermodynamics}
de=\theta ds - p dV,
\end{equation}
where $$ds$$ is the change in specific entropy of the system,
\begin{equation}\label{eq: enthalpy differential element}
dh = \theta ds + vdp.
\end{equation}

Now, consider the Gibbs free energy per unit mass, defined as,
\begin{equation}
g=h-\theta s.
\end{equation}
From Eq. \ref{eq: enthalpy differential element},
\begin{equation}
dg= vdp-sd\theta.
\end{equation}
So the change in $$g$$ with respect to $$\theta$$ at a constant pressure is nothing more than the negative entropy,
\begin{equation}
\frac{dg}{d\theta}|_p = -s,
\end{equation}
and similarly, the change in $$g$$ with respect to $$p$$ at a constant temperature is nothing more than the specific volume,
\begin{equation}
\frac{dg}{dp} | _\theta = v.
\end{equation}
From these two results, we obtain the Maxwell relation,
\begin{equation}
-\frac{ds}{dp}| _\theta = \frac{dv}{d\theta} |_p.
\end{equation}
Great, we are almost there. Taking the differential element of the entropy,
\begin{equation}
ds = \frac{ds}{d\theta}| _pd\theta + \frac{ds}{dp} | _\theta dp,
\end{equation}
We use our Maxwell relation and the definition of the <em>Specific Heat Capacity at Constant Pressure</em>, $$C_p$$,
\begin{equation}
C_p = \frac{de}{d\theta}| _p=\theta\frac{ds}{d\theta}|_p,
\end{equation}
to find,
\begin{equation}\label{eq: entropy differential element final}
ds = \frac{C_p}{\theta}d\theta -\frac{dv}{d\theta}|_p dp.
\end{equation}

Finally, we combine Eq. \ref{eq: enthalpy differential element} with Eq. \ref{eq: entropy differential element final} to write the change in enthalpy in terms of the pressure, density, and temperature,
\begin{equation}
dh = c_p d\theta + \left(v - \theta \frac{dv}{d\theta}|_p \right)dp = c_p d\theta + \left(\frac{1}{\rho} + \frac{\theta}{\rho^2} \frac{d\rho}{d\theta}|_p \right)dp.
\end{equation}

This result allows us to express Eq. \ref{eq: enthalpy balance equation} in terms of $$\theta$$ rather $$h$$,
\begin{equation}\label{eq: thermal energy balance equation}
\rho c_p D_t\theta =  p\partial_i u^i + \sigma^{ij}E_{ij}-\partial_iq^i - \frac{\theta}{\rho} \frac{d\rho}{d\theta}\|_p D_t p.
\end{equation}

The good news is that we now have a relationship between the temperature and our other variables of interest. The bad news is that we are no closer to solving our problem since we have introduced four new variables, $$\theta$$ and the $$3$$ components of $$\mathbf{q}$$ and only one equation. Perhaps the second law of thermodynamics will prove useful.

### The Second Law of Thermodynamics
The second law states that the entropy change of a system multiplied by the temperature is greater than or equal to the total heat change caused by heat exchange with the system's surroundings. In differential form, this is stated as,
\begin{equation}
dS\geq \frac{dQ}{\theta}.
\end{equation}
When we apply the second law to our material volume, we find,
\begin{equation}
D_t\left[\int_{v_m(t)}dV\ \rho s\right]+\int_{A_m(t)}dA\ \frac{\hat{n}_iq^i}{\theta}\geq 0.
\end{equation}
Proceeding as usual with the Reynolds transport theorem, continuity equation, and applying our result to an arbitrary control volume,

\begin{equation}
\rho D_t s + \partial_i\left(\frac{q^i}{\theta}\right)\geq 0.
\end{equation}
Now we employ the thermodynamic relationship, Eq. \ref{eq: first law of thermodynamics}, to remove the entropy,
\begin{equation}
\rho \theta D_t s = \rho D_t e -\frac{p}{\rho}D_t \rho.
\end{equation}
Substituting $$D_t e$$ using our expression for the thermal energy balance from Eq. \ref{eq: thermal energy balance} and using the continuity equation, Eq. \ref{eq: continuity equation convective derivative form}, we obtain the inequality,
\begin{equation}\label{eq: entropy constitutive inequality}
\sigma^{ij}E_{ij}+p\partial_iu^i - \frac{1}{\theta}q^i\partial_i\theta\geq 0.
\end{equation}
Although this result is not instantly helpful, we will see that it aids in obtaining constitutive relationships for the stress tensor and heat flux vector.

## Constitutive Relationships
Let's pause and take stock of our progress. So far, we have obtained five differential equations from basic principles of mass, momentum, and energy conservation:
<ol>    
<li> The continuity equation, Eq. \ref{eq: continuity equation}</li>
<li> Cauchy's equation, Eq. \ref{eq: Cauchy momentum equation}</li>
<li> Thermal energy balance equation, Eq. \ref{eq: thermal energy balance equation}</li>
</ol>
We also have a restriction on the symmetry of the stress tensor based on the conservation of angular momentum and an inequality based on the second law of thermodynamics. Unfortunately, our system is still severely undertermined, we have $$14$$ unkowns, $$\rho + u^i + \sigma^{ij} + p + q^i$$, for our five equations. We must find additional relationships in order to determine solutions for our independent variables.

### Fourier's Law
Let's begin by remembering that $$\mathbf{q}$$ represents the flux of molecular energy due to the random motion of particles, this called convective heat transport. It is clear that this flux should depend on the temperature gradient in the fluid. When there is no temperature gradient, there should be zero flux of heat. Furthermore, this fluid is assumed to be homogeneous in that the relationship between the heat flux and temperature gradient is the same throughout the fluid.

We also assume that the heat flux depends only on the temperature gradient magnitude, not its orientation. This is a statement of <em>istoropy</em>, reflecting the symmetry of the particles constituting the fluid. Generally, this is not the case for a general material, but we assume this to be the case for most common fluids viewed from the spatially averaged continuum viewpoint.

From here, we guess the simplest possible linear relationship,
\begin{equation}
q^i=-k\partial^i\theta.
\end{equation}
This is known as **Fourier's Law of Heat Conduction**, where $$k$$ is a constant of thermal conductivity. Although this conduction law is known to be experimentally accurate for many real substances, it is important to keep in mind that this is little more than an educated guess.

Applying this to our entropy inequality, Eq. \ref{eq: entropy constitutive inequality}, for a static fluid, $$u^i=0$$,
\begin{equation}\label{eq: fourier law constitutive}
k\partial_i\theta\partial^i\theta\geq 0,
\end{equation}
from which we conclude the thermal conductivity must be nonnegative, $$k\geq0$$.

### The Newtonian Fluid
Now for the stress tensor, $$\sigma^{ij}$$. First, consider the momentum equation, Eq. \ref{eq: Cauchy momentum equation}, in the absence of fluid motion with an external forcing,
\begin{equation}
\delta_j\sigma^{ij}+f^i=0.
\end{equation}
In this case, the only surface force must be through the pressure $$p$$, acting normal to a surface with a magnitude independent of its orientation. The surface force vector takes the form,
\begin{equation}
t^i=-p\hat{n}^i,
\end{equation}
From which we conclude that the stress tensor must satisfy,
\begin{equation}
\sigma^{ij}=-p\delta^{ij}+\tau^{ij}\left(\mathbf{u}\right),
\end{equation}
where $$\tau^{ij}$$ is an unknown element that depends on the fluid velocity and vanishes in the case of zero fluid motion.

Specifically, the deviatoric stress $$\tau^{ij}$$ should be symmetric, and because deviatoric stress should not arise from rigid body motion, depend only on the rate of strain tensor $$E^{ij}$$. We proceed by making a guess, assuming the simplest constitutive relation, with the stress deviator depending linearly on the rate of strain,
\begin{equation}
\tau^{ij}=A^{ij}_{kl}E^{kl},
\end{equation}
where the fourth-order tensor $$A^{ijkl}$$ is symmetric in its first two indices. The most general isotropic such fourth-order tensor that is invariant under coordinate rotations is given by,

\begin{equation}
A_{ijkl}=\lambda\delta_{ij}\delta_{kl}+\mu\left(\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk}\right).
\end{equation}
With this choice, we find the most general constitutive relation for the stress tensor is,
\begin{equation}\label{eq: stress tensor constitutive relation} 
\sigma^{ij}=\left(-p+\lambda E^k_k\right)\delta^{ij}+2\mu E^{ij}.
\end{equation}
Fluids for which this serves as a constitutive model are known as <em>Newtonian fluids</em>. Again, we should remember this relationship is little more than an educated guess. Fortunately, experimental results have verified that most gases and ordinary liquids are fairly Newtonian. Non-Newtonian fluids also very much exist, and their study opens another several cans of complicated worms. 

Finally, inserting Eq. \ref{eq: stress tensor constitutive relation} into our second-law inequality, Eq. \ref{eq: entropy constitutive inequality}, 
\begin{equation}
\left(\lambda +\frac{2}{3}\mu\right)\left(E^k_k\right)^2+2\mu \left(E^{ij}-\frac{1}{3}E^l_l\delta^{ij}\right) \left(E_{ij}-\frac{1}{3}E^k_k\delta_{ij}\right) + k\partial_i\theta\partial^i\theta\geq 0.
\end{equation}
From which we constrain the constants,
\begin{equation}
\left(\lambda+\frac{2}{3}\right)\geq 0,\quad\mu\geq0,\quad k\geq0,
\end{equation}
$$\mu$$ is the fluid viscosity and $$\left(\lambda+\frac{2}{3}\right)$$ is known as the bulk viscosity. 

## The Equations of Motion for A Newtonian Fluid
We are ready to assemble the equations of motion for a Newtonian fluid. Armed with nine new constitutive equations, we now have $$14$$ equations to match $$14$$ unknowns. Applying our constitutive relations, Eq. \ref{eq: fourier law constitutive} and Eq. \ref{eq: stress tensor constitutive relation}, we obtain the following set of differential equations,
\begin{equation}
D_t\rho+\rho\partial_iu^i=0,
\end{equation}
\begin{equation}
\rho D_tu^i=f^i-\partial^ip+\partial^i\left[\left(\lambda+\frac{2}{3}\mu\right)\partial_ju^j\right]+2\partial_j\left[\mu E^{ij}\right]-\frac{2}{3}\partial^i\left[\mu\partial_ju^j\right],
\end{equation}
\begin{equation}
\rho c_p D_t\theta =  \left(\lambda +\frac{2}{3}\mu\right)\left(E^k_k\right)^2+2\mu \left(E^{ij}-\frac{1}{3}E^l_l\delta^{ij}\right) \left(E_{ij}-\frac{1}{3}E^k_k\delta_{ij}\right) + \partial_i\left(k\partial^i\theta\right) - \frac{\theta}{\rho} \frac{d\rho}{d\theta}\|_p D_t p.
\end{equation}
These are the continuity equation, the momentum equation, and the equation of thermal energy balance. The most common assumption to make is that of incompressibility, which is a statement that the density is independent of the pressure sch that $$D_t \rho=0$$. This is a very reasonable assumption if the characteristic fluid velocity is much lower than the speed of sound in the fluid, which is usually the case for liquids. Therefore, for an incompressible fluid, $$\partial_iu^i=0$$, and the velocity field is solenoidal.

For an incompressible fluid, our equations simplify significantly, 
\begin{equation}
\partial_iu^i=0,
\end{equation}
\begin{equation}
\rho D_tu^i=f^i-\partial^ip+2\partial_j\left[\mu E^{ij}\right],
\end{equation}
\begin{equation}
\rho c_p D_t\theta = 2\mu E^{ij}E_{ij} + \partial_i\left(k\partial^i\theta\right) - \frac{\theta}{\rho} \frac{d\rho}{d\theta}\|_p D_t p.
\end{equation}

For a final simplification, if we assume the fluid is also isothermal and we assume that the viscosity can be approximated as constant, we obtain the **Navier-Stokes equations** for an incompressible, isothermal fluid,
\begin{equation}
\rho\partial_iu^i=0,
\end{equation}
\begin{equation}
\rho D_tu^i=f^i-\partial^ip+\mu\partial^j\partial_ju^i,
\end{equation}
which should look somewhat familiar!

## Boundary Conditions
We aren't quite done. Any differential equation system requires boundary conditions to be soluble. Without boundary conditions, we cannot solve our problem. Here, we discuss boundary conditions for different types of interfaces and conditions. 

Consider two phases denoted with velocities $$\mathbf{u}$$ and $$\tilde{\mathbf{u}}$$. The interface itself may also have a velocity denoted by $$\mathbf{u}_I$$. First, at the interface, we must have mass conservation, with the amount of "stuff" flowing between phases to match,
\begin{equation}\label{eq: normal velocity mass conservation BC}
\rho\left(u^i-u^i_I\right)\hat{n}_i=\tilde{\rho}\left(\tilde{u}^i-u^i_I\right)\hat{n}_i\quad\text{at interface}.
\end{equation}
This also applies to a phase-transition process, for instance, a liquid changing to a solid with a different density. In the case of equal densities between both phases, we simply have a normal velocity matching condition, $$u^i\hat{n}_i=\tilde{u}^i\hat{n}_i$$.

Now for thermal boundary conditions. First, any phase boundary should keep thermal equilibrium, so it follows that,
\begin{equation}
\theta=\tilde{\theta}\quad\text{at interface}.
\end{equation}
The second boundary condition arises from the conservation of thermal energy at the interface. This requires the total heat flux vectors to match at the interface. The heat flux vector for a Fourier Law fluid is defined as,
\begin{equation}
j^i=-k\partial^i\theta + \rho\left(u^i-u^i_I\right)C_p\left(\theta-\theta_\text{ref}\right).
\end{equation}
The heat flux vector is the sum of the surface flux vector and the convective heat flux. Matching the normal component of the heat flux vectors at the interface,
\begin{equation}
-k\partial^i\hat{n} _i \theta+ \rho\left(u^i-u^i _I\right)\hat{n}_iC _p\left(\theta-\theta _\text{ref}\right)=-\tilde{k}\partial^i\hat{n} _i \tilde{\theta} + \tilde{\rho}\left(\tilde{u}^i-u^i_I\right)\hat{n} _i \tilde{C} _p\left(\tilde{\theta}-\theta _\text{ref}\right)\quad\text{at interface}.
\end{equation}
We can also express this relation in terms of the enthalpy $$H$$, replacing the $$C_p\Delta\theta$$ term,
\begin{equation}
-k\partial^i\hat{n} _i \theta+ \rho\left(u^i-u^i _I\right)\hat{n}_iH=-\tilde{k}\partial^i\hat{n} _i \tilde{\theta} + \tilde{\rho}\left(\tilde{u}^i-u^i_I\right)\hat{n} _i \tilde{H}\quad\text{at interface}.
\end{equation}
Employing Eq. \ref{eq: normal velocity mass conservation BC}, we may express the relation in terms of the <em>latent heat per unit mass</em>, $$\tilde{H}-H$$.
\begin{equation}
\tilde{k}\partial^i\hat{n} _i \tilde{\theta}= \rho\left(u^i-u^i_I\right)\hat{n} _i \left(\tilde{H}-H\right)\quad\text{at interface}.
\end{equation}
The thermal energy balance at the interface requires an imbalance in the heat flux equal to the change of enthalpy at the material boundary.

Next is the tangential velocity match. There is no macroscopic principle underlying this relationship; the <em>no-slip</em> condition is generally accepted based on empirical evidence for Newtonian fluids. 
\begin{equation}\label{eq: no slip condition}
u^i-\left(u^i\hat{n}_i\right)\hat{n}^i=\tilde{u}^i-\left(\tilde{u}^i\hat{n}_i\right)\hat{n}^i\quad\text{at interface}.
\end{equation}

Eq. \ref{eq: normal velocity mass conservation BC} and Eq. \ref{eq: no slip condition} constitute only three conditions for six velocity components; there are a few other considerations to be considered at an interface. Here, we assume the interface is deformable and is between two fluids without a phase change. First, we introduce a scalar function $$\phi\left(\mathbf{x},t\right)$$ describing the interface such that for a set of points lying at the interface, $$\mathbf{x}_s$$,
\begin{equation}
\phi\left(\mathbf{x}_s,t\right)=0,
\end{equation}
From which it is simple to show that the unit normal to the surface is given by,
\begin{equation}
\hat{n}_i=\pm\frac{\partial_i\phi}{\sqrt{\partial_j\phi\partial^j\phi}},
\end{equation}
with the sign chosen to be the outer unit normal vector in the context of the problem. Because $$\phi$$ is always zero on the interface, its convective derivative along the interface must be zero,
\begin{equation}
\partial_t\phi+u^i\partial_i\phi=0\rightarrow\frac{\partial_t\phi}{\sqrt{\partial_j\phi\partial^j\phi}}+u^i\hat{n}_i=0\quad\text{at interface}.
\end{equation}
This is the general form of the kinematic boundary condition.

There is also a stress balance condition at the interface. Consider the force balance for an arbitrary fluid surface element, denoted as $$A$$. Denote the unit normal at any point on $$A$$ as $$\hat{n}_i$$, and denote the boundary curve $$C$$ around the edge of the surface $$A$$. Let $$\hat{t}_i$$ be a unit vector that is normal to $$C$$ and tangent to $$\hat{n}_i$$ at each point. The traction imbalance integrated over the surface $$A$$ is compensated by a surface tension force with magnitude $$\gamma$$, known as the interfacial tension. Mathematically, we express this balance as,
\begin{equation}\label{eq: tension condition BC}
\int_AdA\ \left(\sigma^{ij}-\tilde{\sigma}^{ij}\right)\hat{n}_j + \oint_C dS\ \gamma\hat{t}^i=0,
\end{equation}
the negative sign before $$\tilde{\sigma}^{ij}$$ is a consequence of our choice in the unit normal direction. Now consider the vector $$\hat{r}_i$$, which moves clockwise around the boundary $$C$$, so the tangent vector is, $$\hat{t}_i=\epsilon _{ijk}\hat{r}^j\hat{n}^k$$, from which is follows,
\begin{equation}
\oint_C dS\ \gamma\hat{t}^i=\oint_C dS\ \gamma\epsilon _{ijk}\hat{r}^j\hat{n}^k=\int_AdA\hat{n} _m\epsilon^{mjk}\partial_j\left(\gamma\epsilon^i _{kl}\hat{n}^l\right),
\end{equation}
where we have applied Stokes' theorem to turn the boundary integral into a surface integral. Then using the identities of the Levi-Cevita symbol, $$\epsilon^{mjk}\epsilon^i _{kl}=\delta^{ij}\delta^m_l-\delta^{im}\delta^j_l$$,
\begin{equation}\label{eq: stokes boundary area tension}
\oint_C dS\ \gamma\hat{t}^i=\int_AdA\left[\hat{n}_j\partial^i\left(\gamma\hat{n}^j\right)-\hat{n}^i\partial_j\left(\gamma\hat{n}^j\right)\right].
\end{equation}
Combining Eq. \ref{eq: tension condition BC} and Eq. \ref{eq: stokes boundary area tension} applied to an arbitrary surface element, and recalling that $$\hat{n}_j\partial^i\left(\hat{n}^j\right)=0$$, we find,
\begin{equation}
\left(\sigma^{ij}-\tilde{\sigma}^{ij}\right)\hat{n}_j+\left(\partial^i-\hat{n}^i\hat{n}^j\partial_j\right)\left[\gamma\right]-\gamma\hat{n}^i\partial_j\left(\hat{n}^j\right)=0.
\end{equation}
These are our final three boundary conditions: one in the normal direction and one each in the two tangential directions. In the normal direction, we have,
\begin{equation}
\left(\tilde{p}-p\right)+\left(\tau^{ij}-\tilde{\tau}^{ij}\right)\hat{n}_j\hat{n}_i-\gamma\partial_j\left(\hat{n}^j\right)=0.
\end{equation}
For each tangential direction, with tangent vectors components notated as $$\hat{t} _{(k)}^i$$ with $$k=1,2$$,
\begin{equation}
\left(\tau^j_i-\tilde{\tau}^j_i\right)\hat{n}_j\hat{t} _{(k)}^i+\hat{t} _{(k)}^i\partial_i\left[ \gamma \right]=0.
\end{equation}

 We have found all the boundary conditions necessary to solve our problem. Armed with a physical description of the fluid field and all relevant boundary conditions for a given interface, we can now, at least in principle, tackle any problem involving Newtonian fluids. Granted, by "tackle" I mean to approach the problem as a physicist would, who happily stops once the governing equations of motion are found and the problem is determined to be soluble. As to actually getting solutions, that is up to the very clever mathematician.

### Sources
These notes follow very closely the first chapter of Leal's excellent book,

_Leal G. Advanced Transport Phenomena. Cambridge University Press; 2007._

