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

Back in high school, I would always aspire to fill my notebooks and chalkboards with deranged mathematical scribblings that looked oh so incomprehensible. Unfortunately, as I learned more physics and maths, the incomprehensible became comprehensible and my scribblings never quite reached the heights of insanity to which I aspired, except in Quantum Field Theory (QFT). Even the most organized, well-documented, structured QFT calculation (that these notes certainly are not) looks like a mess, with enough symbols and letters to boggle even the most intrepid physicist.

I am, unfortunately, no longer much of a theoretical physicist. I took three semesters of QFT and decided it was not for me. But there is a beauty in the calculations of QFT, the slow methodical alignment of a maelstrom of algebra and indices. I doubt these notes will serve me much in the future, but I wish to conserve some fraction of what I learned in QFT in a more permanent manner. (You can clearly tell I wrote this **before** embarking on my calculations. I am currently halfway through and am wondering why I ever decided this was a good or reasonable idea).

Here, we will compute the first-order renormalization of the theory of Quantum Electrodynamics (QED). That is to say, we will identify the four counterterms necessary to remove divergences from 1-loop level QED diagrams. This will mostly involve resolving some very nasty-looking integrals, but after doing these calculations once, they can be done a thousand times. I will not present every detail, leaving some things untouched. Otherwise, these notes would quickly spiral into an entire semester's worth of content. There is a lot of algebra here. I spent a long time trying to make sure everything was right, but be warned, I do make mistakes.

Note here that we will only look at the tip of the QFT iceberg. Things become **severely** more complicated at higher orders of loop calculation, and everything I will present is relatively straightforward. For the sake of not complicating things too much, I will not go too too in-depth here, leaving the more sophisticated details to those who are more qualified than me; again, it is very easy to go down rabbit holes when doing these sorts of things.

## Notation and Convention
We use the standard non-dimensionalization setting $$c=\hbar=1$$. We use the mostly negative metric convention,
\begin{equation}
ds^2=\eta^{\mu\nu}x_\mu x_\nu = dt^2-dx^2-dy^2-dz^2,
\end{equation}
apologies if this was not the convention you used in your physics education. None of the ideas change, but the algebra will differ.

We use Gamma matrices, $$\gamma^\mu$$ with $$\mu=0,1,2,3$$ satisfying the anticommutation relation,
\begin{equation}\label{eq: gamma anticommutation relation}
\left\lbrace\gamma^\mu,\gamma^\nu\right\rbrace=\eta^{\mu\nu}.
\end{equation}
Here we have suppressed spinor indices and will continue to do so. Keep in mind that $$\gamma^\mu$$ is a four-by-four matrix in spinor space. 
A useful property that follows from Eq. \ref{eq: gamma anticommutation relation} is,
\begin{equation}
\left(\gamma^\mu\right)^\dagger=\gamma^0\gamma^\mu\gamma^0.
\end{equation}
There are also several properties involving the traces of the gamma matrices,
\begin{equation}
\text{tr}\left[\gamma^\mu\gamma^\nu\right]=4\eta_{\mu\nu},\quad\text{tr}\left[\gamma^\mu\gamma^\nu\gamma^\alpha\gamma^\beta\right]=4\left(\eta_{\mu\nu}\eta_{\alpha\beta}-\eta_{\mu\alpha}\eta_{\nu\beta}+\eta_{\mu\beta}\eta_{\nu\alpha}\right).
\end{equation}
Furthermore, due to anticommutation, the trace of a product of an odd number of gamma matrices is zero. All of these properties are relatively straightforward to derive given the anticommutation result.

A few more properties related to the sums of gamma matrices that can be similarly obtained from the commutation relation,
\begin{equation}
\gamma^\mu\gamma_\mu = d,\quad\gamma^\mu\gamma^\nu\gamma_\nu=\left(2-d\right)\gamma^\nu,
\end{equation}
where $$d$$ is the number of spacetime dimensions. Note that $$d\neq4$$ necessarily.

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
The Lagrangian for QED describing the interactions between a spin-1/2 spinor field $$\psi\left(\mathbf{x}\right)$$ and a gauge field $$A_\mu\left(\mathbf{x}\right)$$ is,
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

Via the **Ward-Takahashi identity**, which is essentially Noether's Theorem applied to path integrals, it can be shown that the two-point photonic propagator satisfies,
\begin{equation}
\frac{i}{\xi}q^2q^\mu D_{\mu\nu}=q_\nu.
\end{equation}
For convenience, denote the tensor and the projector,

\begin{equation}
t_{\mu\nu}=\eta_{\mu\nu}-\left(1-\xi\right)\frac{q_\mu q_\nu}{q^2},\quad t _{T\ \mu\nu}=\eta _{\mu\nu}-\frac{q _\mu q _\nu}{q^2},
\end{equation}

noting that,
\begin{equation}
t^\alpha_{T\ \mu}t_{T\ \alpha\nu}=t_{T\ \mu\nu},\quad t^\alpha_{T\ \mu}t_{\alpha\nu}=t_{T\ \mu\nu},\quad t _{\mu\nu}q^\mu = \xi q _\nu,\quad t _{T\ \mu\nu}q^\mu=0.
\end{equation}
At tree-level, the propagator takes the form,
\begin{equation}
 D^\text{tree} _{\mu\nu}= -\frac{i}{q^2}t _{\mu\nu},
\end{equation}
from which we identify,
\begin{equation}
\frac{i}{\xi}q^2q^\mu D^\text{tree} _{\mu\nu}=q _\nu .
\end{equation}
Therefore, corrections beyond first-order should be proportional to $$t _{T\ \mu\nu}$$ which is orthogonal to $$q^\nu$$. And with this in mind, we write the 1PI diagram for an internal fermion loop as $$i q^2 \Pi\left(q\right) t _{T\ \mu\nu}$$, where $$\Pi\left(q\right)$$ is a function of the momentum to be determined.

Beyond tree level, the general propagator can be written as the sum of 1PI diagrams. First tree level, then tree level followed by 1PI followed by tree level, then tree level, 1PI, tree level, 1PI, tree level, and so forth,
\begin{equation}
 D^{\mu\nu} =  -\frac{i}{q^2}t _{\mu\nu} + \left(-\frac{i}{q^2}t ^{\mu\alpha}\right)\left(i q^2 \Pi t _{T\ \alpha\beta}\right)\left(-\frac{i}{q^2}t ^{\beta\nu}\right)
\end{equation}
\begin{equation}
+\left(-\frac{i}{q^2}t ^{\mu\alpha}\right)\left(i q^2 \Pi t _{T\ \alpha\beta}\right)\left(-\frac{i}{q^2}t ^{\beta\gamma}\right)\left(i q^2 \Pi t _{T\ \gamma\sigma}\right)\left(-\frac{i}{q^2}t _{\sigma\nu}\right) + ...\nonumber
\end{equation}


\begin{equation}
 D^{\mu\nu} =  -\frac{i}{q^2}t _{\mu\nu} -\frac{i}{q^2}\left(\Pi +\Pi^2+...\right) t_T ^{ \mu\nu} .\nonumber
 \end{equation}
 Recalling the solution for a geometric series,
\begin{equation}
 D^{\mu\nu} =  -\frac{i}{q^2}\frac{1}{1 - \Pi}t_T ^{ \mu\nu} - \xi \frac{i}{q^2} \frac{q^\mu q^\nu}{q^2}.
\end{equation}
This is interesting but not instantly helpful. When we renormalize, it will become more relevant.


Finally, we are ready to start integrating to determine the value of $$\Pi\left(q\right)$$. Reading off the Feynman rules from the 1PI 1-loop diagram,
\begin{equation}\label{1pi photon loop integral}
i q^2 \Pi\left(q\right) t _{T\ \mu\nu} = \left(-i e\right)^2(-1)\int\bar{d}^dk\ \frac{\text{tr}\left[\gamma^\mu i\left(\not k+m\right)i\gamma^\nu\left(\not q + \not k +m \right)\right]}{\left(k^2-m^2\right)\left(\left(k+q\right)^2-m^2\right)}.
\end{equation}
I have written the integral in $$d$$ dimensions, which should be $$d=4$$, but we will keep it as $$d$$ for now for reasons that will be evident later. The factor of $$(-1)$$ arises from the presence of a closed Fermion loop, and we take the trace over the closed fermion loop.

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
\begin{equation}\label{eq: Pi one loop}
\Pi= 2\frac{ e'^2}{ 4\pi^2 } \left(-\frac{1}{6}\epsilon^{-1}-\frac{1}{6}\left(\log\left(4\pi\right)-\gamma_E\right)+
\int_0^1 dx\ x\left(1-x\right)\log\left(\frac{m^2-x(1-x)q^2}{\mu^2}\right)\right).
\end{equation}
This resolution may seem a little off the cuff, we will return to these ideas later after assessing all other loop diagrams and formalize the rescalings for $$e$$ and the other scales in the problem.

## The Fermionic Propagator at One Loop
In the same vein as our photonic calculation, we calculate the 1-loop correction for the fermionic two-point propagator $$S(p)$$. Again, the general propagators can be decomposed as a sum of the tree-level diagram and 1PI diagrams. 

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/QED_diagrams/S_fermion_propagator.png" title="S_fermion_propagator" class="img-fluid rounded z-depth-0" width="auto" height="270" %}
</div>

The 1PI diagram we calculate is $$i\Sigma(p)$$. Like the photonic propagator, we can write the general $$S$$ two-point function in terms of a series of the 1PI function $$i\Sigma$$,

\begin{equation}
iS =  \frac{i}{\not p - m} + \left(\frac{i}{\not p - m}\right)\left(i \Sigma\right)\left(\frac{i}{\not p - m}\right) + \left(\frac{i}{\not p - m}\right)\left(i \Sigma\right)\left(\frac{i}{\not p - m}\right)\left(i \Sigma\right)\left(\frac{i}{\not p - m}\right)+...
\end{equation}
This can be simplified by a geometric series,

\begin{equation}
iS =  \frac{i}{\not p - m}\left(1 + \left(i \Sigma\right)\left(\frac{i}{\not p - m}\right) +\left(i \Sigma\right)\left(\frac{i}{\not p - m}\right)\left(i \Sigma\right)\left(\frac{i}{\not p - m}\right)+...\right),
\end{equation}
as,

\begin{equation}
\left(i \Sigma\right)\left(\frac{i}{\not p - m}\right) = -\frac{\Sigma}{\not p - m},
\end{equation}

\begin{equation}
iS =  \frac{i}{\not p - m}\left(1 -\frac{\Sigma}{\not p - m} +\left(-\frac{\Sigma}{\not p - m}\right)^2+...\right).
\end{equation}

Recalling our geometric series,

\begin{equation}
iS =  \frac{i}{\not p - m}\left(\frac{1}{1+\frac{\Sigma}{\not p - m}}\right) = \frac{i}{\not p - m + \Sigma}.
\end{equation}

This is again an interesting result relating the general propagator and the 1PI function which we will employ later.


We perform the calculation in a general gauge. Consulting our Feynman diagram, the loop integral is,

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
\begin{equation}\label{eq: gauegelss lintegral 1}
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
\begin{equation}\label{eq: gauegelss lintegral 2}
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
-\ell^2\left(\left(1+x\right)\not p-m\right) + 2 (1-x)  \not \ell \ell^\mu p_\mu+x^2p^2\left((1-x)\not p + m\right)\right]
\end{equation}
\begin{equation}
 = -\left(1-\xi\right)\left[-\ell^2\left(\left(1+x-\frac{2\left(1-x\right)}{d}\right)\not p-m\right) + x^2p^2\left((1-x)\not p + m\right) \right]. \nonumber
\end{equation}
Evaluating the integrals over $$\ell$$,
\begin{equation}
\int\bar{d}^d\ell\ \frac{1}{\left(\ell^2-\Delta'\right)^3}=-\frac{ i }{ 2\left(4\pi\right)^{2} }\Gamma\left(1+\epsilon\right)\left(\frac{\Delta'}{4\pi}\right)^{-\epsilon}\Delta'^{-1},
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
-x^2p^2\left((1-x)\not p + m\right) \Delta' ^{-1} \Gamma\left(1+\epsilon\right) \left(\frac{\Delta'}{4\pi}\right)^{-\epsilon}  = -x^2p^2\left((1-x)\not p + m\right)\Delta' ^{-1} + ...
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
I + I_\xi = \frac{ i }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}\left(3m\right)-3m\left(\frac{1}{2}+\gamma_E\right)+\frac{1}{2}\not p \right. 
\end{equation}
\begin{equation}
\left.+ 2\int_0^1 dx\ \left[\left(x\not p -2m\right)\log\left(\frac{\Delta}{4\pi}\right)  - \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta'}{4\pi}\right)-\frac{x^2p^2}{\Delta'}\left((1-x)\not p + m\right)\right] \right] \right] \nonumber
\end{equation}

\begin{equation}
+\xi \frac{i}{\left(4\pi\right)^2} \left[\frac{1}{\epsilon}\left(m-\not p\right) + \left(\not p -m \right)\left(\frac{1}{2}+\gamma_E\right)\right. \nonumber
\end{equation}
\begin{equation}
\left. + \int_0^1 dx\ \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta'}{4\pi}\right)-\frac{x^2p^2}{\Delta'}\left((1-x)\not p + m\right) \right] \right] \nonumber.
\end{equation}

And thus, our full fermionic 1PI propagator is,
\begin{equation}
\Sigma = -\frac{ e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}\left(3m\right)-3m\left(\frac{1}{2}+\gamma_E\right)+\frac{1}{2}\not p \right.
\end{equation}
\begin{equation}
\left. + 2\int_0^1 dx\ \left[\left(x\not p -2m\right)\log\left(\frac{\Delta}{4\pi\mu^2}\right)  - \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta'}{4\pi\mu^2}\right)-\frac{x^2p^2}{\Delta'}\left((1-x)\not p + m\right) \right] \right] \right] \nonumber
\end{equation}
\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[\frac{1}{\epsilon}\left(m-\not p\right) + \left(\not p -m \right)\left(\frac{1}{2}+\gamma_E\right) \right. \nonumber
\end{equation}
\begin{equation}
\left. + \int_0^1 dx\ \left(1-x\right)\left[\left(\left(1+3x\right)\not p - 2m\right)\log\left(\frac{\Delta'}{4\pi\mu^2}\right)-\frac{x^2p^2}{\Delta'}\left((1-x)\not p + m\right)\right] \right] \nonumber.
\end{equation}
We have again used $$e=e'\mu$$ to obtain the correct dimensions in the logarithmic terms. There is, again, more to be said about the divergences with $$\epsilon^{-1}$$, but before that we have one more diagram to calculate. Also, keen-eyed readers may have noted that one of the integrals over $$x$$ is not actually convergent. We will discuss more on that a bit later as well.

## The Three-Point Vertex at One Loop
One more diagram to do. This is the one-loop correction to the three-point vertex. The general three-point interaction can be decomposed into two fermionic two-point interactions and a photonic general propagator, leading to a three-point 1-PI vertex. This vertex, $$\Gamma^\mu(p,p')$$ is a function of the momenta of the incoming particles. We calculate the first-order diagram for $$\Gamma^\mu(p,p')$$ as shown in the following diagram:

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/QED_diagrams/3pt_loop_diagram.png" title="3pt_loop_diagram" class="img-fluid rounded z-depth-0" width="auto" height="270" %}
</div>

Using our Feynman rules as usual, the loop integral is,

\begin{equation}
i M^\mu = \left(-ie\right)^3 \left [ \int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\gamma^\nu i\left(\not k + \not p' +m \right)\left(-i \eta_{\nu\alpha}\right)\gamma^\mu i\left(\not k + \not p +m \right) \gamma^\alpha u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^2\right)\left(\left(k+p\right)^2-m^2\right)} \right.
\end{equation}

\begin{equation}
+\left. \int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\gamma^\nu i\left(\not k + \not p' +m \right)\left(i\left(1-\xi\right)k_\alpha k_\nu\right)\gamma^\mu i\left(\not k + \not p +m \right) \gamma^\alpha u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^4\right)\left(\left(k+p\right)^2-m^2\right)} \right]. \nonumber
\end{equation}

\begin{equation}
= i M^\mu_\text{gaugeless} + i M^\mu_\text{gaugefull}.
\end{equation}

We once again have an integral without the gauge term, and one with the gauge term. We saved the best for last; these integrals are the nastiest of the bunch. On with the show!

### Gauge-less Integral
Starting with the less terrible integral,
\begin{equation}
 i M^\mu_\text{gaugeless} = \left(-ie\right)^3  \int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\gamma^\nu i\left(\not k + \not p' +m \right)\left(-i \eta_{\nu\alpha}\right)\gamma^\mu i\left(\not k + \not p +m \right) \gamma^\alpha u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^2\right)\left(\left(k+p\right)^2-m^2\right)}.
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
\ell= k + x p' + y p,\ \Delta = \left( xp'+ yp\right)^2 = m^2\left(x+y\right)^2 -xy q^2.
\end{equation}
Here we have applied the on-shell condition, setting $$p^2=p'^2=m^2$$ to simplify $$\Delta$$, and also used $$q^\mu=p'^\mu-p^\mu$$.

The integral becomes,
\begin{equation}
 i M^\mu_\text{gaugeless} = \left(-ie\right)^3 \int \bar{d}^d \ell\  \int_0^1dx\ \int_0^{1-x}dy\ 2\frac{\left[\text{Num}\right]}{\left( \ell^2-\Delta \right)^3 }.
\end{equation}

For the numerator,
\begin{equation}
\left[\text{Num}\right] = i\bar{u}\left(p'\right)\gamma^\nu \left(\not \ell - y \not p + \left(1-x\right)\not p' +m \right)\gamma^\mu \left(\not \ell + \left(1-y\right) \not p -x \not p' +m \right) \gamma_\nu u\left(p\right).
\end{equation}
Our first observation is to drop terms in odd powers of $$\ell$$,
\begin{equation}
\left[\text{Num}\right] = i\bar{u}\gamma^\nu \left[\not \ell\gamma^\mu\not \ell +\left(\left(1-x\right)\not p' -y \not p + m\right) \gamma^\mu \left(\left(1-y\right)\not p - x\not p' + m \right)\right]\gamma_\nu u.
\end{equation}
The $$\not \ell$$ term is,
\begin{equation}
\gamma^\nu\not \ell\gamma^\mu\not \ell\gamma_\nu = \gamma^\nu\left(-\not\ell^2\gamma^\mu+2\not\ell\ell^\mu\right)\gamma_\nu = \left(d-2\right)\ell^2\gamma^\mu-2\ell^2\gamma^\mu+\frac{4}{d}\ell^2\gamma^2
\end{equation}
\begin{equation}
= \frac{\left(d-2\right)^2}{d}\ell^2\gamma^\mu.\nonumber
\end{equation}

The other non-$$\ell$$ terms are less pleasant. We use the identities, 
\begin{equation}
\bar{u}\not p'=\bar{u}m,\quad \not p u = m u,
\end{equation}
\begin{equation}
\bar{u}\gamma^\nu \left(\left(1-x\right)\not p' -y \not p + m\right) = \bar{u}\left(xm \gamma^\nu + 2\left(1-x\right) p'^\nu - y\gamma^\nu\not p\right),
\end{equation}
\begin{equation}
\left(\left(1-y\right)\not p -x \not p' + m\right)\gamma_\nu u = \left(ym \gamma_\nu + 2\left(1-y\right) p_\nu - x\not p'\gamma_\nu\right) u.
\end{equation}
This is where the fun begins, multiplying out all nine terms,
\begin{equation}
\left[\text{non-}\ell\text{ terms}\right] = \bar{u}\left(xm \gamma^\nu + 2\left(1-x\right) p'^\nu - y\gamma^\nu\not p\right)\gamma^\mu\left(ym \gamma_\nu + 2\left(1-y\right) p_\nu - x\not p'\gamma_\nu\right) u
\end{equation}
\begin{equation}
 = \bar{u}\left[ xy(2-d)m^2\gamma^\mu + 2x(1-y)m\not p \gamma^\mu + 2y(1-x)m\gamma^\mu\not p' - x^2 m \gamma^\nu\gamma^\mu\not p'\gamma_\nu - y^2 m \gamma^\nu \not p \gamma^\mu \gamma_\nu \right. \nonumber
\end{equation}
\begin{equation}
\left.  +4(1-x)(1-y) p'^\nu p_\nu \gamma^\mu - 2x(1-x)\gamma^\mu \not p'^2 -2y(1-y)\not p^2 \gamma^\mu + xy\gamma^\nu\not p\gamma^\mu \not p'\gamma_\nu \right] u \nonumber.
\end{equation}

We must simplify to have terms with only one or no gamma matrices; we omit the outside $$\bar{u}$$ and $$u$$ from the following equations for ease of notation,
\begin{equation}
2x(1-y)m\not p \gamma^\mu = -2x(1-y)m^2\gamma^\mu + 4x(1-y)mp^\mu,
\end{equation}
\begin{equation}
2y(1-x)m\gamma^\mu\not p' = -2y(1-x)m^2\gamma^\mu + 4y(1-x)mp'^\mu,
\end{equation}
\begin{equation}
-x^2 m \gamma^\nu\gamma^\mu\not p'\gamma_\nu = x^2(2-d) m \gamma^\mu \not p' - 2x^2m \not p'\gamma^\mu = -x^2(4-d)m^2 \gamma^\mu + 2x^2(2-d)mp'^\mu,
\end{equation}
\begin{equation}
-y^2 m \gamma^\nu \not p \gamma^\mu \gamma_\nu = -y^2(4-d)m^2 \gamma^\mu + 2y^2(2-d)mp^\mu,
\end{equation}
\begin{equation}
-2x(1-x)\gamma^\mu \not p'^2 = -2x(1-x)m^2\gamma^\mu,
\end{equation}
\begin{equation}
-2y(1-y)\not p^2 \gamma^\mu = -2y(1-y)m^2\gamma^\mu,
\end{equation}
and the fun one,
\begin{equation}
xy\gamma^\nu\not p\gamma^\mu \not p'\gamma_\nu = xy\left(-\not p \gamma^\nu + 2 p^\nu\right)\gamma^mu\left(-\gamma_\nu \not p' + 2p'_\nu\right)
\end{equation}

\begin{equation}
= xy(2-d)\not p \gamma^\mu \not p' + 4xy p'^\nu p _\nu \gamma^\mu - 2xy\left(\not p \not p' \gamma^\mu + \gamma^\mu \not p \not p'\right)  \nonumber
\end{equation}

\begin{equation}
= - xy(4-d)\not p \not p' \gamma^\mu  + 2xy(2-d)m p'^\mu + 4xy p'^\nu p _\nu \gamma^\mu - 2xy \gamma^\mu \not p \not p' \nonumber
\end{equation}

\begin{equation}
= xy(4-d)\not p' \not p \gamma^\mu + 2(d-4) xyp'^\nu p _\nu \gamma^\mu  + 2xy(2-d)m p'^\mu  + 2xy \gamma^\mu \not p' \not p \nonumber
\end{equation}

\begin{equation}
= -xy(6-d) m^2 \gamma^\mu  + 2xy(4-d)m \left(p'^\mu + p^\mu\right) + 2(d-4) xyp'^\nu p _\nu \gamma^\mu  \nonumber
\end{equation}

Now we combine all of these terms.

For $$m^2\gamma^\mu$$,
\begin{equation}
xy(2-d)-2x(1-y)-2y(1-x)-x^2(4-d)-y^2(4-d)-2x(1-x)-2y(1-y)-xy(6-d)
\end{equation}
\begin{equation}
=  -2\left(2\left(x+y\right)-\left(x^2+y^2\right)+\frac{4-d}{2}\left(x^2+y^2\right)\right) \nonumber.
\end{equation}
For $$p'^\nu p _\nu \gamma^\mu$$,
\begin{equation}
4(1-x)(1-y) + 2(d-4) xy = 2\left(2(1-x)(1-y) + (d-4)\right)
\end{equation}
For $$m p'^\mu $$,
\begin{equation}
4y(1-x) + 2y^2(2-d) + 2xy(4-d) = 2\left(\left(2 - d\right)xy + 2y + y^2(2-d)\right).
\end{equation}
For $$m p^\mu $$,
\begin{equation}
4x(1-y) + 2x^2(2-d) + 2xy(4-d) = 2\left(\left(2 - d\right)xy + 2x + x^2(2-d)\right).
\end{equation}

Let's check on our non-$$\ell$$ terms,
\begin{equation}
\left[\text{non-}\ell\text{ terms}\right] = -2\left(2\left(x+y\right)-\left(x^2+y^2\right)+\frac{4-d}{2}\left(x^2+y^2\right)\right)m^2\gamma^\mu
\end{equation}
\begin{equation}
+2\left(2(1-x)(1-y) + (d-4)\right)p'^\nu p _\nu \gamma^\mu + 2\left(\left(2 - d\right)xy + 2y + y^2(2-d)\right)m p'^\mu \nonumber
\end{equation} 
\begin{equation}
+2\left(\left(2 - d\right)xy + 2x + x^2(2-d)\right)m p^\mu \nonumber.
\end{equation} 

We are nearly there, I promise. 

First, we rewrite the momentum terms using $$q=p'-p$$ and $$p'+p$$,
\begin{equation}
 2\left(\left(2 - d\right)xy + 2y + y^2(2-d)\right)m p'^\mu + 2\left(\left(2 - d\right)xy + 2x + x^2(2-d)\right)m p^\mu
\end{equation}
\begin{equation}
= 2(y+x)\left(1+\frac{2-d}{2}\left(y+x\right)\right)m\left(p'^\mu+p^\mu\right) + 2\left(y-x\right)\left(1+\frac{2-d}{2}\left(y+x\right)\right)mq^\mu \nonumber.
\end{equation}
A first simplification: because the $$q^\mu$$ is odd under the exchange $$y\leftrightarrow x$$, it vanishes over the $$x$$, $$y$$ integral. As for the second term, using the **Gordon Identity**,
\begin{equation}
\bar{u}\left(p'\right)\gamma^\mu u\left(p\right) = \frac{1}{2m}\bar{u}\left(p'\right)\left[\left(p' ^\mu + p^\mu\right) + 2i\Sigma^{\mu\nu}q_\nu \right]u\left(p\right) ,
\end{equation}
where,
\begin{equation}
\Sigma^{\mu\nu} = \frac{i}{4}\left\lbrace\gamma^\mu\right\rbrace,
\end{equation}

which can be derived from the Dirac equation; we may replace,
\begin{equation}
p' ^\mu + p^\mu = 2m\gamma^\mu - 2i\Sigma^{\mu\nu}q_\nu.
\end{equation}
The non-$$\ell$$ terms become,
\begin{equation}
\left[\text{non-}\ell\text{ terms}\right] = -2\left(2\left(x+y\right)-\left(x^2+y^2\right)+\frac{4-d}{2}\left(x^2+y^2\right)\right.
\end{equation}
\begin{equation}
\left. -2(x+y)\left(1+\frac{2-d}{2}\left(y+x\right)\right)\right)m^2\gamma^\mu \nonumber
\end{equation}

\begin{equation}
+2\left(2(1-x)(1-y) + (d-4)\right)p'^\nu p _\nu \gamma^\mu - 4i(y+x)\left(1+\frac{2-d}{2}\left(y+x\right)\right)m\Sigma^{\mu\nu}q _\nu\nonumber.
\end{equation}

We can make a very important observation that we should've noticed earlier. The denominator is of the form $$\left(\ell^2-\Delta\right)^3$$ and the numerator has no terms proportional to $$\ell$$. So integrating over $$\ell$$ in four dimensions is actually convergent. Therefore, in these non-$$\ell$$ terms for the numerator, we can safely set $$d=4$$ since any terms proportional to $$\epsilon$$ will vanish when we take the limit of $$\epsilon\rightarrow0$$ and do not contribute to finite terms. 
Setting $$d=4$$,
\begin{equation}
\left[\text{non-}\ell\text{ terms}\right] _{d=4} = -2\left(\left(x+y\right) +2xy - (y+x)\left(1-y-x\right)\right)m^2\gamma^\mu
\end{equation}
\begin{equation}
+4(1-x)(1-y)p'^\nu p _\nu \gamma^\mu - 4i(x+y)\left(1-y-x\right)m\Sigma^{\mu\nu}q _\nu\nonumber.
\end{equation}
And finally, using the on-shell condition,
\begin{equation}
p'^\nu p _\nu = -\frac{q^2}{2}+m^2,
\end{equation}
\begin{equation}
\left[\text{non-}\ell\text{ terms}\right] _{d=4} = -2\left(\left(x+y\right) +2xy - (y+x)\left(1-y-x\right) -2(1-x)(1-y)\right)m^2\gamma^\mu
\end{equation}
\begin{equation}
-2(1-x)(1-y)q^2 \gamma^\mu - 4i(x+y)\left(1-y-x\right)m\Sigma^{\mu\nu}q _\nu\nonumber.
\end{equation}

and the final numerator with both $$\ell$$ and non-$$\ell$$ terms is,
\begin{equation}
\left[\text{Num}\right] = -2i\bar{u}\left[ \left( -\frac{\left(d-2\right)^2 }{2d}\ell^2  + \left(2\left(x+y\right) + (x+y)^2-2\right)m^2 + (1-x)(1-y)q^2 \right) \gamma^\mu \right.
\end{equation}
\begin{equation}
\left. + \frac{2i\Sigma^{\mu\nu}q _\nu}{2m}2m^2(x+y)\left(1-y-x\right) \right]u \nonumber.
\end{equation} 
We identify the two form factors, $$F_1$$ and $$F_2$$,
\begin{equation}
\left[\text{Num}\right] = -2i\bar{u}\left[ \left[F_1\text{ term}\right]\gamma^\mu + \left[F_2\text{ term}\right]\frac{2i\Sigma^{\mu\nu}q _\nu}{2m}\right].
\end{equation}
$$F_1$$ is proportional to $$\gamma^\mu$$ and represents a modification to the tree-level charge $$e$$ due to the interaction loop, and $$F_2$$ is associated with the electron's spin, pairing the spin with the electromagnetic field. Computing the full 3-point vertex without the gauge terms,

\begin{equation}
i M^\mu_\text{gaugeless} = -i e \bar{u} \left[ F_1^\text{gaugeless}\gamma^\mu + F_2^\text{gaugeless}\frac{2i\Sigma^{\mu\nu}q _\nu}{2m} \right] u,
\end{equation}
\begin{equation}
F_1^\text{gaugeless} = 4ie^2 \int \bar{d}^d \ell\  \int_0^1dx\ \int_0^{1-x}dy\ \frac{\left[F_1\text{ term}\right]}{\left( \ell^2-\Delta \right)^3 },
\end{equation}
\begin{equation}
F_2^\text{gaugeless} = 4ie^2 \int \bar{d}^d \ell\  \int_0^1dx\ \int_0^{1-x}dy\ \frac{\left[F_2\text{ term}\right]}{\left( \ell^2-\Delta \right)^3 }.
\end{equation}

Now we evaluate the $$\ell$$ integrals with the usual $$d$$-dimensional integration tricks. Beginning with the non-divergent $$F_2$$ integral,
\begin{equation}
F_2^\text{gaugeless} = 2ie^2 \frac{-i}{\left(4\pi\right)^2 }\int_0^1dx\ \int_0^{1-x}dy\ \frac{2m^2(x+y)\left(1-y-x\right)} {m^2\left(x+y\right)^2 -xy q^2} = \frac{2e^2}{\left(4\pi\right)^2 }\int_0^1dz\  \frac{1} {1+z(z-1)\hat{q}^2}.
\end{equation}
where $$\hat{q}^2=q^2/m^2$$. We have partially evaluated the integral over $$x$$ and $$y$$, performing a change of variables to write the integral in a  cleaner form. Note that in the limit of $$q^2\rightarrow0$$, 
\begin{equation}
F_2(0) = \frac{2e^2}{\left(4\pi\right)^2 }.
\end{equation}
This is the first-order loop correction to the electron's magnetic moment, and one of the most well-verified experimental predictions of QED. We will see shortly that this holds independently of the gauge parameter as well. Had I performed this calculation eighty years ago, it would be worth a Nobel Prize!

Now for $$F_1$$,
\begin{equation}
F_1^\text{gaugeless} = 4ie^2 \int \bar{d}^d \ell\  \int_0^1dx\ \int_0^{1-x}dy\ \frac{ -\frac{\left(d-2\right)^2 }{2d}\ell^2  + \left(2\left(x+y\right) + (x+y)^2-2 \right)m^2 + (1-x)(1-y)q^2 }{\left( \ell^2-\Delta \right)^3 }
\end{equation}
\begin{equation}
 = -4ie^2 \frac{i}{4\left(4\pi\right)^{d/2}}\int_0^1dx\ \int_0^{1-x}dy\ \left[ \frac{d\left(d-2\right)^2 }{2d}\Gamma\left(2-d/2\right)\Delta^{d/2-2} + 2\frac{\left(2\left(x+y\right) + (x+y)^2-2\right)m^2 + (1-x)(1-y)q^2}{m^2\left(x+y\right)^2 -xy q^2} \right] \nonumber
\end{equation}
\begin{equation}
 = \frac{ e^2 }{ \left(4\pi\right)^2 }\int_0^1dx\ \int_0^{1-x}dy\ \left[ 2\left(1-\epsilon\right)^2 \Gamma\left(\epsilon\right)\left(\frac{\Delta}{4\pi}\right)^{-\epsilon} + 2\frac{\left(2\left(x+y\right) + (x+y)^2-2\right)m^2 + (1-x)(1-y)q^2}{ m^2\left(x+y\right)^2 -xy q^2 } \right]. \nonumber
\end{equation}

Beginning with the $$\ell^2$$ term,
\begin{equation}
 \frac{ e^2}{\left(4\pi\right)^{2}}\int_0^1dx\ \int_0^{1-x}dy\ 2\left(1-\epsilon\right)^2 \Gamma\left(\epsilon\right)\left(\frac{\Delta}{4\pi}\right)^{-\epsilon}
\end{equation}
\begin{equation}
 = \frac{2e'}{\left(4\pi\right)^{2}}\int_0^1dx\ \int_0^{1-x}dy\ \left[\frac{1}{\epsilon} - \gamma_E - 2 -\log\left(\frac{m^2\left(x+y\right)^2 -xy q^2}{4\pi\mu}\right)\right]  \nonumber
\end{equation}
\begin{equation}
= \frac{ e'^2}{\left(4\pi\right)^{2}}\left[\frac{1}{\epsilon} - \gamma_E - 2 - 2\int_0^1dx\ \int_0^{1-x}dy\ \log\left(\frac{m^2\left(x+y\right)^2 -xy q^2}{4\pi\mu}\right) \right]. \nonumber
\end{equation}
There is a divergent and a finite contribution. For the non-$$\ell$$ term, there is only the integral,
\begin{equation}
 = \frac{ 2 e^2 }{ \left(4\pi\right)^2 }\int_0^1dx\ \int_0^{1-x}dy\ \frac{\left(2\left(x+y\right) + (x+y)^2-2\right)m^2 + (1-x)(1-y)q^2}{ m^2\left(x+y\right)^2 -xy q^2 } . 
\end{equation}
This integral is not always convergent, but we will address that a little later. For the moment, we are satisfied that it does not diverge as $$d\rightarrow4$$. We have completed all of the Gauge-less integrals.


### Gauge-full Integral
Now for the less pleasant integral,
\begin{equation}
 i M^\mu_\text{gauge} = \left(-ie\right)^3  \int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\gamma^\nu i\left(\not k + \not p' +m \right)\left(i \left(1-\xi\right)k_\alpha k_\nu\right)\gamma^\mu i\left(\not k + \not p +m \right) \gamma^\alpha u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^4\right)\left(\left(k+p\right)^2-m^2\right)}
\end{equation}
\begin{equation}
= \left(-ie\right)^3  \left(-i \left(1-\xi\right)\right)\int \bar{d}^d k\ \frac{\bar{u}\left(p'\right)\not k \left(\not k + \not p' +m \right)\gamma^\mu \left(\not k + \not p +m \right) \not k u\left(p\right)}{\left(\left(k+p'\right)^2-m^2\right)\left(k^4\right)\left(\left(k+p\right)^2-m^2\right)}. \nonumber
\end{equation}

Now with the $$n$$-paramter Feynman trick,
\begin{equation}
\frac{1}{a_1a_2,...a_n} =\Gamma\left(n\right)\int_0^1dx_1\ \int_0^1dx_2\ ... \int_0^1dx_n\ \frac{\delta\left(1-u_1-u_2-...u_n\right)}{\left(a_1u_1+a_2u_2+...a_n u_n\right)^n},
\end{equation}
The denominator is actually identical to our previous one with an extra power,
\begin{equation}
\left[\text{Den}\right] = \left(\ell^2-\Delta\right)^4,
\end{equation}
\begin{equation}
\ell= k + x p' + y p,\ \Delta = \left( xp'+ yp\right)^2 = m^2\left(x+y\right)^2 -xy q^2.
\end{equation}

The integral becomes,
\begin{equation}
 i M^\mu_\text{gauge} = \left(-ie\right)^3  \left(-6i \left(1-\xi\right)\right) \int \bar{d}^d \ell\  \int_0^1dxdydzdw\ \delta\left(1-x-y-w-z\right)\frac{\left[\text{Num}\right]}{\left( \ell^2-\Delta \right)^4}
\end{equation}
\begin{equation}
= \left(-ie\right)^3  \left(-6i \left(1-\xi\right)\right) \int \bar{d}^d \ell\  \int_0^1dx\ \int_0^{1-x}dy\ \left(1-x-y\right)\frac{\left[\text{Num}\right]}{\left( \ell^2-\Delta \right)^4}\nonumber.
\end{equation}

Again, starting with the numerator,
\begin{equation}
\left[\text{Num}\right] = \bar{u}\not k \left(\not k + \not p' +m \right)\gamma^\mu \left(\not k + \not p +m \right) \not k u
\end{equation}
\begin{equation}
= \bar{u}\left(\not \ell - x\not p' - y\not p \right) \left(\not \ell +\left(1-x\right) \not p' -y \not p +m \right)\gamma^\mu \left(\not\ell + \left(1-y\right)\not p -x\not p' +m \right)\left(\not \ell - x\not p' - y\not p \right) u\nonumber.
\end{equation}
Here I wave my white flag. I will not be doing the full Dirac algebra for this numerator. A back-of-the-envelope calculation tells you there are $$74$$ terms that have even powers of $$\ell$$, and each of those terms will generically split into a few more as we compute the gamma matrix commutators. 

Fortunately, we don't actually need to do all the algebra. In fact, we haven't had to do so much math as we have been doing throughout this entire noteset. Well, not really. If we are interested in both the divergent **and** the finite portions of the loop integrals as we have been, it is necessary to fully calculate the numerator Dirac algebra. But, as we have already seen, it is only the high powers of $$\ell$$ that contribute to the divergent portions of the integral. In this case, since the denominator goes with $$\ell^8$$, only terms in the numerator proportional to $$\ell^4$$ will result in divergences. For this gauge term, we only calculate this divergence and ignore the finite contribution. Later, we will say more about why we ignore these contributions in the greater context of renormalizability, but for now, let's worry about the divergent term.
\begin{equation}
\left[\text{Num}\right]_\text{divergent} = \bar{u}\not \ell \not \ell \gamma^\mu \not \ell \not \ell u = \ell^4 \bar{u}\gamma^\mu u.
\end{equation}
We see the divergent gauge contribution is added to $$F_1$$,

\begin{equation}
F_{1\ \text{divergent}}^\text{gauge} = 6i\left(e\right)^2\left(1-\xi\right)\int \bar{d}^d \ell\  \int_0^1dx\ \int_0^{1-x}dy\ \left(1-x-y\right)\frac{\ell^4}{\left( \ell^2-\Delta \right)^4}.
\end{equation}

The general integral over $$\ell$$ follows from the same computations we did previously,
\begin{equation}
\int \bar{d}^d \ell\  \frac{\left(\ell^2 \right)^\alpha}{\left( \ell^2-\Delta \right)^\beta} = \frac{i\left(-1\right)^{\alpha-\beta }}{\left(4\pi\right)^{d/2}}\frac{\Gamma\left(d/2+\alpha\right)}{\Gamma\left(d/2\right)}\frac{\Gamma\left(\beta-\alpha-d/2\right)}{\Gamma\left(\beta\right)}\Delta^{d/2+\alpha-\beta}.
\end{equation}
From this, it is much more evident that a divergence exists when $$d/2+\alpha-\beta=0$$, meaning in the case of $$\beta=4$$, $$\alpha=2$$ is the divergence-causing term. We can directly compute $$F_{1\ \text{divergent}}^\text{gauge}$$,
\begin{equation}
F_{1\ \text{divergent}}^\text{gauge} = -\left(e\right)^2\left(1-\xi\right) \frac{1}{\left(4\pi\right)^{d/2}}\frac{\Gamma\left(d/2+2\right)}{\Gamma\left(d/2\right)}\Gamma\left(2-d/2\right)\int_0^1dx\ \int_0^{1-x}dy\ \left(1-x-y\right) \Delta^{d/2-2}
\end{equation}
\begin{equation}
 = -\left(e\right)^2\left(1-\xi\right) \frac{1}{\left(4\pi\right)^{d/2}}\frac{d}{2}\left(\frac{d}{2}+1\right)\Gamma\left(\epsilon\right)\int_0^1dx\ \int_0^{1-x}dy\ \left(1-x-y\right) \left(\frac{\Delta}{4\pi}\right)^{-\epsilon}
\end{equation}
\begin{equation}
 = -\left(e\right)^2\left(1-\xi\right) \frac{1}{\left(4\pi\right)^{2}}\frac{1}{\epsilon}.
\end{equation}
This is the divergent portion, and notice that the $$\epsilon^{-1}$$ terms not proportional to $$\xi$$ actually vanish!,
\begin{equation}
F_1 = \frac{ e'^2}{\left(4\pi\right)^{2}}\left[ \xi \frac{1}{\epsilon} - \gamma_E - 2 - 2\int_0^1dx\ \int_0^{1-x}dy\ \log\left(\frac{m^2\left(x+y\right)^2 -xy q^2}{4\pi\mu}\right) \right.
\end{equation}
\begin{equation}
+2\int_0^1dx\ \int_0^{1-x}dy\ \frac{ \left( \left(x+y\right) +2(x+y)^2-2(1+xy) \right)m^2 + (1-x)(1-y)q^2 }{ m^2\left(x+y\right)^2 -xy q^2 } \nonumber
\end{equation}
\begin{equation}
\left. +\left(1-\xi\right)\left[\text{term of } \mathcal{O}\left(\epsilon^0\right)\right] \right]. \nonumber
\end{equation}

We can also show that there are no gauge contributions to $$F_2$$. Return to the numerator, and define $$w_1=k+p'$$ and $$w_2=k+p$$,
\begin{equation}
\left[\text{Num}\right] = \bar{u}\left(\not w_1 -\not p'\right) \left(\not w_1 +m \right)\gamma^\mu \left(\not w_2 +m \right) \left(\not w_2 - \not p\right) u.
\end{equation}
Walking $$\not p'$$ and $$\not p$$ into $$\bar{u}$$ and $$u$$,
\begin{equation}
\left[\text{Num}\right] = \bar{u}\left(\not w_1 -m\right) \left(\not w_1 +m \right)\gamma^\mu \left(\not w_2 +m \right) \left(\not w_2 - m\right) u = \bar{u} \left(w_1 -m^2\right)^2 \gamma^\mu \left( w_2 - m^2 \right)^2 u.
\end{equation}
so, the gauge contribution is purely proportional to $$\gamma^\mu$$, and $$F_2^\text{gauge}=0$$, resulting in,
\begin{equation}
F_2 = \frac{2e^2}{\left(4\pi\right)^2 }\int_0^1dz\  \frac{1} {1+z(z-1)\hat{q}^2}.
\end{equation}

We have finished all of our integrals! Stand up, stretch, go outside. The hard part is behind us, now we just go through the renormalization procedure.

## Renormalization
Taking a step back and returning to our QED Lagrangian, Eq. \ref{eq: QED Lagrangian},
\begin{equation}
\mathcal{L} _\text{QED}=\bar{\psi}_0\left(i\not \partial-e _0\not A _0-m_0\right)\psi_0-\frac{1}{4}F_0^{\mu\nu}F _{0\ \mu\nu}-\frac{1}{2\xi _0}\left(\partial _\mu A _0 ^\mu\right)^2.
\end{equation}
We have added a $$0$$ indicator to all of our bare fields. The idea of renormalization is to express these bare quantities in terms of renormalized fields and physical parameters together with multiplicative renormalization constants. The divergences arising in loop calculations are absorbed into these constants, leaving finite predictions for physical observables.

\begin{equation}
\psi_0=Z^{1/2}_\psi\psi,\quad m_0=Z_m m,\quad A_0^\mu = Z_A^{1/2}A^\mu,\quad e_0=Z_e e, \quad \xi_0=Z_A\xi.
\end{equation}
For the gauge parameter $$\xi$$, we may choose any coupling we desire, and it is more convenient to pick $$Z^A$$. We also raise some couplings to the half power for convenience. 

The renormalization constants are determined order by order in perturbation theory and admit an expansion in powers of the coupling,
\begin{equation}
Z_i = 1+\delta_i,
\end{equation}
where the constants $$\delta_i$$ begin at one-loop order. These terms invoke a split Lagrangian, into one built from the counterterms $$\delta_i$$ and one with the renormalized fields. Replacing the bare terms with renormalized terms, 
\begin{equation}
\mathcal{L} _\text{QED}= Z _\psi \bar{\psi} i\not \partial \psi - Z _\psi Z _m m \bar{\psi}\psi - Z _\psi Z_A^{1/2}Z _e e \bar{\psi} \not A \psi - \frac{1}{4} Z_A F^{\mu\nu}F _{\mu\nu} -\frac{1}{2\xi }\left(\partial _\mu A  ^\mu\right)^2,
\end{equation}
and expanding to first order in $$\delta_i$$, since higher orders of $$\delta_i$$ correspond to higher-order loop corrections,
\begin{equation}
\mathcal{L} _\text{QED}= \mathcal{L} _\text{QED}^\text{renormalized} + \mathcal{L} _\text{QED}^\text{counter},
\end{equation}
\begin{equation}
\mathcal{L} _\text{QED}^\text{renormalized} = \bar{\psi}\left(i\not \partial-e \not A -m\right)\psi-\frac{1}{4}F^{\mu\nu}F _{\mu\nu}-\frac{1}{2\xi }\left(\partial _\mu A ^\mu\right)^2
\end{equation}
\begin{equation}
\mathcal{L} _\text{QED}^\text{counter} = \delta _\psi \bar{\psi} i\not \partial \psi - \left(\delta _\psi + \delta _m\right)m \bar{\psi}\psi - \delta_1 e \bar{\psi} \not A \psi - \frac{1}{4} \delta_A F^{\mu\nu}F _{\mu\nu},
\end{equation}
we have defined,
\begin{equation}
\delta_1 = \delta _\psi + \frac{1}{2}\delta_A + \delta_e.
\end{equation}

Each term in the counter Lagrangian modifies the corresponding propagator. Writing general propagators and vertices in terms of bare and counterterms,

\begin{equation}
D _{\mu\nu}^\text{bare}=D _{\mu\nu}(q)^\text{renormalized} - \frac{i\delta_A}{q^2}t _{T\ \mu\nu} +\left[\text{Higher-Order Coutnerterms}\right],
\end{equation}

\begin{equation}
S^\text{bare}=S^\text{renormalized} +\frac{i}{\not p - m}\left(i \delta_\psi\left(\not p -m\right) -i m\delta _m\right)\frac{i}{\not p - m} +\left[\text{Higher-Order Coutnerterms}\right],
\end{equation}

\begin{equation}
V_\mu^\text{bare}=i S^\text{bare} D_{\mu\nu}^\text{bare} \left(\Gamma^{\nu\ \text{renormalized}} - ie\delta_1\gamma^\nu\right) i S^\text{bare} +\left[\text{Higher-Order Coutnerterms}\right].
\end{equation}

We have all of the vertices and propagators; now we just need to decide how we should determine the values of our counterterms. 

### The On-Shell Scheme
We have four renormalization constants and require four conditions to set these. We use the **On-Shell** renormalization scheme in which the renormalized mass is identified with the physical pole mass of the electron. The fermionic propagator should have a pole when $$p^2=m^2$$, where $$m$$ is the renormalized mass. Using our formulation of the 2pt electron propagator, 
\begin{equation}
iS = \frac{i}{\not p - m + \Sigma},
\end{equation}
 a pole at $$\not p = m$$ requires,
\begin{equation}
\Sigma^\text{renormalized}\left(\not p=m\right)=0.
\end{equation}
Because the residue of $$S$$ should approach unity as $$p\rightarrow m$$, we also require,
\begin{equation}
\left.\frac{d\Sigma^\text{renormalized}}{d\not p}\right|_{\not p=m}=0.
\end{equation}

We also require that the photon remain massless; at a photon energy of $$q^2=0$$, the photonic propagator should have a pole with unit residue. Using the two-point photonic propagator,
\begin{equation}
D^{\mu\nu}=-\frac{i}{q^2}\frac{1}{1-\Pi}t^{\mu\nu}_T-\xi\frac{i}{q^2}\frac{q^\mu q^\nu}{q^2},
\end{equation}
the propagator already has a pole at $$q^2=0$$. Requiring a unit residue results in,
\begin{equation}
\Pi^\text{renormalized}\left(q^2=0\right)=0.
\end{equation}

Our final condition comes from the Ward Identity. Via the Schwinger-Dyson equation, it can be shown that,
\begin{equation}
\frac{i}{\xi}q^2q^\mu V_\mu\left(p,p'\right) = ie\left(S\left(p\right)-S\left(p'\right)\right).
\end{equation}
This looks odd, but is just a result of applying Noether's Theorem to the path integral again, nothing too bad. Using our other Ward-Takahashi Identity, $$\frac{i}{\xi}q^2q^\mu D_{\mu \nu}=q_\nu$$,
\begin{equation}
\frac{i}{\xi}q^2q^\mu V_\mu\left(p,p'\right) = -\frac{i}{\xi}q^2q^\mu S\left(p'\right) D_{\mu\nu}\left(q\right)\Gamma^\nu\left(p,p'\right)S\left(p\right) = -q_\nu S\left(p'\right) \Gamma^\nu\left(p,p'\right)S\left(p\right),
\end{equation}
and,
\begin{equation}
 q_\nu \Gamma^\nu\left(p,p'\right) = -ie\left(S^{-1}\left(p'\right)-S^{-1}\left(p\right)\right).
\end{equation}
This is the Ward Identity. In the limit of $$p\rightarrow0$$, $$p'\rightarrow0$$,
\begin{equation}
\Gamma^{\nu\ \text{bare}}\left(p,p\right) = -ie\frac{d\left(S^\text{bare}\right)^{-1}\left(p\right)}{d p_\nu} = -i e\gamma^\mu\left(1 + \frac{d\Sigma^\text{bare}}{d\not p}\right),
\end{equation}
\begin{equation}
\Gamma^{\nu\ \text{renormalized}}\left(p,p\right) = -ie\frac{d\left(S^\text{bare}\right)^{-1}\left(p\right)}{d p_\nu} = -i e\gamma^\mu\left(1 + \frac{d\Sigma^\text{renormalized}}{d\not p}\right).
\end{equation}

This fixes the value of the three-point vertex. Note that the identity applies to both the bare and renormalized operators since it is a general statement arising from our path integral, not a physical condition imposed by the on-shell scheme.

We have all our conditions for our renormalized propagators; we just need to compare the lengthy integrals we calculated with our counters and use the four conditions to assign values to each $$\delta_i$$. 

## Assigning Counterterms and Renormalization

### Photonic Counter
Starting with the photon. Recalling the bare term to first loop order,
\begin{equation}
\Pi^\text{bare}\left( q^2 \right) = \Pi^\text{renormalized}\left( q^2 \right) + \delta_A.
\end{equation}
We already found the one-loop integral in terms of bare parameters, Eq. \ref{eq: Pi one loop},
\begin{equation}
\Pi^\text{bare}\left( 0 \right) = 2\frac{ e_0'^2}{ 4\pi^2 } \left(-\frac{1}{6}\epsilon^{-1}-\frac{1}{6}\left(\log\left(4\pi\right)-\gamma_E\right)+
\int_0^1 dx\ x\left(1-x\right)\log\left(\frac{m^2}{\mu^2}\right)\right)
\end{equation}
\begin{equation}
 = -\frac{ e'^2}{ 12\pi^2 } \left( \epsilon^{-1} -\gamma_E+\log\left(\frac{4\pi \mu^2 }{m^2}\right) \right). \nonumber
\end{equation}

Because we are working at first loop order, we are free to substitute $$e_0\rightarrow e$$ here. We identify $$\delta_A$$ necessary to set $$\Pi^\text{renormalized}\left(0\right)=0$$ at first loop order,
\begin{equation}
\delta_A = -\frac{ e'^2}{ 12\pi^2 } \left( \epsilon^{-1} -\gamma_E+\log\left(\frac{4\pi \mu^2 }{m^2}\right) \right).
\end{equation}
The next term contributes at order $$e^4$$.

### Fermionic Counter
Now for the fermion. To first loop order, the bare term reads,
\begin{equation}
\Sigma^\text{bare} = \Sigma^\text{renormalized} + \left(\delta_\psi\left(\not p - m\right) - m\delta _m\right).
\end{equation}
We already know the two-point fermion loop integral. And, again since we are first order, we may replace the bare $$e_0\rightarrow e$$ and $$m_0\rightarrow m$$,
\begin{equation}
\Sigma^\text{bare}\left(\not p = m\right) = -\frac{ e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}\left(3m\right)-3m\left(\frac{1}{2}+\gamma_E\right)+\frac{1}{2}m \right.
\end{equation}
\begin{equation}
\left. + 2\int_0^1 dx\ \left[m\left(x -2\right)\log\left(\frac{\Delta}{4\pi\mu^2}\right)  - \left(1-x\right)\left[m\left(-1+3x\right) \log\left(\frac{\Delta'}{4\pi\mu^2}\right)-x^2m^3\left(2-x\right)\Delta' ^{-1}\right] \right] \right] \nonumber
\end{equation}
\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[ \int_0^1 dx\ \left(1-x\right)\left[m\left(-1+3x\right)\log\left(\frac{\Delta'}{4\pi\mu^2}\right)-x^2m^3\left(2-x\right)\Delta' ^{-1}\right] \right] \nonumber.
\end{equation}
Inserting,
\begin{equation}
\Delta\left(p=m\right) = m^2\left(1-x\right)^2,\quad \Delta'\left(p=m\right) = m^2x\left(1-x\left(1-x\right)\right),
\end{equation}
we calculate $$\Sigma$$ at $$\not p =m$$,
\begin{equation}
\Sigma^\text{bare}\left(\not p = m\right) = -\frac{ e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}\left(3m\right)-3m\left(\frac{1}{2}+\gamma_E\right)+\frac{1}{2}m \right.
\end{equation}
\begin{equation}
+2\int_0^1 dx\ \left[m\left(x -2\right)\log\left(\frac{m^2\left(1-x\right)^2}{4\pi\mu^2}\right) \right]
\end{equation}
\begin{equation}
\left. - 2\int_0^1 dx\ \left[ \left(1-x\right)\left[m\left(-1+3x\right) \log\left(\frac{m^2x\left(1-x\left(1-x\right)\right)}{4\pi\mu^2}\right)-m\frac{x\left(2-x\right)}{\left(1-x\left(1-x\right)\right)}\right] \right] \right] \nonumber
\end{equation}
\begin{equation}
\left. + 2\int_0^1 dx\ \left[m\left(x -2\right)\log\left(\frac{m^2\left(1-x\right)^2}{4\pi\mu^2}\right)  - \left(1-x\right)\left[m\left(-1+3x\right) \log\left(\frac{m^2x\left(1-x\left(1-x\right)\right)}{4\pi\mu^2}\right)-m\frac{x\left(2-x\right)}{\left(1-x\left(1-x\right)\right)}\right] \right] \right] \nonumber
\end{equation}


\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[ \int_0^1 dx\ \left(1-x\right)\left[m\left(-1+3x\right)\log\left(\frac{m^2x\left(1-x\left(1-x\right)\right)}{4\pi\mu^2}\right)-m\frac{x\left(2-x\right)}{\left(1-x\left(1-x\right)\right)}\right] \right] \nonumber.
\end{equation}

We evaluate the finite integrals over $$x$$, 
\begin{equation}
\int_0^1 dx\ \left(x -2\right)\log\left(\left(1-x\right)^2\right) = \frac{5}{2},
\end{equation}
\begin{equation}
\int_0^1 dx\ \left(1-x\right)\left(-1+3x\right) \log\left(x\left(1-x\left(1-x\right)\right)\right) = \frac{\pi}{\sqrt{3}}-\frac{3}{2},
\end{equation}
\begin{equation}
\int_0^1 dx\ \frac{x\left(1-x\right)\left(2-x\right)}{\left(1-x\left(1-x\right)\right)} = \frac{\pi}{\sqrt{3}}-\frac{3}{2}.
\end{equation}
This is interesting: the two integrals of the gauge term are equivalent. Now we simplify the expression for $$\Sigma^\text{bare}\left(\not p = m\right)$$,
\begin{equation}
\Sigma^\text{bare}\left(\not p = m\right) = -\frac{ e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}\left(3m\right)-3m\left(\frac{1}{2}+\gamma_E\right)+\frac{1}{2}m + 2\left(\frac{5}{2}m-\frac{3}{2}m\log\left(\frac{m^2}{4\pi\mu^2}\right)\right) \right],
\end{equation}
and the gauge term entirely drops. The only remaining contributions are gauge-independent! This is expected since our choice of gauge should not influence our renormalization procedure. The gauge parameter has no influence on the pole location, so it should not influence the result of $$\delta_m$$. We obtain,
\begin{equation}
\Sigma^\text{bare}\left(\not p = m\right) = -\frac{ 3 m e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}-\gamma_E+\frac{4}{3} + \log\left(\frac{4\pi\mu^2}{m^2}\right) \right] \nonumber.
\end{equation}
Using,
\begin{equation}
\Sigma^\text{bare}\left(\not p = m\right) = \Sigma^\text{renormalized}\left(\not p = m\right) - m\delta _m,
\end{equation}
we identify $$\delta_m$$,
\begin{equation}
\delta_m = \frac{ 3 e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{\epsilon}-\gamma_E+\frac{4}{3} + \log\left(\frac{4\pi\mu^2}{m^2}\right) \right].
\end{equation}

Now for $$\delta_\psi$$, this requires the derivative of $$\Sigma$$ with respect to $$\not p$$. Using
\begin{equation}
\left.\frac{\Delta}{d\not p}\right|_{\not p=m} = -2x\left(1-x\right)m,\quad \left.\frac{\Delta'}{d\not p}\right| _{\not p=m} = -2x^2\left(1-x\right)m,
\end{equation}
we calculate $$\left.\frac{d\Sigma}{d\not p}\right| _{\not p=m}$$. Starting with the gaugeless polynomial terms,
\begin{equation}
\left.\frac{d\Sigma}{d\not p}\right| _{\not p=m} = -\frac{ e'^2 }{ \left(4\pi\right)^2 }\left[\frac{1}{2}\right.
\end{equation}
then the gaugeless integral terms,
\begin{equation}
+2\int_0^1 dx\ \left[x \log\left(\frac{m^2\left(1-x\right)^2}{4\pi\mu^2}\right) -2 \frac{x(x-2)}{\left(1-x\right)}\right] \nonumber
\end{equation}
\begin{equation}
- 2\int_0^1 dx\ \left(1-x\right)\left[ \left(1+3x\right)\log\left(\frac{m^2x\left(1-x\left(1-x\right)\right)}{4\pi\mu^2}\right) \nonumber
\end{equation}
\begin{equation}
\left. \left. -2 \frac{ x\left(-1+3x\right) \left(1-x\right)}{\left(1-x\left(1-x\right)\right)} -\frac{x\left(5-3x\right)}{\left(1-x\left(1-x\right)\right)} -2\frac{x^2(2-x)(1-x)}{\left(1-x\left(1-x\right)\right)^2} \right] \right] \nonumber
\end{equation}
and the gauge polynomial terms,
\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[-\frac{1}{\epsilon} \right. \nonumber
\end{equation}
and the gauge integral terms,
\begin{equation}
+ \int_0^1 dx\ \left(1-x\right)\left[ \left(1+3x\right)\log\left(\frac{m^2x\left(1-x\left(1-x\right)\right)}{4\pi\mu^2}\right)  \nonumber
\end{equation}
\begin{equation}
\left. \left. -2 \frac{ x\left(-1+3x\right) \left(1-x\right)}{\left(1-x\left(1-x\right)\right)} -\frac{x\left(5-3x\right)}{\left(1-x\left(1-x\right)\right)} -2\frac{x^2(2-x)(1-x)}{\left(1-x\left(1-x\right)\right)^2} \right] \right]. \nonumber
\end{equation}

Evaluating the $$x$$ integrals,
\begin{equation}
\int_0^1 dx\ x \log\left(\frac{m^2\left(1-x\right)^2}{4\pi\mu^2}\right) = \log\left(\frac{m^2}{4\pi\mu^2}\right) +\frac{3}{2},
\end{equation}
\begin{equation}
\int_0^1 dx\ \left(1-x\right)\left[ \left(1+3x\right)\log\left(\frac{m^2x\left(1-x\left(1-x\right)\right)}{4\pi\mu^2}\right) \right] = \log\left(\frac{m^2}{4\pi\mu^2}\right) +\frac{2\pi}{\sqrt{3}}-5,
\end{equation}
\begin{equation}
\int_0^1 dx\ \left(1-x\right)\left[ -2 \frac{ x\left(-1+3x\right) \left(1-x\right)}{\left(1-x\left(1-x\right)\right)} -\frac{x\left(5-3x\right)}{\left(1-x\left(1-x\right)\right)} -2\frac{x^2(2-x)(1-x)}{\left(1-x\left(1-x\right)\right)^2} \right]
\end{equation}
\begin{equation}
= \frac{-2\sqrt{3}\pi - 9}{2}, \nonumber
\end{equation}
and let,
\begin{equation}
I_{IR} = \int_0^1 dx\ \frac{x(x-2)}{\left(1-x\right)},
\end{equation}

This integral is not convergent as $$x\rightarrow1$$. This is known as an infrared divergence. All of our other divergences so far have resulted from $$\ell\rightarrow\infty$$, the so-called high-energy or ultraviolet limit. But in this case, the problem is on the other end of the spectrum. Returning to the integral that gave rise to $$I_{IR}$$, the problem was in the gaugeless term for the fermionic loop integral, Eq. \ref{eq: gauegelss lintegral 1},
\begin{equation}
I = \int\bar{d}^dk\ \frac{\gamma^\mu i\left(\not k + m\right)\gamma^\nu\left(-i\eta_{\mu\nu}\right)}{\left(k^2-m^2\right)\left(k-p\right)^2} = \frac{ i }{ \left(4\pi\right)^{2} }\Gamma\left(\epsilon\right)\int_0^1 dx\ \left(\left(4-2\epsilon\right)m + (2\epsilon-2) x\not p\right)\left(\frac{\Delta}{4\pi}\right)^{-\epsilon}.
\end{equation}
Previously, we expanded in terms of small $$\epsilon$$ and then took the derivative with respect to $$\not p$$, but to isolate the divergence, we will perform the opposite procedure,
\begin{equation}
i e^2\frac{d}{d\not p}\left(I\right) =- \frac{  e'^2 }{ \left(4\pi\right)^{2} }\Gamma\left(\epsilon\right)\int_0^1 dx\ \left [\left((2\epsilon-2) x\right)\left(\frac{\Delta}{4\pi\mu^2}\right)^{-\epsilon} \right.
\end{equation}
\begin{equation}
\left. +2\left(4\pi\mu^2\right)^{-1}\epsilon\left(\left(4-2\epsilon\right)m + (2\epsilon-2) x\not p\right)\left(\left(1-x\right)x\not p\right)\left(\frac{\Delta}{4\pi\mu^2}\right)^{-1-\epsilon}\right]. \nonumber
\end{equation}
Setting $$\not p = m$$, 
\begin{equation}
i e^2\frac{d}{d\not p}\left(I\right) =- \frac{  e'^2 }{ \left(4\pi\right)^{2} }\Gamma\left(\epsilon\right)\int_0^1 dx\ \left [\left((2\epsilon-2) x\right)\left(\frac{m^2\left(1-x\right)^2}{4\pi\mu^2}\right)^{-\epsilon} \right.
\end{equation}
\begin{equation}
\left. +2\left(4\pi\mu^2\right)^{-1}m^2\epsilon \left(\left(4-2\epsilon\right) + (2\epsilon-2) x\right)\left(\left(1-x\right)x\right)\left(\frac{m^2\left(1-x\right)^2}{4\pi\mu^2}\right)^{-1-\epsilon}\right]. \nonumber
\end{equation}

We recognize the first term as the usual UV divergence as $$\epsilon\rightarrow0$$, the second term converges in this limit, but diverges as we take $$x\rightarrow1$$. We identify this as $$I'_ {IR}$$,
\begin{equation}
i e^2 I'_ {IR} = - \frac{ 2  e'^2 }{ \left(4\pi\right)^{2} }\Gamma\left(\epsilon\right)\int_0^1 dx\  \left(\frac{m^2}{4\pi\mu^2} \right)^{-\epsilon} \epsilon \left(\left(4-2\epsilon\right) + (2\epsilon-2) x\right)x \left( \left(1-x\right) \right)^{-1-2\epsilon}.
\end{equation}
Indeed, if we take $$\epsilon\rightarrow0$$, we see,
\begin{equation}
i e^2 \lim_{\epsilon\rightarrow 0}\left(I'_ {IR}\right) = \frac{ 4 e'^2 }{ \left(4\pi\right)^{2} }\int_0^1 dx\  \frac{x(2-x)}{\left(1-x\right) } = \frac{ 4 e'^2 }{ \left(4\pi\right)^{2} }I_{IR},
\end{equation}
which is the term causing the IR divergence. But if we integrate before taking the limit of small $$\epsilon$$, we obtain,
\begin{equation}
i e^2 I'_ {IR} = - \frac{ 2  e'^2 }{ \left(4\pi\right)^{2} }\left(\frac{m^2}{4\pi\mu^2} \right)^{-\epsilon} \Gamma\left(\epsilon\right)\epsilon \int_0^1 dx\    \left(\left(4-2\epsilon\right) + (2\epsilon-2) x\right)x \left( \left(1-x\right) \right)^{-1-2\epsilon}
\end{equation}
\begin{equation}
= \frac{ 2  e'^2 }{ \left(4\pi\right)^{2} }\left(\frac{m^2}{4\pi\mu^2} \right)^{-\epsilon} \Gamma\left(\epsilon\right)\epsilon \left[\frac{\left(4-2\epsilon\right)\Gamma\left(-2\epsilon\right)}{\Gamma\left(2-2\epsilon\right)} + 2\frac{\left(2-2\epsilon\right)\Gamma\left(-2\epsilon\right)}{\Gamma\left(3-2\epsilon\right)}\right]. \nonumber
\end{equation}
Using the usual Gamma function expansions near $$\epsilon=0$$, to finite order,
\begin{equation}
i e^2 I'_ {IR} = - \frac{ 2  e'^2 }{ \left(4\pi\right)^{2} } \left[ \frac{1}{\epsilon_{\text{IR}}} + 1 +3\gamma_E- \log\left(\frac{m^2}{4\pi\mu^2}\right) \right].
\end{equation}
We have notated $$\epsilon_{\text{IR}}$$ to specify that this term arises from an $$IR$$, not a $$UV$$ divergence. Having isolated this divergence, we may construct the full term,
\begin{equation}
\left.\frac{d\Sigma}{d\not p}\right| _{\not p=m} = -\frac{ e'^2 }{ \left(4\pi\right)^2 }\left[ \frac{1}{2} +2\log\left(\frac{m^2}{4\pi\mu^2}\right) +3 + 2\left( \frac{1}{\epsilon _{\text{IR}}} + 1 + 3\gamma_E- \log\left(\frac{m^2}{4\pi\mu^2}\right)\right) \right.
\end{equation}
\begin{equation}
\left. - 2\left[\log\left(\frac{m^2}{4\pi\mu^2}\right) - \frac{\pi}{\sqrt{3}} -\frac{1}{2}\right] \right] \nonumber
\end{equation}
\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[-\frac{1}{\epsilon} + \log\left(\frac{m^2}{4\pi\mu^2}\right) - \frac{\pi}{\sqrt{3}} -\frac{1}{2}\right] . \nonumber
\end{equation}

which reduces to,
\begin{equation}
\left. \frac{d\Sigma}{d\not p}\right| _{\not p=m} = -\frac{ 2 e'^2 }{ \left(4\pi\right)^2 }\left[ \frac{1}{\epsilon _{\text{IR}}} + \frac{11}{4} - \frac{\pi}{\sqrt{3}} + 3\gamma_E- \log\left(\frac{m^2}{4\pi\mu^2}\right) \right]
\end{equation}
\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[ -\frac{1}{\epsilon}  + \log\left(\frac{m^2}{4\pi\mu^2}\right) - \frac{\pi}{\sqrt{3}} -\frac{1}{2} \right]. \nonumber
\end{equation}

From this, we identify the value of $$\delta _\psi$$,
\begin{equation}
\delta _\psi = -\frac{ 2 e'^2 }{ \left(4\pi\right)^2 }\left[ \frac{1}{\epsilon _{\text{IR}}} + \frac{11}{4} - \frac{\pi}{\sqrt{3}} + 3\gamma_E- \log\left(\frac{m^2}{4\pi\mu^2}\right) \right]
\end{equation}
\begin{equation}
-\xi \frac{e'^2 }{\left(4\pi\right)^2} \left[ -\frac{1}{\epsilon}  + \log\left(\frac{m^2}{4\pi\mu^2}\right) - \frac{\pi}{\sqrt{3}} -\frac{1}{2} \right]. \nonumber
\end{equation}

### Vertex Counter
And finally, our last quantity to compute is the three-point vertex, with the condition
\begin{equation}
\Gamma^{\nu\ \text{bare}}\left(p,p\right) = -ie\frac{d\left(S^\text{bare}\right)^{-1}\left(p\right)}{d p_\nu} = -i e\gamma^\mu\left(1 + \frac{d\Sigma^\text{bare}}{d\not p}\right).
\end{equation}
Using the relationship between the bare and renormalized couplings,
\begin{equation}
\Gamma^{\mu\ \text{bare}} = \Gamma^{\mu\ \text{renormalized}} - i e\delta_1\gamma^\mu = -i e\gamma^\mu\left(1 + \frac{d\Sigma^\text{renormalized}}{d\not p} + \delta_\psi\right),
\end{equation}
and using the Ward condition in the renormalized fields, we find,
\begin{equation}
\delta_1 = \delta_\psi\rightarrow \delta_e = -\frac{1}{2}\delta_A = \frac{ e'^2}{ 24\pi^2 } \left( \epsilon^{-1} -\gamma_E+\log\left(\frac{4\pi \mu^2 }{m^2}\right) \right).
\end{equation}
We have set the value of our final counterterm.

Now, we should be good physicists and verify that this counterterm does actually remove the divergence from our vertex loop diagram. We already identified all the divergent terms in the loop diagram, and these should be canceled by the $$\delta_1$$ counterterm.

From our loop integral for the vertex term,
\begin{equation}
\Gamma^{\mu\ \text{bare}} = F_1\gamma^\mu + F_2\frac{2i\Sigma^{\mu\nu}q_\nu}{2m},
\end{equation}
with,
\begin{equation}
F_1 = \frac{ e'^2}{\left(4\pi\right)^{2}}\left[ \xi \frac{1}{\epsilon} - \gamma_E - 2 - 2\int_0^1dx\ \int_0^{1-x}dy\ \log\left(\frac{m^2\left(x+y\right)^2 -xy q^2}{4\pi\mu}\right) \right.
\end{equation}
\begin{equation}
+2\int_0^1dx\ \int_0^{1-x}dy\ \frac{ \left( \left(x+y\right) +2(x+y)^2-2(1+xy) \right)m^2 + (1-x)(1-y)q^2 }{ m^2\left(x+y\right)^2 -xy q^2 } \right] \nonumber
\end{equation}
\begin{equation}
+\left(1-\xi\right)\left[\text{term of } \mathcal{O}\left(\epsilon^0\right)\right] , \nonumber
\end{equation}
and,
\begin{equation}
F_2 = 2ie^2 \frac{2e^2}{\left(4\pi\right)^2 }\int_0^1dx\  \frac{m^2} {m^2+x(x-1)q^2}  . \nonumber
\end{equation}

We must verify the infrared behaviour of both integrals. We know $$F_2$$ is convergent in the infrared, which makes sense as the counterterm, $$ie\delta_1\gamma^\mu$$ can already only impact $$F_1$$.


### Sources
I sought to do this without any external sources. Mainly to see if I still could. I only reviewed my own notes taken during my Quantum Field Theory II class (8.324), taught by Professor Ian Stewart during the 2025 Fall semester.

