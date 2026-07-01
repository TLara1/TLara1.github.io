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

Back in high school, I would always aspire to fill my notebooks and chalkboards with deranged mathematical scribblings that looked oh so incomprehensible. Unfortunately, as I learned more physics and maths, the incomprehensible became comprehensible and my scribblings never quite reached the heights of insanity to which I aspired. Except in Quantum Field Theory (QFT). Even the most organized, well-documented, structured QFT calculation (that these notes certainly are not) looks like a mess, with enough symbols and letters to boggle even the most intrepid physicist.

I am, unfortunately, no longer much of a theoretical physicist. I took three semesters of QFT and decided it was not for me. But there is a beauty in the calculations of QFT, the slow methodical alignment of a maelstrom of algebra and indices. I doubt these notes will serve me much in the future, but I wish to conserve some fraction of what I learned in QFT in a more permanent manner. (You can clearly tell I wrote this **before** embarking on my calculations. I am currently halfway through and am wondering why I ever decided this was a good or reasonable idea).

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
There are also a number of properties involving the traces of the gamma matrices,
\begin{equation}
\text{tr}\left[\gamma^\mu\gamma^\nu\right]=4\eta_{\mu\nu},\quad\text{tr}\left[\gamma^\mu\gamma^\nu\gamma^\alpha\gamma^\beta\right]=4\left(\eta_{\mu\nu}\eta_{\alpha\beta}-\eta_{\mu\alpha}\eta_{\nu\beta}+\eta_{\mu\beta}\eta_{\nu\alpha}\right).
\end{equation}
Furthermore, due to anticommutation, the trace of a product of an odd number of gamma matrices is zero.

A few more properties related to the sums of gamma matrices that can be similarly obtained from the commutation relation,
\begin{equation}
\gamma^mu\gamma_mu = d,\quad\gamma^mu\gamma^nu\gamma_\nu=\left(2-d\right)\gamma^\nu,
\end{equation}
where $$d$$ is the number of spacetime dimensions.

We also define the adjoint $$\bar{\psi}^\mu$$ operation as,
\begin{equation}
\bar{\psi}^\mu=\left(\psi^\mu\right)^\dagger\gamma^0,
\end{equation}
where $$\psi$$ is a four-component spinor. We use the $$\not p$$ notation to denote a combination with the gamma matrices,
\begin{equation}
\not{p}=\gamma^\mu p_\mu.
\end{equation}
We also use the $$\bar d$$ notation to indicate division by $$2\pi$$, 
\begin{equation}
\bar{d} k = \frac{d k}{2\pi}
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
\sum_{s} u^{(s)} \bar{u}^{(s)}=\not{p}+m,\quad\sum_{r} v^{(r)} \bar{v}^{(r)}=\not{p}-m,
\end{equation}
\begin{equation}
\sum_{s} \epsilon^\mu \left(\epsilon^{*}\right) ^\nu = -\eta^{\mu\nu} + \left(1-\xi\right)\frac{p^\mu p^nu}{p^2}.
\end{equation}

These relations will come in handy when resolving our diagrams. 

## The Photonic Propagator at One Loop
In this section, we are interested in the two-point photonic propagator $$D_{\mu\nu}$$, which, in general, will have a diagram resembling: 

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
t_{\mu\nu}=\eta_{\mu\nu}-\left(1-\xi\right)\frac{q_\mu q_\nu}{q^2},\quad t _{T\ \mu\nu}=\eta _{\mu\nu}-\frac{q _\mu q _\nu}{q^2},
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

Finally, we are ready to start integrating to determine the value of $$\Pi\left(q\right)$$. Reading off the Feynman rules from the 1PI 1-loop diagram,
\begin{equation}\label{1pi photon loop integral}
i q^2 \Pi\left(q\right) t _{T\ \mu\nu} = \left(-i e\right)^2(-1)\int\bar{d}^dk\ \frac{\text{tr}\left[\gamma^\mu i\left(\not k+m\right)i\gamma^\nu\left(\not q + \not k +m \right)\right]}{\left(k^2-m^2\right)\left(\left(k+q\right)^2-m^2\right)}.
\end{equation}
I have written the integral in $$d$$ dimensions, which should be $$d=4$$, but we will keep it as $$d$$ for now for reasons that will be evident later. The factor of $$(-1)$$ arises from the presence of a closed Fermion loop and we take the trace over the closed fermion loop.

Lovely. Okay, here we go. First, we use the Feynman parameterization, which is the integral identity,
\begin{equation}
\frac{1}{ab}=\int_0^1dx\ \frac{1}{\left(ax+b\left(1-x\right)\right)^2}.
\end{equation}
The denominator of the integrand of Eq. \ref{1pi photon loop integral} becomes,
\begin{equation}
\left[\text{Den}\right]=\left( x\left(k+q\right)^2+\left(1-x\right)k^2-m^2 \right)^2=\left(\ell^2-\Delta\right)^2,\quad\ell=k+xq,\ \Delta=m^2-x\left(1-x\right)q^2.
\end{equation}
In substituting $$\ell$$ and $$\Delta$$, we have simply completed the square. Since $$\ell$$ is linear in $$k$$, our integral over $$k$$ becomes an integral over $$\ell$$,
\begin{equation}
\int\bar{d}^dk\ \frac{\left[\text{Num}\right]}{\left[\text{Den}\right]} = \int\bar{d}^d\ell\ \int_0^1 dx \frac{\left[\text{Num}\right]}{ \left(\ell^2-\Delta \right)^2 }.
\end{equation}

The numerator is a bit trickier. With our gamma matrix trace identities, we have,
\begin{equation}
\left[\text{Num}\right]=-\text{tr}\left[\left(\gamma^\mu \not k \gamma^\nu+m\gamma^\mu\gamma^\nu\right)\left(\not q + \not k +m \right)\right] 
\end{equation}
\begin{equation}
= -4 m^2 \eta^{\mu\nu} - 4\left( 2k^\mu k^\nu + k^\mu q^\nu + k^\nu q^\mu - \eta^{\mu\nu} \left(k^2 + k^\alpha q_\alpha\right) \right), \nonumber
\end{equation}
and substituting in $$\ell$$,
\begin{equation}
-\frac{1}{4}\left[\text{Num}\right]=\left(\ell^\mu-x q^\mu\right) \left(\ell^\nu+\left(1-x\right)q^\nu\right) + \left(\ell^\nu-x q^\nu\right) \left(\ell^\mu+\left(1-x\right)q^\mu\right)
\end{equation}

\begin{equation}
-\eta^{\mu\nu}\left(\left(\ell^\alpha-x q^\alpha\right) \left(\ell_\alpha+\left(1-x\right)q_alpha\right)-m^2\right).\nonumber
\end{equation}

We can simplify. Since the denominator is even in $$\ell$$, any term in the numerator that is odd in $$\ell$$ integrates to $$0$$
\begin{equation}
-\frac{1}{4}\left[\text{Num}\right]=2\left(\ell^\mu\ell^\nu-x\left(1-x\right) q^\mu q^\nu\right) - \eta^{\mu\nu} \left(\ell^2 - x(1-x)q^2-m^2\right).
\end{equation}

Now let's consider the $$\ell^\mu\ell^nu$$ terms. The integral over these terms can be written as,
\begin{equation}
I^{\mu\nu}=\int \bar{d}^d \ell\ \frac{\ell^\mu\ell^\nu}{f\left(\ell^2\right)},
\end{equation}
but we know $$I^{\mu\nu}$$ should have no preferred direction and is symmetric in its indices, so it must be proportional to the metric, writing,
\begin{equation}
I^{\mu\nu}=C\eta^{\mu\nu},
\end{equation}
by normalization,
\begin{equation}
I^{\mu\nu}\eta_{\mu\nu}=C\eta^{\mu\nu}\eta_{\mu\nu}=Cd,
\end{equation}
for a $$d$$-dimensional spacetime. So, we conclude that we can replace the $$\ell^\mu\ell^\nu$$ terms with $$\eta^{\mu\nu}\ell^2/d$$, and the numerator becomes,
\begin{equation}
-\frac{1}{4}\left[\text{Num}\right]=x\left(1-x\right)\left(q^2\eta^{\mu\nu} -2  q^\mu q^\nu \right) + m^2\eta^{\mu\nu} + \left(\frac{2}{d} - 1\right)\ell^2.
\end{equation}

We have two integrals to evaluate. First, terms in the numerator that have constant coefficients,
\begin{equation}
\int\bar{d}^d\ell\ \frac{1}{\left(\ell^2-\Delta\right)^2}=i\int\bar{d}^d\ell_E\ \frac{1}{ \left( \ell_E^2+\Delta \right)^2 }.
\end{equation}
We have performed a Wick Rotation, the Euclidean momenta $$\ell_E^\mu$$ are related to $$\ell^\mu$$ with,
\begin{equation}
\ell_E^0=i\ell^0,\ \ell_E^i=\ell^i.
\end{equation}
from which it follows that,
\begin{equation}
\ell^2=\eta_{\mu\nu}\ell^\mu\ell^nu=-\ell_E^2=-\left(\ell_E^0\right)^2-\left(\ell_E^1\right)^2-\left(\ell_E^2\right)^2-\left(\ell_E^3\right)^2.
\end{equation}
We can now transform the integral into spherical coordinates with the $$d$$-dimensional radius $$r_E^2=\ell_E^2$$ and,
\begin{equation}
\bar{d}^d\ell_E = dr_E r_E^{d-1} d\Omega_d.
\end{equation}
We evaluate the $$d-1$$ angular dependence using the standard result for the volume of a $$d$$ ball,
\begin{equation}
\int d\Omega_d = \frac{2\pi^{d/2}}{\Gamma\left(d/2\right)}.
\end{equation}
In summary, our integral has been transformed into,
\begin{equation}
\int\bar{d}^d\ell\ \frac{1}{\left(\ell^2-\Delta\right)^2}=\frac{ 2\pi^{d/2}i }{\left(2\pi\right)^d\Gamma\left(d/2\right)}\int_0^\infty dr_E\ \frac{r_E^{d-1}}{ \left( r_E^2+\Delta \right)^2}.
\end{equation}
After evaluating the final integral using the Beta function, we find
\begin{equation}
\int\bar{d}^d\ell\ \frac{1}{\left(\ell^2-\Delta\right)^2}=\frac{ i }{ \left(4\pi\right)^{d/2} }\Gamma\left(2-d/2\right)\Delta^{d/2-2}.
\end{equation}
Using the exact same procedure for the $$\ell^2$$ integrals, we obtain
\begin{equation}
\int\bar{d}^d\ell\ \frac{\ell^2}{\left(\ell^2-\Delta\right)^2}=-\frac{ 2\pi^{d/2}i }{\left(2\pi\right)^d\Gamma\left(d/2\right) }\int_0^\infty dr_E\ \frac{r_E^{d+1}}{ \left( r_E^2+\Delta \right)^2}
\end{equation}
\begin{equation}
=-\frac{ i }{\left(4\pi\right)^{d/2}\Gamma\left(d/2\right)}\Gamma\left(1+d/2\right)\Gamma\left(1-d/2\right)\Delta^{d/2-1}.\nonumber
\end{equation}
We may modify this slightly with the recurance relation $$\Gamma\left(z+1\right)=z\Gamma\left(z\right)$$,
\begin{equation}
\int\bar{d}^d\ell\ \frac{\ell^2}{\left(\ell^2-\Delta\right)^2}=-\frac{ i }{\left(4\pi\right)^{d/2}\left(1-d/2\right)}\frac{d}{2}\Gamma\left(2-d/2\right)\Delta^{d/2-1}.
\end{equation}

We are ready to integrate over $$\ell$$ for the terms in our numerator,
\begin{equation}
\int\bar{d}^d\ell\ \frac{ x\left(1-x\right)\left(q^2\eta^{\mu\nu} -2  q^\mu q^\nu \right) + m^2\eta^{\mu\nu} }{ \left(\ell^2-\Delta \right)^2 }
\end{equation}
\begin{equation}
=\frac{ i }{ \left(4\pi\right)^{d/2} }\left( x\left(1-x\right)\left(q^2\eta^{\mu\nu} -2  q^\mu q^\nu \right) + m^2\eta^{\mu\nu} \right)\Gamma\left(2-d/2\right)\Delta^{d/2-2}\nonumber
\end{equation}
\begin{equation}
=\frac{ i }{ \left(4\pi\right)^{d/2} }\left( 2x\left(1-x\right)q^2 t^{\mu\nu}_T + \Delta \eta^{\mu\nu} \right)\Gamma\left(2-d/2\right)\Delta^{d/2-2}.\nonumber
\end{equation}
For the $$\ell^2$$ term,
\begin{equation}
\int\bar{d}^d\ell\ \frac{ \left(\frac{2}{d} - 1\right)\ell^2 }{ \left(\ell^2-\Delta \right)^2 }= -\frac{ i \left(\frac{2}{d} - 1\right)}{\left(4\pi\right)^{d/2}\left(1-d/2\right)}\frac{d}{2}\Gamma\left(2-d/2\right)\Delta^{d/2-1}.
\end{equation}
\begin{equation}
= -\frac{ i }{\left(4\pi\right)^{d/2}}\Gamma\left(2-d/2\right)\Delta^{d/2-1}.\nonumber
\end{equation}
As expected, the non-$$t^{\mu\nu}_T$$ terms cancel, and writing out our loop integral in full,
\begin{equation}
\int\bar{d}^d\ell\ \frac{\left[\text{Num}\right]}{ \left(\ell^2-\Delta \right)^2 } = -\frac{ 8i }{ \left(4\pi\right)^{d/2} }q^2 t^{\mu\nu}_T\Gamma\left(2-d/2\right)x\left(1-x\right)\Delta^{d/2-2}.
\end{equation}

Wonderful, now we need only evaluate the integral over $$x$$ arising from the Feynman parametrization, which means calculating the integral,
\begin{equation}
\frac{\Gamma\left(2-d/2\right)}{ \left(4\pi\right)^{d/2} } \int_0^1 dx\ x\left(1-x\right)\left(m^2-x(1-x)q^2\right)^{d/2-2},
\end{equation}
for $$d=4$$. Unfortunately, this expression is divergent as $$d\rightarrow4$$, which is the whole reason we need to go about this program of renormalization. The key is that because we have reduced the complicated integral into this simple form, it is easy to extract the divergent element. We will replace $$d\rightarrow 4-2\epsilon$$, and study the limit as $$\epsilon\rightarrow0$$. We need only retain terms that are order $$\epsilon^0$$ or smaller, as the rest will vanish.
\begin{equation}
\frac{\Gamma\left(2-d/2\right)}{ \left(4\pi\right)^{d/2} }  \int_0^1 dx\ x\left(1-x\right)\left(m^2-x(1-x)q^2\right)^{d/2-2}
\end{equation}
\begin{equation}
=\frac{1}{\left(4\pi\right)^2}4\pi^\epsilon\Gamma\left(\epsilon\right) \int_0^1 dx\ x\left(1-x\right)\left(m^2-x(1-x)q^2\right)^{-\epsilon},\nonumber
\end{equation}
with the usual expansion for small $$\epsilon$$,
\begin{equation}
\Gamma\left(\epsilon\right)=\frac{1}{\epsilon}-\gamma_E+\mathcal{O}\left(\epsilon\right),\quad A^\epsilon=1+\epsilon\log\left(A\right),
\end{equation}
where $$\gamma_E$$ is Euler's gamma constant. Expanding,
\begin{equation}
4\pi^\epsilon\Gamma\left(\epsilon\right) \int_0^1 dx\ x\left(1-x\right)\left(m^2-x(1-x)q^2\right)^{-\epsilon}
\end{equation}
\begin{equation}
= \int_0^1 dx\ x\left(1-x\right)\left(\frac{1}{\epsilon}-\gamma_E+...\right)\left(1+\epsilon\log\left(4\pi\right)-\epsilon\log\left(m^2-x(1-x)q^2\right)+...\right)\nonumber
\end{equation}

\begin{equation}
4\pi^\epsilon\Gamma\left(\epsilon\right) \int_0^1 dx\ x\left(1-x\right)\left(m^2-x(1-x)q^2\right)^{-\epsilon}
\end{equation}
\begin{equation}
= \frac{1}{6}\epsilon^{-1}+\frac{1}{6}\left(\log\left(4\pi\right)-\gamma_E\right) -
\int_0^1 dx\ x\left(1-x\right)\log\left(m^2-x(1-x)q^2\right) + ...\nonumber
\end{equation}

where all unwritten terms vanish with $$\epsilon$$. The integral over $$x$$ is convergent, although perhaps imaginary in the massless limit $$m\rightarrow0$$, which is okay as far as renormalization is concerned.

Finally, including all terms and writing the 1PI function $$\Pi(q)$$, we obtain,
\begin{equation}
\Pi= 2\frac{ e^2}{ 4\pi^2 } \left(-\frac{1}{6}\epsilon^{-1}-\frac{1}{6}\left(\log\left(4\pi\right)-\gamma_E\right)+
\int_0^1 dx\ x\left(1-x\right)\log\left(m^2-x(1-x)q^2\right)\right).
\end{equation}
There is a slight problem in the dimensionality of our answer. Notice that we are taking the logarithm of a dimensional quantity, which cannot possibly be correct. We can resolve this by performing the rescaling,
\begin{equation}
e\rightarrow e'\left(\mu\right)\mu^{\epsilon},
\end{equation}
where $$\mu$$ has dimension 1 and $$e'$$ is dimensionless. Inserting the appropriate factors of $$\mu$$ before expanding in small $$\epsilon$$, we find,
\begin{equation}
\Pi= 2\frac{ e'^2}{ 4\pi^2 } \left(-\frac{1}{6}\epsilon^{-1}-\frac{1}{6}\left(\log\left(4\pi\right)-\gamma_E\right)+
\int_0^1 dx\ x\left(1-x\right)\log\left(\frac{m^2-x(1-x)q^2}{\mu^2}\right)\right).
\end{equation}
This resolution may seem a little off the cuff, we will return to these ideas later after assessing all other loop diagrams and formalize the rescalings for $$e$$ and the other scales in the problem.

## The Fermionic Propagator at One Loop
In the same vein as our photonic calculation, we calculate the 1-loop correction for the fermionic two-point propagator $$S(p)$$. Again, the general propagators can be decomposed as a sum of the tree-level diagram and 1PI diagrams. 

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/QED_diagrams/S_fermion_propagator.png" title="S_fermion_propagator" class="img-fluid rounded z-depth-0" width="auto" height="270" %}
</div>

The 1PI diagram we calculate is $$i\Sigma(p)$$. We perform the calculation in a general gauge. Consulting our Feynman diagram, the loop integral is,

\begin{equation}\label{1pi fermion loop integral}
i \Sigma = \left(-i e\right)^2 \left[\int\bar{d}^dk\  \frac{\gamma^\mu i\left(\not k + m\right)\gamma^\nu\left(-i\eta_{\mu\nu}\right)}{\left(k^2-m^2\right)\left(k-p\right)^2} \right.
\end{equation}

\begin{equation}
\left. + \int\bar{d}^dk\ \frac{\gamma^\mu i\left(\not k + m\right)\gamma^\nu\left(i\left(1-\xi\right)\left(k-p\right) _\mu\left(k-p\right) _\nu \right) }{\left(k^2-m^2\right)\left(k-p\right)^4} \right] \nonumber
\end{equation}

\begin{equation}
 = \left(-i e\right)^2 \left[ I + I _\xi\right].
\end{equation}

where $$I$$ and $$I_\xi$$ denote the ordinary and the gauge integrals, respectively. As the steps are repeated from our previous loop integral, we will be a little more terse this time around.

### Gauge-less Integral
The first of these looks somewhat more wholesome, so let's begin there.
\begin{equation}
I = \int\bar{d}^dk\ \frac{\gamma^\mu i\left(\not k + m\right)\gamma^\nu\left(-i\eta_{\mu\nu}\right)}{\left(k^2-m^2\right)\left(k-p\right)^2}.
\end{equation}
With Feynman parameters,
\begin{equation}
\left[\text{Den}\right] = \left((k-p)^2x + (k^2-m^2)(1-x)\right)^2 = \left(\ell-\Delta\right)^2,\quad\ell=k-xp,\ \Delta = \left(1-x\right)\left(m^2-xp^2\right).
\end{equation}
The numerator becomes, after using gamma matrix identities,
\begin{equation}
\left[\text{Num}\right] = \gamma^\mu \left(\not k + m\right)\gamma_\mu = dm + (2-d)\not k = dm + (2-d) x \not p,
\end{equation}
we have dropped the term linear in $$\ell$$ that vanishes over integration. Using the same dimensional regularization as we did previously in $$d=4-2\epsilon$$ dimensions,
\begin{equation}
\int\bar{d}^d\ell\ \frac{1}{\left(\ell^2-\Delta\right)^2}=\frac{ i }{ \left(4\pi\right)^{2} }\left(4\pi\right)^{\epsilon}\Gamma\left(\epsilon\right)\Delta^{-\epsilon}.
\end{equation}
This gives the expression for $$I$$,
\begin{equation}
I = \frac{ i }{ \left(4\pi\right)^{2} }\Gamma\left(\epsilon\right)\int_0^1 dx\ \left(\left(4-2\epsilon\right)m + (2\epsilon-2) x\not p\right)\left(\frac{\Delta}{4\pi}\right)^{-\epsilon}.
\end{equation}
Expanding the integrand around small $$\epsilon$$,
\begin{equation}
I = \frac{ i }{ \left(4\pi\right)^{2} }\int_0^1 dx\ \left[ \frac{2}{\epsilon}\left(m - x\not p\right) +2\left(x \not p-m\right)+2\left(x\not p -2m\right)\left(\log\left(\frac{\Delta}{4\pi}\right)+\gamma_E\right) + ... \right]
\end{equation}
and performing the integral and removing terms linear in $$\epsilon$$,
\begin{equation}
I = \frac{ i }{ \left(4\pi\right)^{2} }\left[\frac{1}{\epsilon}\left(4m-\not p\right)+\left(-2\left(1+2\gamma_E\right)m+\left(1+\gamma_E\right)\not p\right) + 2\int_0^1 dx\ \left(x\not p -2m\right)\log\left(\frac{\Delta}{4\pi}\right)\right].
\end{equation}
Excellent.

### Gauge-full Integral
The second, less wholesome integral is,
\begin{equation}
I_\xi = \int\bar{d}^dk\ \frac{\gamma^\mu i\left(\not k + m\right)\gamma^\nu\left(i\left(1-\xi\right)\left(k-p\right)_\mu\left(k-p\right) _\nu \right) }{\left(k^2-m^2\right)\left(k-p\right)^4}.
\end{equation}
We must employ the three-parameter Feynman trick,
\begin{equation}
\frac{1}{abc} =\int_0^1dx\ \int_0^{1-x}dy\ \frac{2}{\left(c+(a-c)x+(b-c)y\right)^3},
\end{equation}
and rewrite the denominator as,
\begin{equation}
\left[\text{Den}\right] = \left(\left(k-p\right)^2 + \left(-p^2 -m^2 + 2kp\right)x\right)^3 = \left(\ell^2-\Delta'\right)^3,
\end{equation}
\begin{equation}
\ell=k-\left(1-x\right)p,\ \Delta' = x\left(m^2+x\left(x-1\right)p^2\right).
\end{equation}
Integrating over $$y$$ and accounting for the prefactor, the integral becomes,

\begin{equation}
I_\xi = \int\bar{d}^d\ell\ \int _0^1 dx\ 2\left(1-x\right)\frac{\left[\text{Num}\right]}{\left(\ell^2-\Delta'\right)^3}.
\end{equation}

For the numerator,
\begin{equation}
\left[\text{Num}\right] = -\left(1-\xi\right)\left(\not k-\not p\right) \left(\not k + m\right)\left(\not k-\not p\right) =  -\left(1-\xi\right)\left(\not \ell-x\not p\right) \left(\not \ell+(1-x)\not p + m\right)\left(\not \ell-x\not p\right).
\end{equation}
Dropping terms that are odd in $$\ell$$ and employing our gamma matrix identities,
\begin{equation}
\left[\text{Num}\right] = -\left(1-\xi\right)\left[ 
-\ell^2\left(\left(1+x\right)\not p-m\right) + 2 (1-x)  \not \ell \ell^\mu p_mu+x^2p^2\left((1-x)\not p + m\right)\right]
\end{equation}
\begin{equation}
 = -\left(1-\xi\right)\left[-\ell^2\left(\left(1+x-\frac{2\left(1-x\right)}{d}\right)\not p-m\right) + x^2p^2\left((1-x)\not p + m\right) \right]. \nonumber
\end{equation}
Evaluating the integrals over $$\ell$$,
\begin{equation}
\int\bar{d}^d\ell\ \frac{1}{\left(\ell^2-\Delta'\right)^3}=-\frac{ i }{ 2\left(4\pi\right)^{2} }\Gamma\left(1+\epsilon\right)\left(\frac{\Delta}{4\pi}\right)^{-\epsilon}\Delta'^{-1},
\end{equation}
and,
\begin{equation}
\int\bar{d}^d\ell\ \frac{\ell^2}{\left(\ell^2-\Delta'\right)^3}=\frac{ i }{ 2\left(4\pi\right)^{2} \Gamma\left(2-\epsilon\right)}\Gamma\left(3-\epsilon\right)\Gamma\left(\epsilon\right)\left(\frac{\Delta'}{4\pi}\right)^{-\epsilon}
\end{equation}
\begin{equation}
=\frac{ i \left(2-\epsilon\right)}{ 2\epsilon\left(4\pi\right)^2 }\Gamma\left(1+\epsilon\right)\left(\frac{\Delta'}{4\pi}\right)^{-\epsilon}.\nonumber
\end{equation}
Evaluating the numerator,
\begin{equation}
\left[ \text{Num} \right] = -\left(1-\xi\right)\frac{i}{2\left(4\pi\right)^2} \left[  -\frac{\left(2-\epsilon\right)}{\epsilon}\left(\left(1+x-\frac{2\left(1-x\right)}{4-2\epsilon}\right)\not p-m\right) - x^2p^2\left((1-x)\not p + m\right) \Delta' ^{-1} \right]
\end{equation}
\begin{equation}
\times\Gamma\left(1+\epsilon\right)\left(\frac{\Delta'}{4\pi}\right)^{-\epsilon}.\nonumber
\end{equation}
We see there will be a term of order $$\epsilon^{-1}$$ in addition to the finite term. Expanding around $$\epsilon=0$$,
\begin{equation}
-\frac{\left(2-\epsilon\right)}{\epsilon}\left(\left(1+x-\frac{2\left(1-x\right)}{4-2\epsilon}\right)\not p-m\right) \Gamma\left(1+\epsilon\right)\left(\frac{\Delta'}{4\pi}\right)^{-\epsilon}
\end{equation}
\begin{equation}
 = \left(\frac{1}{\epsilon}\left(-\left(1+3x\right)\not p +2m\right)+\frac{1}{2}\left(1+3x\right)\not p - m + ...\right) \Gamma\left(1+\epsilon\right)\left(\frac{\Delta'}{4\pi}\right)^{-\epsilon}\nonumber
\end{equation}
\begin{equation}
= \frac{1}{\epsilon}\left(-\left(1+3x\right)\not p +2m\right)+\frac{1}{2}\left(1+3x\right)\not p - m + \left(\left(1+3x\right)\not p - 2m\right)\left(\gamma_E+\log\left(\frac{\Delta'}{4\pi}\right)\right) + ...\nonumber
\end{equation}
For the finite term,
\begin{equation}
-x^2p^2\left((1-x)\not p + m\right) \Delta' ^{-1} \Gamma\left(1+\epsilon\right) \left(\frac{\Delta}{4\pi}\right)^{-\epsilon}  = -x^2p^2\left((1-x)\not p + m\right)\Delta' ^{-1} + ...
\end{equation}
The full integral to leading order in $$\epsilon$$ is expressed as the sum of two integrals over $$x$$,
\begin{equation}
I_\xi = -\left(1-\xi\right) \frac{i}{2\left(4\pi\right)^2} \left[I_\xi^A+I_\xi^B\right],
\end{equation}
\begin{equation}
I_\xi^A = \int_0^1 dx\ 2\left(1-x\right)  \left[ \frac{1}{\epsilon}\left(-\left(1+3x\right)\not p +2m\right)+\frac{1}{2}\left(1+3x\right)\not p - m \right. 
\end{equation}

\begin{equation}
\left. + \left(\left(1+3x\right)\not p - 2m\right)\left(\gamma_E+\log\left(\frac{\Delta'}{4\pi}\right)\right) \right], \nonumber
\end{equation}

and,
\begin{equation}
I_\xi^B = -\int_0^1 dx\ 2\left(1-x\right) x^2p^2\left((1-x)\not p + m\right)\Delta' ^{-1}.
\end{equation}
Evaluating the first of these,
\begin{equation}
I_\xi^A = \frac{2}{\epsilon}\left(m-\not p\right) + \left(\not p -m \right)\left(1+2\gamma_E\right) + 2\int_0^1 dx\ \left(1-x\right)\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta'}{4\pi}\right).
\end{equation}
We combine to find the gauge-dependent integral,
\begin{equation}
I_\xi = -\left(1-\xi\right) \frac{i}{2\left(4\pi\right)^2} \left[\frac{2}{\epsilon}\left(m-\not p\right) + \left(\not p -m \right)\left(1+2\gamma_E\right) \right.
\end{equation}
\begin{equation}
\left. + 2\int_0^1 dx\ \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta'}{4\pi}\right)-x^2p^2\left((1-x)\not p + m\right)\Delta' ^{-1}\right] \right]. \nonumber
\end{equation}

Adding this to $$I$$,
\begin{equation}
I + I_\xi = \frac{ i }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}\left(3m\right)-3m\left(\frac{1}{2}+\gamma_E\right)+\frac{1}{2}\not p + 2\int_0^1 dx\ \left[\left(x\not p -2m\right)\log\left(\frac{\Delta}{4\pi}\right)  - \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta}{4\pi}\right)-x^2p^2\left((1-x)\not p + m\right)\Delta ^{-1}\right] \right] \right]
\end{equation}
\begin{equation}
+\xi \frac{i}{\left(4\pi\right)^2} \left[\frac{1}{\epsilon}\left(m-\not p\right) + \left(\not p -m \right)\left(\frac{1}{2}+\gamma_E\right) + \int_0^1 dx\ \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta}{4\pi}\right)-x^2p^2\left((1-x)\not p + m\right)\Delta ^{-1}\right] \right] \nonumber.
\end{equation}
And thus, our full fermionic 1PI propagator is,
\begin{equation}
\Sigma = -\frac{ e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}\left(3m\right)-3m\left(\frac{1}{2}+\gamma_E\right)+\frac{1}{2}\not p + 2\int_0^1 dx\ \left[\left(x\not p -2m\right)\log\left(\frac{\Delta}{4\pi\mu}\right)  - \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta}{4\pi\mu}\right)-x^2p^2\left((1-x)\not p + m\right)\Delta ^{-1}\right] \right] \right]
\end{equation}
\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[\frac{1}{\epsilon}\left(m-\not p\right) + \left(\not p -m \right)\left(\frac{1}{2}+\gamma_E\right) + \int_0^1 dx\ \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta}{4\pi\mu}\right)-x^2p^2\left((1-x)\not p + m\right)\Delta ^{-1}\right] \right] \nonumber.
\end{equation}
We have again used $$e=e'\mu$$ to obtain the correct dimensions in the logarithmic terms. There is, again, more to be said about the divergences with $$\epsilon^{-1}$$, but before that we have one more diagram to calculate. 

## The Three-Point Vertex at One Loop
One more diagram to do. This is the one-loop correction to the three-point vertex. The general three-point interaction can be decomposed into two fermionic two-point interactions and a photonic general propagator, leading to a three-point 1-PI vertex. This vertex, $$\Gamma^\mu(p,p')$$ is a function of the momenta of the incoming particles. We calculate the first-order diagram for $$\Gamma^\mu(p,p')$$ as shown in the following diagram:

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/QED_diagrams/3pt_loop_diagram.png" title="3pt_loop_diagram" class="img-fluid rounded z-depth-0" width="auto" height="270" %}
</div>

Using our Feynman rules as usual, the loop integral is,

\begin{equation}
i e M^\mu = \left(-ie\right)^3 \left [ \int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\gamma^\nu i\left(\not k + \not p' +m \right)\left(-i \eta_{\nu\alpha}\right)\gamma^\mu i\left(\not k + \not p +m \right) \gamma^\alpha u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^2\right)\left(\left(k+p\right)-m^2\right)} \right.
\end{equation}

\begin{equation}
+\left. \int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\gamma^\nu i\left(\not k + \not p' +m \right)\left(i\left(1-\xi\right)k_\alpha k_\nu\right)\gamma^\mu i\left(\not k + \not p +m \right) \gamma^\alpha u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^4\right)\left(\left(k+p\right)-m^2\right)} \right]. \nonumber
\end{equation}

\begin{equation}
= \left(-ie\right)^3 \left[ I + I_\xi\right].
\end{equation}

We once again have an integral without the gauge term, $$I$$, and an integral with the gauge term, $$I_\xi$$. We saved the best for last; these integrals are the nastiest of the bunch. On with the show!

### Gauge-less Integral
Starting with the less terrible integral,
\begin{equation}
I = \int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\gamma^\nu i\left(\not k + \not p' +m \right)\left(-i \eta_{\nu\alpha}\right)\gamma^\mu i\left(\not k + \not p +m \right) \gamma^\alpha u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^2\right)\left(\left(k+p\right)-m^2\right)}.
\end{equation}
Again, with the three-parameter Feynman trick,
\begin{equation}
\frac{1}{abc} =\int_0^1dx\ \int_0^{1-x}dy\ \frac{2}{\left(c+(a-c)x+(b-c)y\right)^3},
\end{equation}
After a bit of algebra, we find we can rewrite the denominator as,
\begin{equation}
\left[\text{Den}\right] = \left(k^2 + \left(2kp'+p'^2-m^2\right)x + \left(2kp+p^2-m^2\right)y \right)^3= \left(\ell^2-\Delta\right)^3,
\end{equation}
\begin{equation}
\ell= k + x p' + y p,\ \Delta = \left( xp'+ yp\right)^2 - x\left(p'^2-m^2\right) - y \left(p^2-m^2\right).
\end{equation}

The integral becomes,
\begin{equation}
I = \int \bar{d}^d ell\  \int_0^1dx\ \int_0^{1-x}dy\ 2\frac{\left[\text{Num}\right]}{\left( \ell^2-\Delta \right)^3 }.
\end{equation}

For the numerator,
\begin{equation}
\left[\text{Num}\right] = i\bar{u}\left(p'\right)\gamma^\nu \left(\not \ell - y \not p + \left(1-x\right)\not p' +m \right)\gamma^\mu \left(\not \ell + \left(1-y\right) \not p -x \not p' +m \right) \gamma_\nu u\left(p\right).
\end{equation}
Our first observation is



### Sources
