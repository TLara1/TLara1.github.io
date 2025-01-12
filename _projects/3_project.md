---
layout: page
title: On Hertzian Contacts of Two Disks
description:
img: assets/img/mercury_precession.png
importance: 3
category: Physics
giscus_comments: false
---
<h2>Introduction</h2>



<h2>I. Solid Mechanics in Two-Dimensions</h2>

<h3>I.I The Airy Stress Function</h3>
For a body in equilibrium, in Einstein's summation convention:

\begin{equation}\label{force law}
  \sigma_{ij,j}=0
\end{equation}

The stress tensor for an isotropic, homogenous material is given via Hooke's law:

\begin{equation}\label{Hooke's law}
  \sigma_{ij}=C_{ijkl}\epsilon_{kl}=\lambda\delta_{ij}\epsilon_{kk}+2\mu\epsilon_{ij}
\end{equation}

Where $$\epsilon_{ij}\equiv\frac{1}{2}\left(u_{i,j}+u_{j,i}\right)$$ is the strain tensor with displacements $$u_i$$. Note that both $$\sigma_{ij}$$ and $$\epsilon_{ij}$$ are symmetric. Now propose functions $$A$$ and $$B$$ such that:

\begin{equation}
  B_{,x}=-\sigma_{xy} \nonumber
\end{equation}

\begin{equation}
  B_{,y}=\sigma_{xx} \nonumber
\end{equation}

\begin{equation}
  A_{,x}=\sigma_{yy} \nonumber
\end{equation}

\begin{equation}
  A_{,y}=-\sigma_{yx} \nonumber
\end{equation}

Clearly $$A_{,y}=B_{,x}$$, so allow $$U_{,x}=A$$ and $$U_{,y}=B$$. $$U$$ is the _Airy Stress Function_. The following are evident:

\begin{equation}
  \sigma_{xx}=U_{,yy}
\end{equation}

\begin{equation}
  \sigma_{yy}=U_{,xx}
\end{equation}

\begin{equation}
  \sigma_{xy}=-U_{,xy}
\end{equation}

With \eqref{Hooke's law} we write $$U$$ in terms of displacements:
\begin{equation} \label{dis uxx}
  U_{,xx}=\left(\lambda+2\mu\right)\epsilon_{yy}+\lambda\epsilon_{xx}=\left(\lambda+2\mu\right)u_{y,y}+\lambda u_{x,x}
\end{equation}

\begin{equation} \label{dis uyy}
  U_{,yy}=\left(\lambda+2\mu\right)\epsilon_{xx}+\lambda\epsilon_{yy}=\left(\lambda+2\mu\right)u_{x,x}+\lambda u_{y,y}
\end{equation}

\begin{equation} \label{dis uxy}
  U_{,xy}=-2\mu\epsilon_{xy}=-\mu\left(u_{x,y}+u_{y,x}\right)
\end{equation}

So with \eqref{dis uxx} and \eqref{dis uyy}:
\begin{equation} \label{ux U}
  2\mu u_{x,x} = U_{,yy}- \frac{\lambda}{2\left(\lambda+\mu\right)}U_{,kk}
\end{equation}

\begin{equation} \label{uy U}
  2\mu u_{y,y} = U_{,xx}- \frac{\lambda}{2\left(\lambda+\mu\right)}U_{,kk}
\end{equation}

Now, from \eqref{Hooke's law}:

\begin{equation}\label{grad sigma plus}
  \left(\sigma_{xx}+\sigma_{yy}\right) _{,kk} = \sigma _{xx,xx} + \sigma _{xx,yy} + \sigma _{yy,xx} + \sigma _{yy,yy} = 2\left(\lambda+\mu\right)\left(\epsilon _{xx,xx}+\epsilon _{yy,yy}+\epsilon _{xx,yy}+\epsilon _{yy,xx}\right)
\end{equation}

With \eqref{grad sigma plus}:

\begin{equation}\label{sigma sum}
  \sigma _{xx,yy} + \sigma _{yy,xx} - \frac{\lambda}{2\left(\lambda+\mu\right)} \left(\sigma _{xx}+\sigma _{yy}\right) _{,kk} = 2\mu\left(\epsilon _{xx,yy}+\epsilon _{yy,xx}\right)
\end{equation}

With \eqref{Hooke's law}:

\begin{equation}\label{sigma cross grad}
  \sigma_{xy,xy} = 2\mu\epsilon_{xy,xy} = 2\mu\left(u_{x,yxy}+u_{y,xxy}\right)=\mu\left(\epsilon_{xx,yy}+\epsilon_{yy,xx}\right)
\end{equation}

So, combining \eqref{sigma sum} and \eqref{sigma cross grad}:
\begin{equation}\label{full sigma}
  \sigma _{xx,yy} + \sigma _{yy,xx} - \frac{\lambda}{2\left(\lambda+\mu\right)} \left(\sigma _{xx}+\sigma _{yy}\right) _{,kk} - 2\sigma _{xy,xy} = 0
\end{equation}

With \eqref{force law}:
\begin{equation}\label{sigma cross}
  \sigma_{xx,xx}+\sigma_{xy,yx}+\sigma_{yy,yy}+\sigma_{yx,xy}=0\quad\rightarrow\quad - 2\sigma _{xy,xy} = \sigma _{xx,xx} +\sigma _{yy,yy}
\end{equation}

After pairing \eqref{full sigma} and \eqref{sigma cross}:

\begin{equation}\label{grad big sigma}
  left( \sigma _{xx} + \sigma _{yy} \right) _{,kk}=0
\end{equation}

\eqref{grad big sigma} has the immediate consequence that $$U$$ is biharmonic:
\begin{equation}
  U_{,iijj}=0
\end{equation}

<h3>I.II Complex Representations</h3>
Define $$P\equiv U_{,kk}$$, as $$U$$ is biharmonic, $$P_{,kk}=0$$; $$P$$ is harmonic. Allow $$Q$$ to be the harmonic conjugate to $$P$$, and from the Cauchy-Reimann Equations:

\begin{equation}
P_{,x}=Q_{,y} \nonumber
\end{equation}

\begin{equation}
P_{,y}=-Q_{,x} \nonumber
\end{equation}

Define $$\varphi=p+iq$$ such that:

\begin{equation}
  \varphi_{,z}=\varphi_{,x}=p_[,x}+iq_{,x}=\frac{1}{4}\left(P+iQ\right)
\end{equation}

Via Cauchy-Reimann:

\begin{equation}
  p_{,x}=q_{,y}=\frac{1}{4}P \nonumber
\end{equation}

\begin{equation}
  p_{,y}=-q_{,x}=-\frac{1}{4}Q \nonumber
\end{equation}

With \eqref{ux U} and \eqref{uy U}:

\begin{equation}
  2\mu u_{x,x} = -U_{,xx}+\frac{\lambda+2\mu}{2\left(\lambda+\mu\right)}P
\end{equation}

\begin{equation}
  2\mu u_{y,y} = -U_{,yy}+\frac{\lambda+2\mu}{2\left(\lambda+\mu\right)}P
\end{equation}

Integrating:

\begin{equation}
  2\mu u_{x} = -U_{,x}+\frac{2\lambda+2\mu}{\left(\lambda+\mu\right)}p+C_{1}\left(y\right)
\end{equation}

\begin{equation}
  2\mu u_{y} = -U_{,y}+\frac{2\lambda+2\mu}{\left(\lambda+\mu\right)}q+C_{2}\left(x\right)
\end{equation}

From the Cauchy-Reimann Equations:

\begin{equation}
  2\mu \left(u_{x,y}+u_{y,x}\right) = -2U_{,xy}+C_{1,y}\left(y\right)+C_{2,x}\left(x\right)
\end{equation}

From \eqref{dis uxy}:
\begin{equation}
  C_{1,y}\left(y\right)+C_{2,x}\left(x\right)=0
\end{equation}
So, $$C_1\sim y$$ and $$C_2\sim x$$, corresponding to rigid body displacements which we can safely ignore. 

Now consider:
\begin{equation}
  \left(U-xp-yq\right) _{,kk}= U _{,kk} - xp _{,kk} - yq _{,kk} -2p _{,x} - 2q _{,y} = U _{,kk} - xp _{,kk} - yq _{,kk} - P = xp _{,kk} - yq _{,kk} = 0
\end{equation}
We have used the fact that $$p$$ and $$q$$ are harmonic as $$p _{,kk} = p _{,xx} +p _{,yy} = q _{,yx} - q _{,xy} = 0$$

So:
\begin{equation}
  U = xp+yq+\mathcal{p}
\end{equation}
Where $$\mathcal{p}$$ is a harmonic function: $$\mathcal{p}_{,kk}=0$$.
