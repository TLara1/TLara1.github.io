---
layout: page
title: Celestial Mechanics and the Precession of Mercury
description:
img: assets/img/12.jpg
importance: 1
category: work
related_publications: false
---

<h2> Introduction</h2>
\section{Introduction}
The study of celestial bodies is perhaps one of the most well-studied problems in physics. In particular, one of the early triumphs of Einstein's theory of relativity was explaining the classically unexplainable precession of Mercury's perihelion. Many texts on relativity present a proof of Mercury's relativistic precession, but without an explanation of non-relativistic sources of precession, this result is somewhat meaningless. 

In these notes, we take a classical approach to the three-body problem, examining how other planets affect Mercury's perihelion before turning to the relativistic effect. We assume all bodies are perfect spherical point masses with no spin.

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
    \[  Q_j,P_j  \]=\sum_i\frac{\partial Q_j}{\partial q_i}\frac{\partial P_j}{\partial p_i}-\frac{\partial Q_j}{\partial p_i}\frac{\partial P_j}{\partial q_i}
\end{equation}
We show that a transform is canonical if and only if:

\begin{equation}
    \[   Q_i,Q_j   \]=0\label{cannonical 1}
\end{equation}

\begin{equation}
    \[  P_i,P_j  \]=0
\end{equation}

\begin{equation}
    \[  Q_i,P_j  \]=\delta_{ij}\label{cannonical 3}
\end{equation}

Poisson Brackets can also be used to determine if a function of coordinates $$f\left(p_i,q_i\right)$$ is constant in time:
\begin{equation}\label{const function}
    \frac{df}{dt}=\sum_i\frac{\partial f}{\partial q_i}\dot{q}_i+\frac{\partial f}{\partial p_i}\dot{p}_i=\[  f,\mathcal{H}  \]
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

Where $$e$$ is a dimensionless parameter, the _eccentricity_  which we are free to set. Solving for $$r$$:

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

\begin{equation} r=a\left(1-e\cos{E}\right)\label{r E equation}\end{equation}
\begin{equation} \dot{r}=ae\sin{E}\dot{E} \end{equation}

Rewriting \eqref{r dot equation} using $$E$$:

\begin{equation} \dot{E}=\frac{na}{r}=\frac{n}{1-e\cos{E}} \end{equation}

Integrating, we find:

\begin{equation}\label{Kepler eq} E-e\sin{E}=n\left(t-t_0\right)\equiv\mathcal{M} \end{equation}

This is Kepler's Equation, where $$\mathcal{M}$$ is known as the mean anomaly.

<h3>III.II Two-Dimensional Orbital Elliptical Elements</h3>

{% include figure.liquid loading="eager" path="assets/img/Figures_Cmech_Notes/Orbital_Element_diagram_v2.png" title="Orbital element diagram" class="img-fluid rounded z-depth-0" %}
Orbital elements, definition of $$a$$, $$e$$, $$E$$, and $$f$$.

From our orbital element diagram, we can immediately conclude:
\begin{equation}\label{cos f equation}
    q_1=r\cos{f}=a\cos{E}-ae
\end{equation}
From \eqref{r theta equation}:
\begin{equation}
    r=\frac{a(1-e^2)}{1+e\cos{f}}=\frac{ra(1-e^2)}{r+eq_1}=\frac{ra(1-e^2)}{r+e\left(a\cos{E}-ae\right)}
\end{equation}
\begin{equation}
    \rightarrow r=a(1-e^2)-e\left(a\cos{E}-ae\right)=a\left(1-e\cos{E}\right)
\end{equation}
Aligning with our result of \eqref{r E equation}. We can also calculate $$q_2$$:
\begin{equation}
    q_2=\sqrt{r^2-q_1^2}= a\sqrt{\left(1-e\cos{E} \right)^2 - \left(\cos{E}-e \right)^2} = a\sqrt{1-e^2}\sin{E}
\end{equation}
In summary:
\begin{equation}
     q_1=a\left(\cos{E}-e\right)\label{q_1 eq}
\end{equation}
\begin{equation}
     q_2=a\sqrt{1-e^2}\sin{E}\label{q_2 eq}
\end{equation}
\begin{equation}
     r=a\left(1-e\cos{E}\right)
\end{equation}

<h3>III.III Three-Dimensional Orbital Elements</h3>

To characterize the orientation of our ellipse in three-dimensional space with respect to a reference plane $$x,y,z$$, we introduce three new angles. The first is the inclination $$i$$, describing the tilt of the orbiting ellipse with respect to the $$x,y$$ plane. Any orbit with a nonzero inclination will intersect the reference plane at two points. The _ascending node_ is the point at which the body passes from negative $$z$$ to positive $$z$$, and the _descending node_ is the opposite.
The angle between the _ascending node_ with the $$x$$ axis is the longitude of the ascending node, noted by $$\Omega$$. Finally, $$\omega$$, the argument of the pericentre determines the angle from the $$x,y$$ of the pericentre along the orbiting plane.

{% include figure.liquid loading="eager" path="assets/img/Figures_Cmech_Notes/Orbital_3d_elemenets_v2.png" title="Orbital element diagram 3d" class="img-fluid rounded z-depth-0" %}
Three-dimensional orbital angles.

Schematically, the transformation from a vector $$\vec{r}$$ in the reference plane to a vector $$\vec{q}$$ in the orbiting ellipse can be thought of as three consecutive rotations. First, we rotate around the $$z$$ axis by $$\Omega$$ to align the $$x$$ axis with the ascending node. Then we rotate around the $$x$$ axis by $$I$$ to set the $$z$$ axis normal to the orbiting plane. Lastly, we rotate around the $$z$$ axis by $$\omega$$ to set the $$x$$ axis along the semi-minor axis. In summary, we define the rotation:

\begin{equation}
    \vec{r}=**R**_\{Omega} **R**_{I} **R**_{\omega} = **R**_{xq} \vec{q}
\end{equation}

The matrix $$**R**_{xq} $$ transforms $$\vec{q}$$ to $$\vec{r}$$ and $$**R**_{qx} =**R**_{xq}^{-1}$$ does the inverse. $$**R**_\{Omega}$$,  $$**R**_{I}$$, and $$**R**_{\omega}$$ are rotation matrices about the $$z$$, $$x$$, and $$z$$ axis. 

From \eqref{q_1 eq} and \eqref{q_2 eq}, and because the orbit is by definition in the orbiting ellipse setting $$q_3=0$$. Utilizing our transform and polar coordinates, $$q_1=r\cos{f}$$, $$q_2=r\sin{f}$$:
\begin{equation}
    \frac{x}{r}=\left(\cos{\Omega}\cos{\omega}-\sin{\Omega}\cos{I}\sin{\omega}\right)\cos{f}+\left(-\cos{\Omega}\sin{\omega}-\sin{\Omega}\cos{I}\cos{\omega}\right)\sin{f}\nonumber
\end{equation}
\begin{equation}
    =\cos{\Omega}\cos{(\omega+f)}-\sin{\Omega}\cos{I}\sin{(\omega+f)}\label{x orbital elements}
\end{equation}
\begin{equation}
    \frac{y}{r}=\left(\sin{\Omega}\cos{\omega}+\cos{\Omega}\cos{I}\sin{\omega}\right)\cos{f}+\left(-\sin{\Omega}\sin{\omega}+\cos{\Omega}\cos{I}\cos{\omega}\right)\sin{f}\nonumber
\end{equation}
\begin{equation}
    =\sin{\Omega}\cos{(\omega+f)}+\sin{\Omega}\cos{I}\cos{(\omega+f)}\label{y orbital elements}
\end{equation}
\begin{equation}
    \frac{z}{r}=\sin{I}\sin{\omega}\cos{f}+\sin{I}\cos{\omega}\sin{f}\nonumber
\end{equation}
\begin{equation}
    =\sin{I}\sin{(\omega+f)}\label{z orbital elements} 
\end{equation}

<h2>IV. Expansion of the Two-Body Hamiltonian in Delaunay Variables}</h2>
Here we write the Hamiltonian for the two-body system and solve the Hamilton-Jacobi Equation to find a set of action-angle variables that are constant over time.

We begin by identifying the Two-Body Hamiltonian in Cartesian coordinates. From \eqref{governing Newton Law}, the Lagrangian of the system is given by:
\begin{equation}
    \mathcal{L}=\frac{1}{2}\mu\parallel\dot{\vec{r}}\parallel^2+\frac{\mathcal{G}\mu m}{\parallel\vec{r}\parallel}
\end{equation}
Via the Euler-Lagrange Equation, \eqref{governing Newton Law} is recovered:
\begin{equation}
    \frac{d}{dt}\left(\frac{\partial \mathcal{L}}{\partial \dot{\vec{r}}}\right)-\frac{\partial \mathcal{L}}{\partial \vec{r}}=0\rightarrow\mu\ddot{\vec{r}}+\frac{\mathcal{G}\mu m}{\parallel\vec{r}\parallel^3}\vec{r}=0
\end{equation}
We can now write the Hamiltonian using:

\begin{equation}
    \vec{p}=\frac{\partial \mathcal{L}}{\partial \dot{\vec{r}}}=\mu\dot{\vec{r}}\label{p def}
\end{equation}

\begin{equation}
    \mathcal{H}=p\dot{r}-\mathcal{L}=\frac{1}{2\mu}\parallel\vec{p}\parallel^2-\frac{\mathcal{G}\mu m}{\parallel\vec{r}\parallel}
\end{equation}

From the spherical symmetry of the problem, it is natural for us to proceed using spherical coordinates. We perform another canonical transform from $$p_x$$, $$p_y$$, $$p_z$$, $$r_x$$, $$r_y$$, and $$r_z$$ coordinates to $$p_r$$, $$p_\phi$$, $$p_\theta$$, $$r$$, $$\theta$$, and $$\phi$$ coordinates:

\begin{equation}
    r_x = r \cos{\phi} \sin{\theta} \label{polar transform start}
\end{equation}

\begin{equation}
    r_y = r \sin{\phi} \sin{\theta}
\end{equation}

\begin{equation}
    r_z = r \cos{\theta}
\end{equation}

\begin{equation}
    p_x = p_r \cos{\phi} \sin{\theta} - \frac{p_\phi}{r \sin{\theta}} \sin{\phi} + \frac{p_\theta}{r} \cos{\phi} \cos{\theta}
\end{equation}

\begin{equation}
    p_y = p_r \sin{\phi} \sin{\theta} + \frac{p_\phi}{r \sin{\theta}} \cos{\phi} + \frac{p_\theta}{r} \sin{\phi} \cos{\theta}
\end{equation}

\begin{equation}
    p_z = p_r \cos{\theta} - \frac{p_\theta}{r} \sin{\theta}
\end{equation}

\begin{equation}
    p_r = \sqrt{p_x^2 + p_y^2 + p_z^2} \label{polar transform end}
\end{equation}

Again, it can be shown that this transform satisfies \eqref{cannonical 1}-\eqref{cannonical 3}. The Hamiltonian becomes:
\begin{equation}\label{2 body cartesian hamiltonian}
    \mathcal{H}=\frac{1}{2\mu}\left(p_r^2+\frac{p_\theta^2}{r^2}+\frac{p_\phi^2}{r^2\sin^2{\theta}}\right)-\frac{\mathcal{G}\mu m}{r}
\end{equation}

<h3>IV.I Action-Angle Variables</h3>
We now find a canonical transform, $$q_i\rightarrow Q_i$$ and $$p_i\rightarrow P_i$$ such that our transformed Hamiltonian $$\mathcal{K}$$ is a function of only momenta, $$\mathcal{K}\left(P_i\right)$$. Transformed position coordinates are known as _angles_ and transformed momenta are known as _actions_.

Utilizing the Hamilton-Jacobi Equation (\eqref{HJ Equation}) with a generating function $$S\left(r,\theta,\phi;P_1,P_2,P_3;t\right)$$, where $$P_1$$, $$P_2$$, and $$P_3$$ are constants of motion because the transformed Hamiltonian $$\mathcal{K}$$ is independent of $$Q_i$$. The Hamilton-Jacobi Equation is:
\begin{equation}
    \frac{1}{2\mu}\left(\left(\frac{\partial S}{\partial r}\right)^2+\frac{1}{r^2}\left(\frac{\partial S}{\partial \theta}\right)^2+\frac{1}{r^2\sin^2{\theta}}\left(\frac{\partial S}{\partial \phi}\right)^2\right)-\frac{\mathcal{G}\mu m}{r}+\frac{ \partial S}{\partial t}=0
\end{equation}
Separating $$S$$: $$S\left(r,\theta,\phi;P_1,P_2,P_3;t\right)=S_r\left(r;P_i\right)+S_\theta\left(\theta;P_i\right)+S_\phi\left(\phi;P_i\right)+S_t\left(P_i;t\right)$$, we find:
\begin{equation}
    \frac{1}{2\mu}\left(\left(\frac{dS_r}{dr}\right)^2+\frac{1}{r^2}\left(\frac{dS_\theta}{d\theta}\right)^2+\frac{1}{r^2\sin^2{\theta}}\left(\frac{dS_\phi}{d\phi}\right)^2\right)-\frac{\mathcal{G}\mu m}{r}+\frac{S_t}{dt}=0
\end{equation}
We find:
\begin{equation}
    \frac{dS_t}{dt} = -P_1 \label{S_t derivative}
\end{equation}

\begin{equation}
    \frac{dS_\phi}{d\phi} = P_2
\end{equation}

\begin{equation}
    \left(\frac{dS_\theta}{d\theta}\right)^2 + \frac{P_2^2}{\sin^2\theta} = P_3^2
\end{equation}

\begin{equation}
    \left(\frac{dS_r}{dr}\right)^2 + \frac{P_3}{r^2} - \frac{2\mathcal{G}\mu^2 m}{r} = 2\mu P_1 \label{S_r derivative}
\end{equation}

Now we identify the three constants of motion, $$P_1$$, $$P_2$$, and $$P_3$$. As $$\frac{\partial \mathcal{H}}{\partial t}=0$$, the energy of the system is conserved.
\begin{equation}
    P_1=\frac{1}{2\mu}\left(p_r^2+\frac{p_\theta^2}{r^2}+\frac{p_\phi^2}{r^2\sin^2{\theta}}\right)-\frac{\mathcal{G}\mu m}{r}
\end{equation}
The total angular momentum of the system:
\begin{equation}
    P_3^2=p_\theta^2+\frac{p_\phi^2}{\sin^2{\theta}}
\end{equation}
and the angular momentum along the $$z$$ axis:
\begin{equation}
    P_2=p_\phi
\end{equation}
are also conserved. It is not hard to show this conservation via \eqref{const function}. $$\[ P_1,\mathcal{H} \]=0$$, $$\[ P_2^2,\mathcal{H} \]=0$$, and $$\[ P_3,\mathcal{H} \]=0$$. It can also be shown that these variables are canonical (\eqref{cannonical 1}-\eqref{cannonical 3}): $$\[ P_1,P_2^2 \]=0$$, $$\[ P_1,P_3 \]=0$$, and $$\[ P_2^2,P_3 \]=0$$. 

We use our previous results to expand $$P_1$$, $$P_2$$, and $$P_3$$ into orbital elements. $$P_1$$ is the total energy of the system:
\begin{equation}
    P_1=\frac{\mu}{2}\parallel\dot{\vec{r}}\parallel^2-\frac{\mathcal{G}\mu m}{r}=\mathcal{G}\mu m\left(\frac{1}{r}-\frac{1}{2a}\right)-\frac{\mathcal{G}\mu m}{r}=-\frac{\mathcal{G}\mu m}{2a}
\end{equation}
We have used \eqref{p def} and \eqref{v^2 equation}. To transform $$P_2$$ and $$P_3$$, we need to consider the angular momentum of the system. Recalling that $$L\equiv\mu\parallel\vec{r}\times\dot{\vec{r}}\parallel$$ and using \eqref{polar transform end}-\eqref{polar transform end}:
\begin{equation}
    L\equiv\parallel\vec{r}\times{\vec{p}}\parallel=\sqrt{p_\theta^2+\frac{p_\phi^2}{\sin^2{\theta}}}\rightarrow P_3=L
\end{equation}
Considering the $$z$$ component of the angular momentum yields:
\begin{equation}
    \left(\vec{r}\times\dot{\vec{r}}\right)_z=p_\phi=P_2
\end{equation}
As $$L$$ is the norm of the angular momentum, and the angular momentum of the system is normal to the orbital plane, the $$z$$ component of the angular momentum is given by $$P_3=L\cos{I}$$, a projection of the angular momentum onto the $$z$$ axis. With \eqref{L defintion} in summary:
\begin{equation}
    P_1 = -\frac{\mathcal{G}\mu m}{2a} \label{P_1 def}
\end{equation}

\begin{equation}
    P_3 = \mu \sqrt{\mathcal{G}ma\left(1 - e^2\right)} \label{P_3 def}
\end{equation}

\begin{equation}
    P_2 = P_3 \cos{I} \label{P_2 def}
\end{equation}


Having expressed our transformed momenta in orbital elements, we must do the same for our transformed position coordinates. We solve for $$S$$ by integrating \eqref{S_t derivative}-\eqref{S_r derivative}:
\begin{equation}
    S=-P_1t+P_2\phi+\int\sqrt{P_3^2-\frac{P_2^2}{\sin^2\theta}}d\theta+\int\sqrt{2\mu P_1+\frac{2\mathcal{G}\mu^2 m}{r}-\frac{P_3^2}{r^2}}dr
\end{equation}
Using \eqref{transormned position coordinates}:
\begin{equation}
    Q_1 = frac{\partial {S}{\partial P_1} = -t + \mu \int \frac{dr}{\sqrt{2\mu\left(P_1 + \frac{\mathcal{G}\mu m}{r}\right) - \frac{P_3^2}{r^2}}} = -t + \mu I_1
\end{equation}

\begin{equation}
    Q_2 = frac{\partial {S}{\partial P_2} = \phi - P_2 \int \frac{d\theta}{\sin^2\theta\sqrt{P_3^2 - \frac{P_2^2}{\sin^2\theta}}} = \phi - P_2 I_3
\end{equation}

\begin{equation}
    Q_3 = frac{\partial {S}{\partial P_3} = P_3 \int \frac{d\theta}{\sqrt{P_3^2 - \frac{P_2^2}{\sin^2\theta}}} - P_3 \int \frac{dr}{r^2 \sqrt{2\mu \left(P_1 + \frac{\mathcal{G}\mu m}{r}\right) - \frac{P_3^2}{r^2}}} = P_3 \left(I_4 - I_2\right)
\end{equation}
Evaluating the integrals in order, starting with $$I_1$$. With \eqref{P_1 def} and \eqref{P_3 def}:
\begin{equation}
    I_1=\frac{1}{\mu\sqrt{\mathcal{G}m}}\int\frac{rdr}{\sqrt{-\frac{r^2}{a}+2r-a\left(1-e^2\right)}}
\end{equation}
With \eqref{r E equation}, $$dr=ae\sin EdE$$, and $$I_1$$ becomes:
\begin{equation}
    I_1 = \frac{1}{\mu \sqrt{\mathcal{G}m}} \int \frac{a^2 e \left(1 - e \cos E\right) \sin E \, dE}{\sqrt{- a \left(1 - e \cos E\right)^2 + 2a \left(1 - e \cos E\right) - a \left(1 - e^2\right)}}
\end{equation}

\begin{equation}
    = \frac{a^{\frac{3}{2}}}{\mu \sqrt{\mathcal{G}m}} \int \left(1 - e \cos E\right) dE
\end{equation}
Solving and plugging in \eqref{Kepler eq}
\begin{equation}
    I_1=\frac{a^\frac{3}{2}}{\mu\sqrt{\mathcal{G}m}}\left(E-e\sin E\right)=\frac{\mathcal{M}}{\mu n}
\end{equation}
Now for $$I_2$$, with the same substitutions:
\begin{equation}
    I_2 = \frac{1}{\mu \sqrt{\mathcal{G}m}} \int \frac{dr}{r \sqrt{-\frac{r^2}{a} + 2r - a\left(1 - e^2\right)}}
\end{equation}

\begin{equation}
    = \frac{1}{\mu \sqrt{\mathcal{G}m}} \int \frac{e \sin E \, dE}{\left(1 - e \cos{E}\right) \sqrt{- a \left(1 - e \cos E\right)^2 + 2a \left(1 - e \cos E\right) - a \left(1 - e^2\right)}}
\end{equation}

\begin{equation}
    = \frac{1}{\mu \sqrt{\mathcal{G}ma}} \int \frac{dE}{1 - e \cos{E}}
\end{equation}

Now, with \eqref{cos f equation}:
\begin{equation}
    \cos{f} = \frac{a}{r} \left( \cos{E} - e \right) = \frac{\cos{E} - e}{1 - e \cos E}
\end{equation}

\begin{equation}
    \sin{f} = \sqrt{1 - \cos^2 f} = \sqrt{1 - e^2} \frac{\sin E}{1 - e \cos E}
\end{equation}

\begin{equation}
    -\sin f \, df = \frac{\left(e^2 - 1\right) \sin E}{\left(1 - e \cos E\right)^2} \, dE \quad \rightarrow \quad df = \frac{\sqrt{1 - e^2}}{1 - e \cos E} \, dE
\end{equation}

Thus, $$I_2$$ becomes:
\begin{equation}
    I_2=\frac{1}{\mu\sqrt{\mathcal{G}ma\left(1-e^2\right)}}\int df=\frac{f}{P_3}
\end{equation}
Now for $$I_3$$. With \eqref{P_2 def} and \eqref{P_3 def}:
\begin{equation}
    I_3=\frac{1}{P_2}\int\frac{\cos Id\theta}{\sin^2\theta\sqrt{1-\frac{\cos^2 I}{\sin^2\theta}}}
\end{equation}
To proceed, we must consult spherical trigonometric relationships. In \eqref{spherical trig fig}, we plot the angle created by the body's position on the orbital plane and the reference plane. Because $$\theta$$ is measured from the $$z$$ axis towards the reference plane, we must invert $$I$$.



