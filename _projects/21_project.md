---
layout: page
title: On the Renormalization of Quantum Electrodynamics
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

I am, unfortunately, no longer much of a theoretical physicist. I took three semesters of Quantum Field Theory (QFT) and decided it was not for me. But there is a beauty in the calculations of QFT, the slow methodical alignment of a malestrom of algebra and indices. I doubt these notes will serve me much in the future, but I wish to conserve some fraction of what I learned in QFT in a more permanent manner. 

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
where $$\psi$$ is a four-component spinor.

## The Lagrangian of Quantum Electrodynamics
I was originally going to simply present the Lagrangian of Quantum Electrodynamics and move on with my life, but I'm feeling like a completionist this morning, so we will derive it. We'll start with the full non-Abelian theory and then go from there.
Feel fully free to skip this if you cannot be bothered, but I find it interesting.

### Gauge Theory Transform
We begin with matter fields $$\psi_i\left(\mathbf{x}\right)$$ for $$i=1,2,...N$$. Note that each $$\psi_i$$ can be a scalar, spinor, tensor, etc. field, for the moment, our indices run over the field index, not the internal indices that may be associated with each $$\psi_i$$.

We require that in our theory, our physical observables be invariant under the local transform,
\begin{equation}\label{eq: gauge transform}
\psi_i\left(\mathbf{x}\right)\rightarrow \psi_i\left(\mathbf{x}\right)'=U_{ij}\left(\mathbf{x}\right)\psi_j\left(\mathbf{x}\right),
\end{equation}
where the matrix $$\mathbf{U}$$ is unitary,
\begin{equation}
\mathbf{U}^\dagger\mathbf{U}=\mathbf{I},
\end{equation}
This is a statement that the inner product $$\left|\psi\right|^2=\left|\psi'\right|^2$$ is unchanged under our transform. 

Now since the transformation matrix is unitary, we can express $$\mathbf{U}\left(\mathbf{x}\right)$$ as a matrix exponential,
\begin{equation}\label{eq: U transform exponential form}
\mathbf{U}\left(\mathbf{x}\right)=e^{i\alpha(x)^a\mathbf{T}_a}, 
\end{equation}
where each $$\alpha^a(x)$$ function is real and each $$\mathbf{T}_a$$ matrix is hermitian,
\begin{equation}
\mathbf{T}_a=\mathbf{T}_a^\dagger.
\end{equation}
We have done nothing more than express the unitary $$\mathbf{U}\left(\mathbf{x}\right)$$ as an exponent raised to a Hermitian matrix and then expressed this Hermitian matrix along the basis with elements $$\mathbf{T}_a$$. 

Excellent, now there is a good amount of group theory I will sweep under the rug here, and we will content ourselves without proof that our $$\mathbf{T}_a$$ basis matrices can be chosen to satisfy the following properties while still spanning the space for all available hermitian matrices,
\begin{equation}\label{eq: T matrix trace}
\text{Tr}\left(\mathbf{T} _a\mathbf{T} _b\right)=\frac{1}{2} \delta _{ab},
\end{equation}
and,
\begin{equation}\label{eq: structure constant commutation relation}
\left[\mathbf{T} _a,\mathbf{T} _b\right]=if^{c} _{ab}\mathbf{T} _c.
\end{equation}
$$f^{ab}_c$$ is known as a structure constant.

### The Gauge Field and Field Strength Tensor
We have waded through the more nebulous bits that teeter on the edge of abstract mathematics. Onto the more interesting things. Because our observables should be invariant under the transform of Eq. \ref{eq: gauge transform}, so should our Lagrangian. To build such a Lagrangian, we first need a covariant derivative. A covariant derivative $$D_\mu$$ transforms in the same way as our matter field, satisfying, 
\begin{equation}\label{eq: covariant derivative transformation condition}
D_\mu\psi\left(\mathbf{x}\right)\rightarrow D' _\mu\psi'\left(\mathbf{x}\right)=U\left(\mathbf{x}\right)D _\mu\psi\left(\mathbf{x}\right). 
\end{equation}

<em>Note that from here onward, for clarity, I will be suppressing the indices associated with matter fields and also removing the **bold** lettering on matrices acting on matter field indices.</em>. 

We may ask ourselves, what is the problem with an ordinary derivative $$\partial_\mu$$? Consider,
\begin{equation}\label{eq: partial_mu failed transform}
\partial_\mu\psi\left(\mathbf{x}\right)\rightarrow\partial_\mu\psi'\left(\mathbf{x}\right)=\partial_\mu\left(U\left(\mathbf{x}\right)\psi\left(\mathbf{x}\right)\right)=U\left(\mathbf{x}\right)\partial_\mu\psi\left(\mathbf{x}\right)+\partial_\mu\left(U\left(\mathbf{x}\right)\right)\psi\left(\mathbf{x}\right).
\end{equation}
Clearly $$\partial_\mu$$ does not transform as we hoped, but Eq. \ref{eq: partial_mu failed transform} is suggestive. Let's try a covariant derivative,
\begin{equation}\label{eq: covarient derivative definition}
D _\mu =\partial _\mu-i g A _\mu\left(\mathbf{x}\right),
\end{equation}
where $$g$$ is a coupling constant and $$A^a _\mu\left(\mathbf{x}\right)$$ is a gauge field that also transforms in a special way under our transformation rule. Employing Eq. \ref{eq: covarient derivative definition},

\begin{equation}
D_\mu\psi\left(\mathbf{x}\right)\rightarrow D'_\mu\psi'\left(\mathbf{x}\right)=U\partial _\mu\psi+\partial _\mu U\psi - i g A' _\mu\left(\mathbf{x}\right) U\psi.
\end{equation}

We see our transformation condition, Eq. \label{eq: covarient derivative transformation condition}, is satisfied if,
\begin{equation}
\partial_\mu\left(U\right) - i g A' _\mu\left(\mathbf{x}\right) U = - i g A\left(\mathbf{x}\right) U.
\end{equation}
From this we conclude $$A _\mu$$ transforms as,
\begin{equation}
A _\mu\rightarrow A' _\mu = U \left(A - i g^{-1} U^{-1} \partial _\mu \left(U\right)\right) U^{-1}.
\end{equation}
We may simplify by noting,
\begin{equation}
\partial _\mu\left(U^{-1}U\right)=U^{-1}\partial _\mu U + \partial _\mu\left(U^{-1}\right) U = 0 \rightarrow U^{-1}\partial _\mu\left(U\right) U^{-1} = -\partial _\mu\left(U^{-1}\right),
\end{equation}
which gives us,
\begin{equation}
A' _\mu = U \left(A _\mu + i g^{-1} \partial _\mu\right) U^\dagger,
\end{equation}
where we have used the unitarity of $$U$$. 

Because $$A _\mu$$ is a matrix in the matter field indices, we should be able to express it in terms of the basis matrices $$T_a$$ such that $$A _\mu \left(\mathbf{x}\right) = A^a _\mu\left(\mathbf{x}\right) T_a$$. It is easiest to do this by recalling that any transform $$U$$ can be compiled as the result of many infinitesimal transforms. So, we will only consider the transform under $$U\left(\mathbf{x}\right)=1+i\alpha^a\left(\mathbf{x}\right)T_a$$, for $$\alpha$$ small enough to neglect second-order terms. If we can obtain the appropriate transformation for $$A^a _\mu$$ in this case, it will be equivalent to the full transform in general. Applying this idea,

\begin{equation}
A' ^a _\muT_a = \left(1+i\alpha^bT_b\right)\left(A^a _\mu T_a + i g^{-1} \partial _\mu\right) \left(1-i\alpha^cT_c\right) = \left(A^a _\mu +g^{-1} \partial _\mu\alpha^a\right)T_a+iA^a _\mu\alpha^b\left(T_bT_a-T_aT_b\right),
\end{equation}

\begin{equation}\label{eq: A matrix component form transform}
A' ^a _\mu = \left(A^a _\mu +g^{-1} \partial _\mu\alpha^a\right) + A^b _\mu\alpha^cf_{bc}^a,
\end{equation}

we have used Eq. \ref{eq: structure constant commutation relation} to insert the structure constant.

We almost have all of the ingredients we need for our Lagrangian. Next, we construct the field strength tensor. Since the covariant derivative transforms as $$D_\mu'\psi'=UD_\mu\psi$$, it follows that $$D_\mu'=UD_\mu U^\dagger$$. From this, we note that the commutator of the covariant derivatives transforms in the same way,

\begin{equation}
\left[D _\mu,D _\nu\right]\rightarrow\left[D' _\mu,D' _\nu\right]=U\left[D _\mu,D _\nu\right]U^\dagger.
\end{equation}

We define the field strength tensor that transforms in the same way,
\begin{equation}
G_{\mu\nu}=\frac{i}{g}\left[D_\mu,D_\nu\right]=\partial_\mu A_\nu-\partial_\nu A_\mu-ig\left[A_\mu,A_\nu\right].
\end{equation}
In terms of the $$T_a$$ basis elements, the componenets $$G^a_{\mu\nu}$$ can be easily found to be,

\begin{equation}\label{eq: field strength tensor component form}
G^a _{\mu\nu}=\partial _\mu A _\nu^a-\partial _\nu A _\mu^a+gA^b _\mu A^c _\nu f^a _{bc}.
\end{equation}

We may also ask how the components, $$G^a _{\mu\nu}$$, act under a gauge transform. It is possible to use Eq. \ref{eq: field strength tensor component form} to solve for $$G'^a _{\mu\nu}$$ directly since we know how $$A _\nu^a$$ transforms from Eq. \ref{eq: A matrix component form transform}, but it is easier to recall the matrix transform is straightforward,

\begin{equation}
G _{\mu\nu}\rightarrow G' _{\mu\nu}=UG _{\mu\nu}U^\dagger,
\end{equation}

and use the same infinitesimal transformation trick we previously employed,

\begin{equation}
G'^a _{\mu\nu}T_a=\left(1+i\alpha^bT _b\right)G^a _{\mu\nu}T _a\left(1-i\alpha^cT _c\right)=G^a _{\mu\nu}T _a+G^b _{\mu\nu}\alpha^c f^a _{bc}T_a.
\begin{equation}

The field strength tensor $$G _{\mu\nu}$$ has a host of desirable properties. First, it is a local function of our gauge fields, not a differential operator, which is what we want for our Lagrangian. Second, it is only first-order in the derivatives of the Gauge fields, so we can combine two of these tensors to obtain a quantity that is second-order. To build a Lagrangian, we require Lorentz and gauge invariance. The first of these is easy to do: make sure there are no free indices since scalars are Lorentz invariant (more on Lorentz invariance soon). For the second condition, we can take the trace over matter field indices, observing that,

\begin{equation}
\text{Tr}\left(G^{\mu\nu}G _{\mu\nu}\right)\rightarrow\text{Tr}\left(G'^{\mu\nu}G' _{\mu\nu}\right)=\text{Tr}\left( UG^{\mu\nu}U^\dagger UG _{\mu\nu}U^\dagger\right) =\text{Tr}\left(G^{\mu\nu}G _{\mu\nu}\right).
\begin{equation}

Or, in component form,

\begin{equation}
\text{Tr}\left(G^{a\ \mu\nu}G _{b\ \mu\nu}T_aT^b\right) =G^{a\ \mu\nu}G _{b\ \mu\nu}\text{Tr}\left(T _aT^b\right) =\frac{1}{2}G^{a\ \mu\nu}G _{a\ \mu\nu},
\begin{equation}

after consulting Eq. \ref{eq: T matrix trace}. We define the gauge group of our Lagrangian,

\begin{equation}\label{eq: Gauge Lagrangian}
\mathcal{L} _\text{gauge} =-\frac{1}{4} G^{a\ \mu\nu}G _{a\ \mu\nu},
\begin{equation}

which describes the interactions between the gauge fields $$A _\mu\left(\mathbf{x}\right)$$. This Lagrangian is both gauge invariant and Lorentz invariant; of course, there are other Lagrangians we could write down that have these properties, but as we will soon see, many of those possibilities may not be renormalizable and thus not adequate to describe our theory. 

Also, Eq. \ref{eq: Gauge Lagrangian} gives rise to Maxwell's equations. Writing out the Lagrangian, Eq. \ref{eq: Gauge Lagrangian} in full,

\begin{equation}
\mathcal{L} _\text{gauge} = -\frac{1}{4}\left(\partial^\mu A^{a\ \nu} -\partial^\nu A^{a\ \mu}+gA^{b\ \mu}A^{c\ \nu}f^a _{bc}\right)\left(\partial _\mu A _{a\ \nu}-\partial _\nu A _{a\ \mu}+gA^b _\mu A^c _\nu f _{abc}\right)
\begin{equation}

\begin{equation}
=-\frac{1}{2}\left(\partial^\mu A^{a\ \nu}\partial _\mu A _{a\ \nu}-\partial^\mu A^{a\ \nu}\partial ^\nu A ^{a\ \mu}\right)-gf _{abc}A^{b\ \mu} A^{c\ \nu}\partial _\mu A^a_{\nu}-\frac{1}{4}g^2f^a _{bc}f _{ade}A^{b\ \mu}A^{c\ \nu}A^d _\mu A^e _\nu.
\begin{equation}
With the usual Euler-Lagrange Equations,

\begin{equation}
\partial_\nu\left(\frac{\partial\mathcal{L} _\text{gauge}}{\partial\left(\partial _\nu A _{a\ \mu}\right)}\right)-\frac{\partial\mathcal{L} _\text{gauge}}{\partial A _{a\ \mu}}=0,
\begin{equation}
we obtain the following equations of motion,
\begin{equation}
=-\partial _\nu \left(\partial^\nu A^{a\ \mu}-\partial^\mu A^{a\ \nu}\right)-gf _{abc}\partial _\nu\left(A^{b\ \nu} A^{c\ \mu}\right)+2gf _{bac} A^{c\ \nu}\partial ^\mu A^b _{\nu}+\frac{1}{2}g^2f^{ba} _{c}f _{bde}A^{c\ \nu}A^d _\mu A^e _\nu=0.
\begin{equation}
In a slightly cleaner form,
\begin{equation}
=\partial^2 A^{a\ \mu}-\partial _\mu\partial^\nu A^{a\ \nu}+gf _{abc}\left(A^{b\ \nu}\partial _\nuA^{c\ \mu}+A^{c\ \mu}\partial _\nu A^{b\ \nu}\right)

\partial _\nu\left(A^{b\ \nu} A^{c\ \mu}\right)


+2gf _{abc}\partial _\nu\left(A^{b\ \nu} A^{c\ \mu}\right)-2gf _{bac} A^{c\ \nu}\partial ^\mu A^b _{\nu}-g^2f^{ba} _{c}f _{bde}A^{c\ \nu}A^d _\mu A^e _\nu=0.
\begin{equation}









### Spinor fields
We have found an adequate term to insert into our Lagrangian that is both lorentz invari


, but it seems that our mass fields $$\psi$$ have fallen by the wayside. Let's consider a spinor field $$\psi$$. <em





The Lagrangian of Quantum Electrodynamics (QED) for a spinor$$-1/2$$ field $$\psi$$ is,
\begin{equation}\label{eq: QED Lagrangian}
\mathcal{L}=\bar{\psi}\left(i\not D-m\right)\psi-\frac{1}{4}F^{\mu\nu}F_{\mu\nu},
\end{equation}
We have used slash notation to indicate, $$\not D=\gamma^\mu D_\mu$$. $$D_\mu$$ is the covariant derivative,
\begin{equation}
D_\mu=\partial_\mu+ie A_\mu,
\end{equation}
where $$e$$ is the coupling constant equal to the charge of the Dirac field and $$A_\mu$$ is the gauge field. $$F_{\mu\nu}$$ is the electromagnetic field strength tensor,
\begin{equation}
F_{\mu\nu}=\partial_\mu A_\nu - \partial_\nu A_\mu.
\end{equation}

There are many ways to derive our Lagrangian, which we will omit here. We will only here show that Eq. \ref{eq: QED Lagrangian} satisfies several properties of interest. 

### Gauge Invariance
First, we note our Lagrangian is invariant under a $$U(1)$$ Gauge transform $$\alpha\left(\mathbf{x}\right)$$,
\begin{equation}
\psi\left(\mathbf{x}\right)\rightarrow e^{i\alpha\left(\mathbf{x}\right)}
\end{equation}




### Sources
