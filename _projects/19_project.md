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
\int_{A_m(t)} dA\ \epsilon^i _{jk}x^j\hat{n} _l \sigma^{kl} = \int _{V _m(t)} dV\ \left[ \epsilon^i _{lk} \sigma^{kl} \right].
\end{equation}

\begin{equation}
\int_{A_m(t)} dA\ \epsilon^i_{jk}x^j\hat{n} _l \sigma^{kl} = \int _{V_m(t)} dV\ \left[\epsilon^i_{lk}\sigma^{kl} + \epsilon^i_{jk}x^j\partial_l\sigma^{kl}\right].
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
D_t\left[\int_{V_m(t)} dV\ \left[\frac{1}{2}\rho u^iu_i + \rho e\right]\right] =\left(\text{rate of work done on }V_m(t)\right)
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
de=\theta dd - p dV,
\end{equation}
where $$dd$$ is the change in specific entropy of the system,
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

Finally, we combine Eq. {eq: enthalpy differential element} with Eq. \ref{eq: entropy differential element final} to write the change in enthalpy in terms of the pressure, density, and temperature,
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
\begin{equation}
\sigma^{ij}E_{ij}+p\partial_iu^i - \frac{1}{\theta}q^i\partial_i\theta\geq 0.
\end{equation}
Although this result is not instantly helpful, we will see that it aids in obtaining constitutive relationships for the stress tensor and heat flux vector.

## Constitutive Relationships
Let's pause and take stock of our progress. So far, we have obtained five differential equations from basic principles of mass, momentum, and energy conservation:
<ol>    
<li> The continuity equation, Eq. \ref{{eq: continuity equation}}</li>
<li> Cauchy's equation, Eq. \ref{eq: Cauchy momentum equation}</li>
<li> Thermal energy balance equation, Eq. \ref{eq: thermal energy balance equation}</li>
</ol>
We also have a restriction on the symmetry of the stress tensor based on the conservation of angular momentum and an inequality based on the second law of thermodynamics. Unfortunately, our system is still severely undertermined, we have $$14$$ unkowns, $$\rho + u^i + \sigma^{ij} + p + q^i$$, for our five equations. We must find additional relationships in order to determine solutions for our independent variables.

## Fourier's Law


### Sources

