---
layout: page
title: On the Dirac Equation - 7/26
description:
img: 
importance: 2
category: Physics
related_publications: false
toc:
  beginning: true
---

## Introduction
I was halfway through writing my notes on quantum electrodynamics when I realized I wanted to discuss the Dirac Equation in more depth. So here we are. 

The main idea is that the Schrödinger equation is well and good for non-relativistic quantum mechanics, but since it is not Lorentz covariant, it is inadequate for a relativistic theory. This is troubling unless your name is Paul Dirac and the year is 1928, in which case you decide to invent new math and change the trajectory of the next century of physics research.

As usual, we use $$c=\hbar=1$$ for simplicity, and we use the mostly negative metric convention,
\begin{equation}
ds^2=\eta^{\mu\nu}x_\mu x_\nu = dt^2-dx^2-dy^2-dz^2.
\end{equation}
There are also a few conventions for gamma matrices that I will introduce when they come up.

## The Failures of the Schrödinger Equation
The usual Schrödinger equation for a wavefunction $$\psi\left(\mathbf{x}\right)$$ is,
\begin{equation}
i\partial_t\psi=H\left[ \psi \right]=-\partial_i\partial^i\psi+V\left(\mathbf{x}\right)\psi.
\end{equation}
We know our physics should be true in any frame of reference, that is to say, the Schrödinger equation should apply after we perform a Lorentz transform, denoting the transformed coordinates $$\mathbf{x}'$$, and the transformed wavefunction as $$\psi'\left(\mathbf{x}'\right)$$, it should be true that $$i\partial_{t'}\psi'=H'\left[\psi'\right]$$. As we will see, this is not the case.

Consider a Lorentz transform along the $$x$$-direction, the $$x$$ and $$t$$ coordinates change as,
\begin{equation}
t\rightarrow t' = \gamma t - \gamma v x,\quad x\rightarrow x' = \gamma x - \gamma v t,
\end{equation}
where $$\gamma=\left(1-v^2\right)^{-1/2}$$ is the Lorentz factor.

The wavefunction $$\psi$$ describes events at points in spacetime. Under a change of coordinates, there is no reason to expect $$\psi$$ to transform as a scalar; we therefore consider a general transform,
\begin{equation}\label{eq: psi transform f rule}
\psi\left(\mathbf{x}'\right)=f\left(\mathbf{x}\right)\psi\left(\mathbf{x}\right),
\end{equation}
and look for a function $$f\left(\mathbf{x}\right)$$ such that the Schrödinger equation is unchanged after our transformation. When $$f\neq1$$, our transform is said to be covariant rather than invariant.

For the left-hand side of the Schrödinger equation,
\begin{equation}\label{eq: transformed Schrodinger LHS}
i\partial_{t'}\psi'=i\partial_{t'}\left( f\psi\right)=i\gamma \left(f\partial_t\psi+ v f\partial_x\psi+\psi\partial_t f+ v\psi\partial_x f\right).
\end{equation}
For the right-hand side, ignoring the potential to assess the validity of the free equation,

\begin{equation}\label{eq: transformed Schrodinger RHS}
-\partial^2 _{x'}\psi'= -f \partial^2 _{x'}\psi - 2\partial _{x'} f \partial _{x'}\psi - \psi \partial^2 _{x'}f 
\end{equation}

\begin{equation}
=-\gamma^2 f \left(\partial_x^2\psi + 2 v \partial_x\partial_t\psi +  v^2\partial_t^2\psi\right) -\gamma^2 \psi \left(\partial_x^2 f + 2 v \partial_x\partial_t f +  v^2\partial_t^2 f \right) - \gamma^2\left(\partial_x\psi + v \partial_t\psi \right) \left(\partial_x f + v \partial_t f \right).
\end{equation}

Combining Eq. \ref{eq: transformed Schrodinger LHS} and Eq. \ref{eq: transformed Schrodinger RHS}, we see there is instantly a problem since the right-hand side contains new second-order derivatives of the form $$\partial_t\partial_x\psi$$ and $$\partial_t^2\psi$$. Reinserting the original Schrödinger equation results in
\begin{equation}
\text{terms with }\left[\psi, \partial_x\psi,\partial_x^2\psi\right] = \text{terms with }\left[\psi, \partial_x\psi,\partial_x^2\psi, \partial_x^3\psi,\partial_x^4\psi\right].
\end{equation}
Our relation must hold for any wavefunction $$\psi$$. Because the covariant transform function $$f$$ cannot depend on the wavefunction itself, there is no way we can find an $$f$$ to remove the higher-order derivative terms. So, we conclude that the Schrödinger equation is not Lorentz invariant or even Lorentz covariant. It is covariant under Galilean transforms, but we will leave that as an exercise to the reader. 

## Matrix-ifying the Schrödinger Equation

We could've avoided all of the math of the previous section by simply noting that the derivatives on each side of the Schrödinger equation are not of the same order, so a Lorentz transform would never work out. For Lorentz invariance, we require the order of the spatial and temporal derivatives to match. For instance, consider the Klein-Gordon equation,
\begin{equation}\label{eq: klein gordon equation}
\partial_\mu\partial^\mu\phi + m^2\phi = \partial_t^2\phi - \partial_i\partial^i\phi + m^2\phi = 0,
\end{equation}
a calculation as we performed above should convince you that this equation **is** Lorentz invariant and fully relativistic. The Dirac equation essentially aims to rewrite the Schrödinger equation with only first-order spatial derivatives. 

Let's first consider the following for our Hamiltonian with first-order spatial derivatives,
\begin{equation}
H = -i\alpha^i\partial_i + \beta m,
\end{equation}
Now we square the Schrödinger equation to find,
\begin{equation}\label{eq: squared shrodinger}
-\partial_t^2\psi = \left(-i\alpha^i\partial_i + \beta m\right)^2\psi.
\end{equation}
Inserting the Klein-Gordon equation in Eq. \ref{eq: squared shrodinger}, we find that $$\alpha$$ and $$\beta$$ should satisfy,
\begin{equation}
-\alpha^i\alpha^j\partial_i\partial_j\psi + \beta^2m^2\psi - i\left(\beta\alpha^i+\alpha^i\beta\right)\partial_i\psi=- \partial_i\partial^i\psi + m^2\psi.
\end{equation}
This gives the following conditions for $$\alpha$$ and $$\beta$$,
\begin{equation}\label{eq: alpha beta condition 1}
\alpha_i\alpha_j+\alpha_j\alpha_i=0\ i\neq j,
\end{equation}
\begin{equation}\label{eq: alpha beta condition 2}
\alpha_i^2=1,
\end{equation}
\begin{equation}\label{eq: alpha beta condition 3}
\beta^2=1,
\end{equation}
\begin{equation}\label{eq: alpha beta condition 4}
\beta\alpha^i+\alpha^i\beta = 0
\end{equation}
\begin{equation}
\alpha_i^\dagger=\alpha_i,
\end{equation}
\begin{equation}\label{eq: alpha beta condition 6}
\beta^\dagger=\beta,
\end{equation}
where the last two conditions follow from the Hermiticity of the Hamiltonian. But we have a huge problem, since $$i=1,2,3$$, Eq. \ref{eq: alpha beta condition 1}-Eq. \ref{eq: alpha beta condition 6} impose $$6+3+1+3+3+1=17$$ conditions for four variables. 

So what are we to do? Well, what if $$\alpha_i$$ and $$\beta$$ are not scalars but $$N\times N$$ matrices? If instead of four variables we have $$4N^2$$, we could satisfy the $$17$$ equations with $$N=3$$. But turns out we need an even $$N$$ for the following reason, we we now soncider $$\alpha$$ and $$\beta$$ as matrices,
\begin{equation}
\beta\alpha^i+\alpha^i\beta = 0\rightarrow\alpha^i=-\beta^{-1}\alpha^i\beta
\end{equation}
Using $$\beta^2=1\rightarrow\beta=\beta^{-1}$$,
\begin{equation}
\text{Tr}\left(\alpha^i\right)=-\text{Tr}\left(\beta^{-1}\alpha^i\beta\right)=-\text{Tr}\left(\alpha^i\right)\rightarrow\text{Tr}\left(\alpha^i\right)=0.
\end{equation}
By an equivalent argument, $$\beta$$ is also traceless, so the smallest $$N$$ we can have is $$N=4$$. So the only way to obtain a Hamiltonian that is first-order in space and is consistent with the Klein-Gordon equation is to turn $$\alpha^i$$ and $$\beta$$ into $$4\times4$$ matrices. Note that because $$4\times4^2=64>17$$, our conditions do not fully determine our matrix coefficients. In fact, there are infinitely many representations of matrices that we may choose. What is important is not the matrix components themselves, but the relationships between the matrices. Picking a set of matrices is nothing more than choosing a representation for our answer, akin to a change of coordinate basis.

We define the gamma matrices,
\begin{equation}
\gamma^0=\beta,\quad\gamma^i=\beta\alpha_i.
\end{equation}
Using Eq. \ref{eq: alpha beta condition 2} and Eq. \ref{eq: alpha beta condition 3}, we find,

\begin{equation}
\left(\gamma^0\right)^2=1,\quad\left(\gamma^i\right)^2=-1.
\end{equation}

Using Eq. \ref{eq: alpha beta condition 1} and Eq. \ref{eq: alpha beta condition 4}, we find,

\begin{equation}
\gamma^\mu\gamma^\nu+\gamma^\nu\gamma^\mu=0\ \mu\neq\nu,
\end{equation}

and we obtain the critical anticommutation relation,
\begin{equation}
\left\lbrace\gamma^\mu,\gamma^\nu\right\rbrace=2\eta^{\mu\nu}.
\end{equation}
The commutation relation is also helpful, 
\begin{equation}\label{eq: gamma commutator relation}
\left\[\gamma^\mu,\gamma^\nu\right\]=2\eta^{\mu\nu}-2\gamma^\nu\gamma^\mu,
\end{equation}
as is the  relation,
\begin{equation}\label{eq: gamma commutator commutator relation}
\left[\left\[\gamma^\mu,\gamma^\nu\right\],\gamma^\lambda\right] = 4\eta^{\nu\lambda}\gamma^\mu-4\eta^{\mu\lambda}\gamma^\nu.
\end{equation}

From the hermiticty of $$\alpha$$ and $$\beta$$, we can also find the conjugate relationship,
\begin{equation}
\left(\gamma^\mu\right) ^\dagger=\gamma^0\gamma^\mu\gamma^0.
\end{equation}

We have said a lot about these matrices, but what about our wavefunction $$\psi$$? What happens now that $$\psi$$ is being multiplied by matrices? Well, $$\psi$$ turns into a four-component spinor. Instead of having one value at a spacetime location $$\mathbf{x}$$, the spinor $$\psi$$ has four. There is more to be said about the properties of spinors, but for the moment, we will treat it as a glorified vector and make sure we take care of its order in any calculation as commutation is no longer guaranteed. Returning to our Hamiltonian, $$H = -i\alpha^i\partial_i + \beta m$$, rewritten in terms of our gamma matrices,
\begin{equation}
H = -i\gamma^0\gamma^i\partial_i +  m \gamma^0.
\end{equation}
And from the Schrödinger equation,
\begin{equation}
i\partial_t\psi = H\psi = -i\gamma^0\gamma^i\partial_i\psi + m \gamma^0 \psi \rightarrow \gamma^\mu\partial_\mu\psi +  m  \psi = 0.
\end{equation}
We have obtained the Dirac equation! This is a fully relativistic version of the Schrödinger equation, which is first-order in both time and space. The Dirac equation will often be written as,
\begin{equation}
\left(i\not\partial-m\right)\psi=0,
\end{equation}
where the slash notation is used to denote $$\not\partial=\gamma^\mu\partial_\mu$$.

## Lorentz Covariance of the Dirac Equation
We have stated, and we expect the Dirac equation to be Lorentz covariant, but we have not determined how our wavefunction $$\psi$$ transforms. We will follow the same procedure we used to show that the unmodified Schrödinger equation was not covariant; performing a Lorentz transform and then determining an adequate modification to $$\psi$$ such that the Dirac equation in the new basis is unchanged. Our procedure this time around will be somewhat more sophisticated. Let's consider a Lorentz transform,
\begin{equation}
x^{\mu}\rightarrow x'^\mu=\Lambda^\mu_\nu x^\nu,
\end{equation}
where $$\Lambda^\mu_\nu$$ is the transformation matrix. Derivatives transform as,
\begin{equation}
\partial_\mu\rightarrow\partial_{\mu'}=\left(\Lambda^{-1}\right)^\nu_\mu\partial_\nu.
\end{equation}
We expect our $$psi$$ spinor field to transform following,
\begin{equation}
\psi\left(\mathbf{x}\right)\rightarrow\psi'\left(\mathbf{x}'\right)=S\left(\Lambda\right)\psi\left(\mathbf{x}\right),
\end{equation}
where $$S$$ is a function of the transformation matrix. This is nothing more than a special case of our covariant transform used previously, Eq. \ref{eq: psi transform f rule}, it will turn out that $$S$$ does not need spacetime dependence. Also, remember that $$S$$ is also a matrix in spinor space. Under a Lorentz transform, the Dirac equation transforms as,
\begin{equation}
i\gamma^\mu\partial_\mu\psi -  m  \psi \rightarrow i\gamma^\mu\partial_{\mu'}\psi' -  m  \psi'  = i\left(\Lambda^{-1}\right)^\nu_\mu \gamma^\mu S\partial_\nu\psi -  m S \psi = 0.
\end{equation}
We wish to have the same equation, which, after multiplying by $$S^{-1}$$, we see can be achieved if we pick $$S$$ such that,
\begin{equation}\label{eq: covariance S relation}
S^{-1}\gamma^\nu S = \Lambda^\nu_\mu \gamma^\mu.
\end{equation}

To solve this equation, we will consider the infinitesimal transform,
\begin{equation}
\Lambda^\nu_\mu=\delta^\nu_\mu+\omega^\nu_\mu. 
\end{equation}
Because a Lorentz transform preserves the metric,
\begin{equation}
\eta^{\mu\nu}=\eta^{\alpha\beta}\Lambda^\mu_\alpha\Lambda^\nu _\beta,
\end{equation}
we can show that $$\omega _{\nu\mu}=-\omega _{\mu\nu}$$ is antisymmetric.

\begin{equation}
\eta^{\mu\nu}=\eta^{\alpha\beta}\left(\delta^\mu_\alpha+\omega^\mu_\alpha\right)\left(\delta^\nu_\beta+\omega^\nu_\beta\right)=\eta^{\mu\nu}+\omega^{\mu\nu}+\omega^{\nu\mu}\rightarrow\omega^{\mu\nu}=-\omega^{\nu\mu}.
\end{equation}
Physically, this makes sense. There are six transforms, three rotations and three boosts, so we should expect six independent components in our transformation matrix.

We do this without loss of generality, since any transform can be made of the sum of infinitesimal transforms. Now we will use the exponential ansatz,
\begin{equation}\label{eq: S ansatz}
S = e^{ -\frac{i}{2}\omega_{\mu\nu}\Sigma^{\mu\nu}} = 1 - \frac{i}{2}\omega_{\mu\nu}\Sigma^{\mu\nu} + \mathcal{O}\left(\omega^2\right),
\end{equation}
where $$\Sigma^{\mu\nu}$$ is a matrix in spinor space that is yet to be determined. Inserting Eq. \ref{eq: S ansatz} into Eq. \ref{eq: covariance S relation},
\begin{equation}
\left(1 + \frac{i}{2}\omega_{\alpha\beta}\Sigma^{\alpha\beta}\right)\gamma^\nu\left(1 - \frac{i}{2}\omega_{\lambda\sigma}\Sigma^{\lambda\sigma}\right) = \left(\delta^\nu_\mu+\omega^\nu_\mu\right) \gamma^\mu,
\end{equation}
\begin{equation}
\frac{i}{2}\omega_{\alpha\beta}\left[\Sigma^{\alpha\beta},\gamma^\nu\right]  = \omega^\nu_\mu\gamma^\mu.
\end{equation}
Via the antisymmetry of $$\omega^{\nu\mu}$$, we may rewrite the right-hand side as,
\begin{equation}
\omega^\nu_\mu\gamma^\mu = \eta^{\nu\alpha}\omega_{\alpha\mu}\gamma^\mu = \frac{1}{2}\omega_{\alpha\beta}\left(\eta^{\nu\alpha}\gamma^\beta-\eta^{\nu\beta}\gamma^\alpha\right),
\end{equation}
from which we conclude we are looking for a $$\Sigma^{\alpha\beta}$$ satisfying,
\begin{equation}
i\left[\Sigma^{\alpha\beta},\gamma^\nu\right]  = \eta^{\nu\alpha}\gamma^\beta-\eta^{\nu\beta}\gamma^\alpha.
\end{equation}
Luckily, we have already seen a relation that follows this property, via Eq. \ref{eq: gamma commutator commutator relation},
\begin{equation}
\Sigma^{\alpha\beta}  = \frac{i}{4}\left\[\gamma^\alpha,\gamma^\beta\right\].
\end{equation}
So, under a Lorentz transformation, the $$\psi$$ spinor field transforms as,
\begin{equation}
\psi\rightarrow\psi'= e^{ -\frac{i}{2}\omega_{\mu\nu}\Sigma^{\mu\nu}}\psi,\quad \Sigma^{\mu\nu} = \frac{i}{4}\left\[\gamma^\mu,\gamma^\nu\right\].
\end{equation}

Now, briefly, a few more identities: first, the conjugate of $$S$$, 
\begin{equation}
\left(\Sigma^{\mu\nu}\right)^\dagger=-\frac{i}{4}\left\[\gamma^\mu,\gamma^\nu\right\]^\dagger=\frac{i}{4}\gamma^0\left\[\gamma^\mu,\gamma^\nu\right\]\gamma^0=\gamma^0\Sigma^{\mu\nu}\gamma^0.
\end{equation}
From which we obtain,
\begin{equation}
S^\dagger=e^{\frac{i}{2}\omega_{\mu\nu}\gamma^0\Sigma^{\mu\nu}\gamma^0} =\gamma^0 e^{ \frac{i}{2}\omega_{\mu\nu}\Sigma^{\mu\nu}}\gamma^0 = \gamma^0S^{-1}\gamma^0.
\end{equation}
We haved used $$\left(\gamma^0\right)^2=1$$. Secondly, note that because $$S$$ is clearly not unitary, $$\psi^\dagger\psi$$ is not Lorentz invarient, but if we define $$\bar{\psi}=\psi^\dagger\gamma^0\psi$$, the quantity $$\bar{\psi}\psi$$ is a Lorentz scalar,
\begin{equation}
\bar{\psi}\psi\rightarrow \psi^\dagger S^\dagger \gamma^0 S \psi = \psi^\dagger \gamma^0S^{-1}\gamma^0 \gamma^0 S \psi = \bar{\psi}\psi.
\end{equation}
Similarly, it can be shown that $$\bar{\psi}\not \partial \psi$$ is also a Lorentz invariant after consulting Eq. \ref{eq: covariance S relation}.

## Solutions to the Dirac Equation
There are two solutions to the Dirac equation,
\begin{equation}
\psi^+=v(p)e^{i x^\mu p_\mu},\quad\psi^-=u(p)e^{-i x^\mu p_\mu}.
\end{equation}
The functions $$u(p)$$ and $$v(p)$$ satisfy,
\begin{equation}\label{eq. u equations}
\left(\not p + m\right)v = 0,\quad\left(\not p -m\right)u=0.
\end{equation}
There is more to be said about $$u$$ and $$v$$, but here we will only derive the **Gordon Identity**. 

Consider the conjugate of Eq. \ref{eq. u equations}
\begin{equation}\label{eq. u conjugate equations}
\bar{u}\left(\not p -m\right)u=0.
\end{equation}
From Eq. \ref{eq. u equations} and Eq. \ref{eq. u conjugate equations}
\begin{equation}
m\bar{u}\left(p'\right)\gamma^\mu u\left(p\right) = \bar{u}\left(p'\right)\gamma^\mu \not p u\left(p\right),\quad m\bar{u}\left(p'\right)\gamma^\mu u\left(p\right) = \bar{u}\left(p'\right)\not p' \gamma^\mu u\left(p\right).
\end{equation}
Adding and dividing by two,
\begin{equation}
\bar{u}\left(p'\right)\gamma^\mu u\left(p\right) = frac{1}{2m}\bar{u}\left(p'\right)\left(\gamma^\mu \not p+ \not p' \gamma^\mu\right)u\left(p\right).
\end{equation}
Using the gamma matrix commutation rules, Eq. \ref {eq: gamma commutator relation}, it is easy to find
\begin{equation}
\gamma^\mu \not p+ \not p' \gamma^\mu =  \frac{1}{2}\left[\not p' - \not p, \gamma^\mu \right] + \left(p' ^\mu + p^\mu\right) = -2i\Sigma^{\mu\nu}\left( p'_\nu - p _\nu\right) + \left(p' ^\mu + p^\mu\right),
\end{equation}
and we obtain the **Gordon Identity**,

\begin{equation}
\bar{u}\left(p'\right)\gamma^\mu u\left(p\right) = \frac{1}{2m}\bar{u}\left(p'\right)\left[\left(p' ^\mu + p^\mu\right) + 2i\Sigma^{\mu\nu}\left( p'_\nu - p _\nu\right) \right]u\left(p\right) .
\end{equation}
This looks somewhat strange, but is very useful for computing integrals in Quantum Field Theory.


## The Dirac Lagrangian
Finally, it is easy to verify that the Lagrangian that gives rise to the Dirac equation is,
\begin{equation}
\mathcal{L}_\text{dirac}=\bar{\psi}\left(i\not\partial-m\right)\psi.
\end{equation}
Variation with respect to $$\bar{\psi}$$ returns the Dirac equation. Note also that $$\mathcal{L} _\text{dirac}$$ is Lorentz covariant as required for a valid relativistic theory. 

There is more to be said about the Dirac equation and the Lagrangian, but for the moment, we will leave the discussion here. We have found the failings of the usual Schrödinger equation, constructed a relativistic version that is first order in all its derivatives and is consistent with the Klein-Gordon equation, and determined how the spinor fields of this new equation transform covariantly.

### Sources
I primarily followed my own course notes from 8.323, Relativistic Quantum Field Theory I, taught by Professor Hong Liu during the 2025 Spring semester.
