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
I was originally going to simply present the Lagrangian of Quantum Electrodynamics and move on with my life, but I'm feeling like a completionist this morning, so we will derive it. We begin with matter fields $$\psi_i\left(\mathbf{x}\right)$$ for $$i=1,2,...N$$. Note that each $$\psi_i$$ can be a scalar, spinor, tensor, etc. field, for the moment, our indices run over the field index, not the internal indices that may be associated with each $$\psi_i$$.

We require that our physical observables be invariant under the local transform,
\begin{equation}
\psi_i\left(\mathbf{x}\right)\rightarrow U_{ij}\left(\mathbf{x}\right)\psi_j\left(\mathbf{x}\right),
\end{equation}
where the matrix $$\mathbf{U}$$ is unitary,
\begin{equation}
\mathbf{U}^\dagger\mathbf{U}=\mathbf{I},
\end{equation}
and,
This is a statement that our observable $$\left|\psi\right\|^2$$ is unchanged under our transform. 

Now since the transformation matrix is unitary, we can express $$\mathbf{U}\left(\mathbf{x}\right)$$ as a matrix exponential,
\begin{equation}
\mathbf{U}\left(\mathbf{x}\right)=e^{i\alpha(x)^a\mathbf{T}_a}, 
\end{equation}
where each $$\alpha^a(x)$$ function is real and each $$\mathbf{T}_a$$ matrix is hermitian,
\begin{equation}
\mathbf{T}_a=\mathbf{T}_a^\dagger.
\end{equation}
We have done nothing more than expressed the unitary $$\mathbf{U}\left(\mathbf{x}\right)$$ as an exponent raised to a Hermitian matrix and then expressed this Hermitian matrix along the basis with elements $$\mathbf{T}_a$$. 

Excellent, now there is a good amount of group theory I will sweep under the rug here, and we will content ourselves without proof that our $$\mathbf{T}_a$$ basis matrices can be chosen to satisfy the following properties while still spanning the space for all available hermitian matrices,
\begin{equation}
\text{Tr}\left(\mathbf{T}_a\mathbf{T} _b\right)=\frac{1}{2} \delta _{ab},
\end{equation}
and,
\begin{equation}
\left[\mathbf{T}^a,\mathbf{T}^b\right]=iC^{ab}_c\mathbf{T}^c.
\end{equation}





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
