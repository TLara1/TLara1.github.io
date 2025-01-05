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

The most useful criteria for determining if a transform is canonical are _Poisson brackets_. Given coordinates $$q_i$$ and $$p_i$$, the Poisson bracket of functions $$Q_j\left(q_i,p_i\right)$$ and $$P_j\left(q_i,p_i\right)$$ is given by:
\begin{equation}
    \[ Q_j,P_j \]=\sum_i\frac{\partial Q_j}{\partial q_i}\frac{\partial P_j}{\partial p_i}-\frac{\partial Q_j}{\partial p_i}\frac{\partial P_j}{\partial q_i}
\end{equation}
We show that a transform is canonical if and only if:

\begin{equation}
    \[  Q_i,Q_j  \]=0\label{cannonical 1}
\end{equation}

\begin{equation}
    \[ P_i,P_j \]=0
\end{equation}

\begin{equation}
    \[ Q_i,P_j \]=\delta_{ij}\label{cannonical 3}
\end{equation}

Poisson Brackets can also be used to determine if a function of coordinates $$f\left(p_i,q_i\right)$$ is constant in time:
\begin{equation}\label{const function}
    \frac{df}{dt}=\sum_i\frac{\partial f}{\partial q_i}\dot{q}_i+\frac{\partial f}{\partial p_i}\dot{p}_i=\[ f,\mathcal{H} \]
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


<h3>II.II Kepler's First Law</h3>
We rewrite \eqref{Netwon polar coordinates} in the $$\hat{e}_r$$ direction:

\begin{equation}\label{r equation newton} \ddot{r}-\frac{L^2}{\mu^2r^3}=-\frac{\mathcal{G}m}{r^2} \end{equation}

Performing the substitution, $$u=\frac{1}{r}$$:

\begin{equation} \dot{r} = \dot{u}\frac{dr}{du} = -r^2\dot{u} = -r^2\dot{f}\frac{du}{df} = -\frac{L}{\mu}\frac{du}{df} \end{equation}

\begin{equation} \ddot{r} = \frac{d}{dt}\left(-\frac{L}{\mu}\frac{du}{df}\right)=--\frac{L}{\mu}\dot{f}\frac{d^2u}{df^2} = -\left(\frac{L}{\mu}\right)^2u^2\frac{d^2u}{df^2} \end{equation}

\eqref{Netwon polar coordinates} in terms of $$u$$:

\begin{equation} \label{dif eq with u} -\left(\frac{L}{\mu}\right)^2u^2\frac{d^2u}{df^2} -\frac{L^2}{\mu^2r^3} = -\mathcal{G}mu^2 \rightarrow \frac{d^2u}{df^2} + u = \mathcal{G}m\frac{\mu^2}{L^2} \end{equation}

Solving for $$u$$:

\begin{equation} u=\mathcal{G}m\frac{\mu^2}{L^2}\left(1+e\cos{f}\right) \end{equation}

Where $$e$$ is a dimensionless parameter, the \textit{eccentricity} which we are free to set. Solving for $$r$$:

\begin{equation}\label{r equation kepler} r=\frac{L^2}{\mathcal{G}m\mu^2}\frac{1}{1+e\cos{f}} \end{equation}

We consider only $$0<e<1$$, giving a closed orbit. Broadly speaking, the closer $$e$$ is to 0, the more circular an orbit is, and as $$e$$ approaches 1, the orbit becomes more elliptical. This is Kepler's First Law. Note that because $$e$$ is a constant we chose, $$\dot{e}=0$$.

<h3>II.III Kepler's Third Law</h3>

We relate the orbit period $$P$$ with the orbit's semi-major axis $$a$$. Converting \eqref{r equation kepler} into Cartesian coordinates:

\begin{equation} r+ex=\frac{L^2}{\mathcal{G}m\mu^2}\rightarrow y^2=\left(\frac{L^2}{\mathcal{G}m\mu^2}-ex\right)^2-x^2 \end{equation}

We find the length $$l$$, of the orbiting ellipse by adding the zeros of our ellipse:

\begin{equation} l= \frac{L^2}{\mathcal{G}m\mu^2}\frac{1}{e+1} - \frac{L^2}{\mathcal{G}m\mu^2}\frac{1}{e-1} = \frac{2L^2}{\mathcal{G}m\mu^2}\frac{1}{1-e^2} \end{equation}

The semi-major axis $$a$$ is defined as half this length:

\begin{equation}\label{a equation} a=\frac{L^2}{\mathcal{G}m\mu^2}\frac{1}{1-e^2} \end{equation}

The height, $$h$$, of our ellipse is given by the maximum of y:

\begin{equation} h=\frac{L^2}{\mathcal{G}m\mu^2}\frac{1}{\sqrt{1-e^2}} \end{equation}

Finding the area, $$A$$, of the ellipse:

\begin{equation} A=\pi\frac{lh}{2}=\pi\left(\frac{L^2}{\mathcal{G}m\mu^2}\right)^2\left({1-e^2}\right)^{-\frac{3}{2}}=\pi\sqrt{\frac{L^2}{\mathcal{G}m\mu^2}}a^{\frac{3}{2}} \end{equation}

Using Kepler's second law, which is easily found by considering the area swept out in our ellipse over time:

\begin{equation} \dot{A} \simeq \frac{1}{2}r^2\dot{f} = \frac{L}{2\mu} \end{equation}

We can find the period $$P$$:

\begin{equation} P=\frac{A}{\dot{A}}=\frac{2\pi a^{\frac{3}{2}}}{\sqrt{\mathcal{G}m}} \end{equation}

We define the mean motion at $$n=\frac{2\pi}{P}$$ and summarize Kepler's Laws:

\begin{equation} n=\sqrt{\frac{\mathcal{G}m}{a^3}}\label{n equation} \end{equation}
\begin{equation} L=\mu\sqrt{\mathcal{G}ma\left(1-e^2\right)}=\mu na^2\sqrt{1-e^2}\label{L defintion} \end{equation}
\begin{equation} r=\frac{a\left(1-e^2\right)}{1+e\cos{f}}\label{r theta equation} \end{equation}

<h2>III. Orbital Elements</h2>
<h3>III.I Derivation of Mean and Eccentric Anomalies</h3>

From \eqref{r theta equation}:

\begin{equation} \dot{r} = \frac{r}{1+e\cos{f}}e\sin{f}\dot{f}=\frac{L}{\mu r\left(1+e\cos{f}\right)}e\sin{f}=\frac{na^2\sqrt{1-e^2}}{r\left(1+e\cos{f}\right)}e\sin{f} \end{equation}

We have used $$L=\mu r^2\dot{f}$$ and \eqref{L defintion}. Again using \eqref{r theta equation}:

\begin{equation} \dot{r} = \frac{na}{\sqrt{1-e^2}}e\sin{f} \end{equation}

In polar coordinates, the magnitude of the velocity vector $$\parallel\dot{\vec{r}}\parallel^2=\parallel\vec{v}\parallel^2=\dot{r}^2+r^2\dot{f}^2$$, resulting in:

\begin{equation} v^2=\dot{r}^2+\frac{L^2}{r^2\mu^2}=\frac{n^2a^2}{1-e^2}e^2\sin^2{f}+\frac{n^2a^2}{1-e^2}\left(1+e\cos{f}\right)^2=\frac{n^2a^2}{1-e^2}\left(1+2e\cos{f}+e^2\right) \end{equation}

With \eqref{r theta equation} and \eqref{n equation}:

\begin{equation}\label{v^2 equation} v^2=\frac{n^2a^2}{1-e^2}\left(\frac{2a(1-e^2)}{r}-1+e^2\right)=\frac{2n^2a^3}{r}-n^2a^2=\mathcal{G}m\left(\frac{2}{r}-\frac{1}{a}\right) \end{equation}

Using \eqref{v^2 equation} to rewrite $$\dot{r}$$:

\begin{equation}\label{r dot equation} \dot{r}^2=v^2-\frac{L^2}{r^2\mu^2}=\frac{2n^2a^3}{r}-n^2a^2-\frac{ n^2a^4\left(1-e^2\right)}{r^2}\rightarrow \dot{r}=\frac{na}{r}\sqrt{a^2e^2-\left(r-a\right)^2} \end{equation}

We have a differential equation for $$r$$, which we solve by writing $$r$$ in terms of the eccentric anomaly $$E$$:

\begin{align} r&=a\left(1-e\cos{E}\right)\label{r E equation}\ \dot{r}&=ae\sin{E}\dot{E} \end{align}

Rewriting \eqref{r dot equation} using $$E$$:

\begin{equation} \dot{E}=\frac{na}{r}=\frac{n}{1-e\cos{E}} \end{equation}

Integrating, we find:

\begin{equation}\label{Kepler eq} E-e\sin{E}=n\left(t-t_0\right)\equiv\mathcal{M} \end{equation}

This is Kepler's Equation, where $$\mathcal{M}$$ is known as the mean anomaly.

<h3>Two-Dimensional Orbital Elliptical Elements</h3>

{% include figure.liquid loading="eager" path="assets/img/Figures Cmech Notes/Orbital_Element_diagram_v2.png" title="example image" class="img-fluid rounded z-depth-1" %}
This image can also have a caption. It's like magic.
