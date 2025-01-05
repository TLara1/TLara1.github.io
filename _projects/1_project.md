---
layout: page
title: Celestial Mechanics and the Precession of Mercury
description:
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

<h2>I. Mechanics</h2>
<h3>I.I Canonical Transforms</h3>

A time-independent coordinate transform $$q_i\rightarrow Q_i$$ and $$p_i\rightarrow P_i$$ is said to be canonical if it preserves Hamilton's equations of motion. Specifically, letting the new Hamiltonian $$\mathcal{K}\left(Q_i,P_i\right)=\mathcal{H}\left(q\left(Q_i,P_i\right),p_i\left(Q_i,P_i\right)\right)$$, then we have:

\begin{equation}
    \dot{Q}_i=\frac{\partial\mathcal{K}}{\partial P_i}
\end{equation}

\begin{equation}
    \dot{P}_i=-\frac{\partial\mathcal{K}}{\partial Q_i}
\end{equation}

The most useful criteria for determining if a transform is canonical are \textit{Poisson brackets}. Given coordinates $$q_i$$ and $$p_i$$, the Poisson bracket of functions $$Q_j\left(q_i,p_i\right)$$ and $$P_j\left(q_i,p_i\right)$$ is given by:
\begin{equation}
    <p>{ Q_j,P_j }<p>=\sum_i\frac{\partial Q_j}{\partial q_i}\frac{\partial P_j}{\partial p_i}-\frac{\partial Q_j}{\partial p_i}\frac{\partial P_j}{\partial q_i}
\end{equation}
We show that a transform is canonical if and only if:

\begin{equation}
    <p>{  Q_i,Q_j  }<p>=0\label{cannonical 1}
\end{equation}

\begin{equation}
    <p>{ P_i,P_j }<p>=0
\end{equation}

\begin{equation}
    <p>{ Q_i,P_j }<p>=\delta_{ij}\label{cannonical 3}
\end{equation}

Poisson Brackets can also be used to determine if a function of coordinates $$f\left(p_i,q_i\right)$$ is constant in time:
\begin{equation}\label{const function}
    \frac{df}{dt}=\sum_i\frac{\partial f}{\partial q_i}\dot{q}_i+\frac{\partial f}{\partial p_i}\dot{p}_i=<p>{ f,\mathcal{H} }<p>
\end{equation}

<h3>I.II The Hamilton-Jacobi Equation</h3>

A generating function $$F$$ generates a canonical transformation from coordinates $$q_i\rightarrow Q_i$$ and $$p_i\rightarrow P_i$$ and a Hamiltonian $$\mathcal{H\rightarrow\mathcal{K}}$$. This generating function satisfies:
\begin{equation}
    p_i\dot{q}_i-\mathcal{H}=P_i\dot{Q}_i-\mathcal{K}+\dot{F}
\end{equation}
Letting $$F=S\left(q_i,P_i,t\right)-Q_iP_i$$, we have:
\begin{equation}
    Q_i=\frac{\partial S}{\partial P_i}\label{transormned position coordinates}
\end{equation}

\begin{equation}
    p_i=\frac{\partial S}{\partial q_i}
\end{equation}

\begin{equation}
    \mathcal{K}=\mathcal{H}+\frac{\partial S}{\partial t}
\end{equation}
Now, suppose we want our transformed Hamiltonian, $$\mathcal{K}=0$$ such that $$\dot{Q}_i=0$$ and $$\dot{P}_i=0$$. So, we look for a generating function with:
\begin{equation}\label{HJ Equation}
    \mathcal{H}\left(q_i,\frac{\partial S}{\partial q_i},t\right)+\frac{\partial S}{\partial t}=0
\end{equation}
This is the Hamilton-Jacobi Equation.

<h2>II. Kepler's Laws</h2>
<h3>II.I Newton's Law and Polar Coordinates</h3>

We consider two bodies of mass $$m_0'$$ and $$m_1'$$. Newton's law of gravitation can be written:
\begin{equation} 
    \ddot{\vec{r}}_0'=\frac{\mathcal{G}m_1'}{\parallel \vec{r}_1'-\vec{r}_0'\parallel^3}\left(\vec{r}_1'-\vec{r}_0'\right)
\end{equation}
\begin{equation}
    \ddot{\vec{r}}_1'=-\frac{\mathcal{G}m_0'}{\parallel \vec{r}_1'-\vec{r}_0'\parallel^3}\left(\vec{r}_1'-\vec{r}_0'\right)
\end{equation}
Defining $$\vec{r}=\vec{r}_1'-\vec{r}_0'$$, we find:
\begin{equation} \label{governing Newton Law}
    \ddot{\vec{r}} = -\frac{\mathcal{G}m}{\parallel \vec{r}\parallel^3}\vec{r}
\end{equation}
we have defined $$m\equiv m_0'+m_1'$$.

We rewrite \eqref{governing Newton Law} using polar coordinates, with the basis transformation:
\begin{equation}    
    \hat{e}_x=\cos{f}\hat{e}_r-\sin{f}\hat{e}_f
\end{equation}

\begin{equation}
    \hat{e}_f=\sin{f}\hat{e}_r+\cos{f}\hat{e}_f
\end{equation}
It is not difficult to demonstrate:
\begin{equation}
    \vec{r}=r\hat{e}_e
\end{equation}

\begin{equation}
    \vec{\dot{r}}=\dot{r}\hat{e}_r+r\dot{f}\hat{e}_f
\end{equation}

\begin{equation}
    \vec{\ddot{r}}=(\ddot{r}-{r}\dot{f}^2){\hat{e}_r}+(2\dot{r} \dot{f} + r \ddot{f})\hat{e}_f
\end{equation}
\eqref{governing Newton Law} becomes:
\begin{equation}\label{Netwon polar coordinates}
    (\ddot{r}-{r}\dot{f}^2){\hat{e}_r}+(2\dot{r} \dot{f} + r \ddot{f})\hat{e}_f = -\frac{\mathcal{G}m}{r^2}\hat{e}_r
\end{equation}
The norm of the angular momentum vector is given by $$\parallel\vec{r}\times\dot{\vec{r}}\parallel= r^2\dot{f}$$. From \eqref{Netwon polar coordinates}, $$\frac{d\left(r^2\dot{f}\right)}{dt}=0$$, a statement of the conservation of total angular momentum. Let us define the reduced mass: $$\mu\equiv\frac{m_0'm_1'}{m_0'+m_1'}$$, and defined the quantity $$L\equiv\mu\parallel\vec{r}\times\dot{\vec{r}}\parallel=\mu r^2\dot{f}$$. 
