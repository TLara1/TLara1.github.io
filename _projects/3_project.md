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

\begin{equation}
\sigma_{ij,j}=0
\end{equation}

The stress tensor for an isotropic, homogenous material is given via Hooke's law:

\begin{equation}\label{Hooke's law}
  \sigma_{ij}=C_{ijkl}\epsilon_{kl}=\lambda\delta_{ij}\epsilon_{kk}+2\mu\epsilon_{ij}
\end{equation}

Where $$\epsilon_{ij}\equiv\frac{1}{2}\left(u_{i,j}+u_{j,i}\right)$$ is the strain tensor with displacements $$u_i$$. Now propose functions $$A$$ and $$B$$ such that:

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

Now, from \eqref{Hooke's law}:

\begin{equation}
  \sigma_{xx,yy}+\sigma_{yy,xx}=\left(\lambda+2\mu\right)\left(\epsilon_{xx,yy}+\epsilon_{yy,xx}\right)+\lambda\left(\epsilon_{yy,yy}+\epsilon_{xx,xx}\right) \nonumber
\end{equation}


