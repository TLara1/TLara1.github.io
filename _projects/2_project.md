---
layout: page
title: On the Precession of Mercury's Perihelion
description:
img: assets/img/mercury_precession.png
importance: 2
category: Physics
giscus_comments: false
toc:
  beginning: true
---

## Introduction
One of the earliest triumphs of Einstein's Theory of Relativity was the correct prediction of the perihelion precession of Mercury. Many sources derive this relativistic precession, but this is in itself meaningless if the classical precession is not understood. Mercury's perihelion is impacted both by the pull of other planets and the effects of general relativity. Here we use the Lagrange Planetary Equations to quantify the perihelion precession from both sources, showing that together they lead to the correct observed precession. 

## I. Bessel Functions
### I.I Introduction to Bessel Functions
Here we discuss Bessel Functions and their series expansions, which will help in our later analysis of orbital elements. Bessel functions, $$J_n(x)$$, of the first kind are defined as follows:
\begin{equation} \label{bessel definition}
    g(x,t) \equiv e^{\frac{x}{2}\left(t-\frac{1}{t}\right)} = \sum_{n=-\infty}^{\infty}J_n(x)t^n
\end{equation}
Where $$g(x,t)$$ is the generating function for real $$t$$ and $$x$$.\\
Now we note:
\begin{equation} \label{bessel recursion 1}
    \sum_{n=-\infty}^{\infty}J_n(x)t^n = \sum_{n=-\infty}^{\infty}J_{n-1}(x)t^{n-1} \rightarrow \sum_{n=-\infty}^{\infty}J_n(x)t^{n+1} = \sum_{n=-\infty}^{\infty}J_{n-1}(x)t^n
\end{equation}
And similarly:
\begin{equation} \label{bessel recursion 2}
    \sum_{n=-\infty}^{\infty}J_n(x)t^n = \sum_{n=-\infty}^{\infty}J_{n+1}(x)t^{n+1} \rightarrow \sum_{n=-\infty}^{\infty}J_n(x)t^{n-1} = \sum_{n=-\infty}^{\infty}J_{n+1}(x)t^n
\end{equation}
We use \eqref{bessel recursion 1} and \eqref{bessel recursion 2} to take the temporal and spatial derivatives of Bessel Functions. 

\begin{equation} 
    \frac{d}{dx}g(x,t) = \frac{1}{2}\left(t-\frac{1}{t}\right)e^{\frac{x}{2}\left(t-\frac{1}{t}\right)}  = \sum_{n=-\infty}^{\infty}\frac{1}{2}\left(t-\frac{1}{t}\right)J_n(x)t^n \nonumber
\end{equation}

\begin{equation}
    = \sum_{n=-\infty}^{\infty}\frac{1}{2}(t^{n+1}-t^{n-1})J_n(x) = \sum_{n=-\infty}^{\infty}\frac{1}{2}\left(J_{n-1}(x)-J_{n+1}(x)\right)t^n \nonumber
\end{equation}

\begin{equation} \label{Bessel space derivative}
    \rightarrow \frac{d}{dx}J_n(x) = \frac{1}{2}\left(J_{n-1}(x)-J_{n+1}(x)\right)
\end{equation}

\begin{equation}
    t\frac{d}{dt}g(x,t) = \frac{x}{2}\left(t + \frac{1}{t}\right)e^{\frac{x}{2}\left(t - \frac{1}{t}\right)} \nonumber
\end{equation}

\begin{equation}
    = \sum_{n=-\infty}^{\infty}\frac{x}{2}(t^{n+1} + t^{n-1})J_n(x) = \sum_{n=-\infty}^{\infty}\frac{x}{2}(J_{n-1}(x) + J_{n+1}(x))t^n    = \sum_{n=-\infty}^{\infty}nJ_n(x)t^n \nonumber
\end{equation}

\begin{equation} \label{Bessel time derivative}
    \rightarrow J_{n-1}(x) = \frac{2n}{x}J_n(x) - J_{n+1}(x).
\end{equation}

Combing \eqref{Bessel space derivative} and \eqref{Bessel time derivative}:

\begin{equation} \label{bessel recursion full 1}
    \frac{d}{dx}J_n(x) = \frac{1}{2}(J_{n-1}(x)-J_{n+1}(x)) = \frac{1}{2}(\frac{2n}{x}J_n(x)-2J_{n+1}(x)) = \frac{n}{x}J_n(x)-J_{n+1}(x)
\end{equation}

\begin{equation} \label{bessel recursion full 2}
    \frac{d}{dx}J_n(x) = \frac{1}{2}(J_{n-1}(x)-J_{n+1}(x)) = \frac{1}{2}(2J_{n-1}(x)-\frac{2n}{x}J_n(x)) = J_{n-1}(x)-\frac{n}{x}J_n(x)
\end{equation}

Now let us calculate $$\frac{d^2}{dx^2}J_n(x)$$ with \eqref{bessel recursion full 1} and \eqref{bessel recursion full 2}.

\begin{equation}
    \frac{d^2}{dx^2}J_n(x)= -\frac{n}{x^2}J_n(x)+\frac{n}{x}\frac{d}{dx}J_n(x)-\frac{d}{dx}J_{n+1}(x)\nonumber
\end{equation}

\begin{equation}
    = -\frac{n}{x^2}J_n(x)+\frac{n}{x}\left(\frac{n}{x}J_n(x)-J_{n+1}(x)\right)-J_n(x)+\frac{n+1}{x}J_{n+1}(x)\nonumber
\end{equation}


\begin{equation}
     = -\frac{n}{x^2}J_n(x)+\frac{n^2}{x^2}J_n(x)-J_n(x)+\frac{1}{x}J_{n+1}(x)
\end{equation}

And, eliminating $$J_{n+1}(x)$$ using $$J_{n+1}(x) = \frac{n}{x}J_{n}(x) - \frac{d}{dx}J_n(x)$$:

\begin{equation}
    \frac{d^2}{dx^2}J_n(x) = -\frac{n}{x^2}J_n(x)+\frac{n^2}{x^2}J_n(x)-J_n(x)+\frac{n}{x^2}J_n(x)-\frac{1}{x}\frac{d}{dx}J_n(x) \nonumber
\end{equation}

\begin{equation}
    x^2\frac{d^2}{dx^2}J_n(x) = n^2J_n(x)-x^2J_n(x)-x\frac{d}{dx}J_n(x) \nonumber
\end{equation}

We conclude that $$J_n(x)$$ solves the following differential equation:

\begin{equation} \label{bessel diffeq}
    x^2\frac{d^2}{dx^2}J_n(x) + x\frac{d}{dx}J_n(x) + (x^2-n^2) J_n(x)= 0
\end{equation}

### I.II Expansion of Bessel Function Through Frobenius Method

In this section, we develop a power series for Bessel Functions which we will use to expand orbital elements around $$e$$. First, suppose $$J_n(x)$$ can be expressed as a power series:

\begin{equation} \label{bessel power series}
    J_n(x) = x^r\sum_{k=0}^\infty A_k x^k
\end{equation}

It follows:

\begin{equation}
    \frac{dJ_n(x)}{dx} = \sum_{k=0}^\infty A_k (k+r)x^{k+r-1}
\end{equation}

\begin{equation}
    \frac{d^2J_n(x)}{dx^2} = \sum_{k=0}^\infty A_k (k+r)(k+r-1)x^{k+r-2}
\end{equation}

Rewriting \eqref{bessel diffeq}:

\begin{equation}
    x^2\sum_{k=0}^\infty A_k (k+r)(k+r-1)x^{k+r-2}+x\sum_{k=0}^\infty A_k (k+r)x^{k+r-1}+(x^2-n^2)\sum_{k=0}^\infty A_k x^{k+r} \nonumber
\end{equation}

\begin{equation}
    = \sum_{k=0}^\infty A_k ((k+r)^2-n^2)x^{k+r}+\sum_{k=2}^\infty A_{k-2} x^{k+r} = 0
\end{equation}

Letting $$k=0$$:

\begin{equation}
    A_0(r^2-n^2)x^r=0
\end{equation}

As $$x^r \neq 0$$ and $$A_0 \neq 0$$, we find $$r = n$$.
Letting $$k=1$$:

\begin{equation}
    A_1((1+n)^2-n^2)x^{1+r}=A_1(2n+1)x^{1+r}=0 \nonumber
\end{equation}

Therefore, $$A_1=0$$.

Letting $$K\geq2$$:

\begin{equation}
    (A_k((k+n)^2-n^2)+A_{k-2})x^{k+r}=0 \nonumber
\end{equation}

\begin{equation}
    A_k=-\frac{1}{k(k+2n)}A_{k-2}
\end{equation}

As $$A_1 = 0$$, for any odd $$k$$, $$A_k=0$$. So, $$k$$ must be even for $$A_k \neq 0$$, and we replace $$k$$ with $$2k$$:

\begin{equation}
    A_{2k}=-\frac{1}{2k(2k+2n)}A_{2k-2} \nonumber
\end{equation}

\begin{equation}
    A_{2k}=\frac{(-1)^2}{2k(2k-2)(2k+2n)(2k+2n-2)}A_{2k-4} \nonumber
\end{equation}

\begin{equation}
    A_{2k}=\frac{(-1)^2}{2^4k(k-1)(k+n)(k+n-1)}A_{2k-4} \nonumber
\end{equation}

\begin{equation}
    A_{2k}=\frac{(-1)^k}{2^{2k}k(k-1)...(1)(k+n)(k+n-1)...(n+1)}A_{0} \nonumber
\end{equation}

\begin{equation}
    A_{2k}=\frac{(-1)^k}{2^{2k}k!\frac{(k+n)!}{n!}}A_{0}
\end{equation}

We chose $$A_0=\frac{2^{-n}}{n!}$$ such that:

\begin{equation}
    A_{2k}=\frac{(-1)^k}{2^{n+2k}k!(k+n)!}
\end{equation}

Returning to \eqref{bessel power series}:

\begin{equation}
    J_n(x) = \sum_{k=0}^\infty A_{2k} x^{2k+n} \nonumber
\end{equation}

\begin{equation}
    J_n(x) = \sum_{k=0}^\infty \frac{(-1)^k}{2^{n+2k}k!(k+n)!} x^{2k+n} \nonumber
\end{equation}

\begin{equation}
    J_n(x) = \left(\frac{x}{2}\right)^n\sum_{k=0}^\infty \frac{(-1)^k}{k!(k+n)!} \left(\frac{x}{2}\right)^{2k}
\end{equation}

We note in particular for negative $$n$$, as our factorial terms cannot contain negative values:

\begin{equation}
    J_{-n}(x) = \left(\frac{x}{2}\right)^{-n}\sum_{k=n}^\infty \frac{(-1)^k}{k!(k-n)!} \left(\frac{x}{2}\right)^{2k} \nonumber
\end{equation}
\begin{equation} \label{bessel -n}
     = \left(\frac{x}{2}\right)^{-n}\sum_{k=0}^\infty \frac{(-1)^{k+n}}{(k+n)!((k+n)-n)!} \left(\frac{x}{2}\right)^{2(k+n)}=(-1)^nJ_n(x)
\end{equation}

We also note:

\begin{equation}
    J_{-n}(-x) = (-1)^n\left(\frac{-x}{2}\right)^n\sum_{k=0}^\infty \frac{(-1)^k}{k!(k+n)!} \left(\frac{-x}{2}\right)^{2k} \nonumber
\end{equation}

\begin{equation}
   = (-1)^n\left(\frac{x}{2}\right)^n\sum_{k=0}^\infty \frac{(-1)^k(-1)^{-n-2k}}{k!(k+n)!} \left(\frac{x}{2}\right)^{2k} = J_{n}(x)
\end{equation}

Let us evaluate our series expansion for a few values of $$n$$:

\begin{equation}
    J_0(x) = 1-\frac{x^2}{4}+\frac{x^4}{64}+\mathcal{O}(x^6)
\end{equation}

\begin{equation}
    J_1(x) = \frac{x}{2}-\frac{x^3}{16}+\frac{x^5}{384}+\mathcal{O}(x^7)
\end{equation}

\begin{equation}
    J_2(x) = \frac{x^2}{8}-\frac{x^4}{96}+\mathcal{O}(x^6)
\end{equation}

\begin{equation}
    J_3(x) = \frac{x^3}{48}-\frac{x^5}{768}+\mathcal{O}(x^7)
\end{equation}

### I.III Integral Representation of Bessel Function
Now we return to \eqref{bessel definition}. Let $$t = e^{i\theta}$$ such that:

\begin{equation}
    t-\frac{1}{t} = 2i\sin{\theta} \rightarrow e^{\frac{x}{2}\left(t-\frac{1}{t}\right)} = e^{ix\sin{\theta}} = \sum_{n=-\infty}^{\infty}J_n(x)e^{in\theta}
\end{equation}

So, $$J_n(x)$$ can represent the Fourier coefficients of $$e^{ix\sin{(\theta)}}$$, and therefore:

\begin{equation}
    J_n(x) = \frac{1}{2\pi} \int_0 ^{2\pi}{e^{-i(n\theta-x\sin{\theta})}d\theta} = \frac{1}{\pi} \int_0 ^{\pi}{\cos{\left(x\sin{\theta-n\theta}\right)}d\theta}
\end{equation}

## II. The Disturbing Function For the Three-Body Problem
We now analyse the disturbing function caused by the presence of a third body of mass $$m_2'$$. 
From Newton's Law, the motions of the three bodies are:

\begin{equation}
    \ddot{\vec{r}}_0' = \frac{\mathcal{G} m_1'}{\parallel \vec{r}_1' - \vec{r}_0' \parallel^3} \left( \vec{r}_1' - \vec{r}_0' \right) + \frac{\mathcal{G} m_2'}{\parallel \vec{r}_2' - \vec{r}_0' \parallel^3} \left( \vec{r}_2' - \vec{r}_0' \right)
\end{equation}

\begin{equation}
    \ddot{\vec{r}}_1' = - \frac{\mathcal{G} m_0'}{\parallel \vec{r}_1' - \vec{r}_0' \parallel^3} \left( \vec{r}_1' - \vec{r}_0' \right) + \frac{\mathcal{G} m_2'}{\parallel \vec{r}_2' - \vec{r}_1' \parallel^3} \left( \vec{r}_2' - \vec{r}_1' \right)
\end{equation}

\begin{equation}
    \ddot{\vec{r}}_2' = - \frac{\mathcal{G} m_0'}{\parallel \vec{r}_2' - \vec{r}_0' \parallel^3} \left( \vec{r}_2' - \vec{r}_0' \right) - \frac{\mathcal{G} m_1'}{\parallel \vec{r}_2' - \vec{r}_1' \parallel^3} \left( \vec{r}_2' - \vec{r}_1' \right)
\end{equation}

We first adjust our coordinate system, defining the centre of mass between $$m_0'$$ and $$m_1'$$, $$\vec{R}_1=\frac{m_0'\vec{r}_0'+m_1'\vec{r}_1'}{m_1}$$. Let $$\vec{R}_2=\vec{r}_2'-\vec{R}_1$$ be the vector from the $$m_0'$$, $$m_1'$$ centre of mass to $$m_2'$$. We write:
\begin{equation}
    \vec{r}_2 = \vec{r}_2' - \vec{r}_0' = \vec{R}_2 + \vec{R}_1 - \vec{r}_0' = \vec{R}_2 + \frac{m_1'}{m_1} \vec{r}_1 \nonumber
\end{equation}
\begin{equation}
    \vec{r}_2 - \vec{r}_1 = \vec{R}_2 + \vec{R}_1 - \vec{r}_1' = \vec{R}_2 - \frac{m_0'}{m_1} \vec{r}_1 \nonumber
\end{equation}
\begin{equation}
    \ddot{\vec{r}}_1 = \frac{\mathcal{G} m_1}{\parallel \vec{r}_1 \parallel^3} \vec{r}_1 + \frac{\mathcal{G} m_2'}{\parallel \vec{R}_2 - \frac{m_0'}{m_1} \vec{r}_1 \parallel^3} \left( \vec{R}_2 - \frac{m_0'}{m_1} \vec{r}_1 \right) - \frac{\mathcal{G} m_2'}{\parallel \vec{R}_2 + \frac{m_1'}{m_1} \vec{r}_1 \parallel^3} \left( \vec{R}_2 + \frac{m_1'}{m_1} \vec{r}_1 \right)
\end{equation}
\begin{equation}
    \ddot{\vec{R}}_2 = - \frac{\mathcal{G} m_1' \left( m_1 + m_2' \right)}{m_1 \parallel \vec{R}_2 - \frac{m_0'}{m_1} \vec{r}_1 \parallel^3} \left( \vec{R}_2 - \frac{m_0'}{m_1} \vec{r}_1 \right) - \frac{\mathcal{G} m_0' \left( m_1 + m_2' \right)}{m_1 \parallel \vec{R}_2 + \frac{m_1'}{m_1} \vec{r}_1 \parallel^3} \left( \vec{R}_2 + \frac{m_1'}{m_1} \vec{r}_1 \right)
\end{equation}
We write the Lagrangian of the system:
\begin{equation}
    \mathcal{L}=\frac{\mu_1}{2}\parallel\dot{\vec{r}}_1\parallel^2+\frac{m_1m_2'}{2\left(m_1+m_2'\right)}\parallel\dot{\vec{R}}_2\parallel^2+\frac{\mathcal{G}\mu_1m_1}{\parallel \vec{r}_1\parallel}+\frac{\mathcal{G}\mu_1m_1m_2'}{m_0'\parallel\vec{R}_2-\frac{m_0'}{m_1}\vec{r}_1\parallel}+\frac{\mathcal{G}\mu_1m_1m_2'}{m_1'\parallel \vec{R}_2+\frac{m_1'}{m_1}\vec{r}_1\parallel}
\end{equation}
From which we can write our three body Hamiltonian:

\begin{equation}\label{3 body hamiltonian}
    \mathcal{H}=\frac{1}{2\mu_1}\parallel{\vec{p}}_1\parallel^2+\frac{m_1+m_2'}{2m_1m_2'}\parallel{\vec{P}}_2\parallel^2-\frac{\mathcal{G}\mu_1m_1}{\parallel\vec{r}_1\parallel}-\frac{\mathcal{G}\mu_1m_1m_2'}{m_0'\parallel\vec{R}_2-\frac{m_0'}{m_1}\vec{r}_1\parallel}-\frac{\mathcal{G}\mu_1m_1m_2'}{m_1'\parallel \vec{R}_2+\frac{m_1'}{m_1}\vec{r}_1\parallel}
\end{equation}

Now we must isolate the disturbing function. First, we observe, via the law of cosines, we can write:

\begin{equation}\label{cosine 1/r expression}
    \frac{1}{\parallel\vec{q}-\vec{q}'\parallel}=\left(q^2+q'^2-2qq'\cos{\psi}\right)^{-\frac{1}{2}}
\end{equation}

Where $$\psi$$ is the angle between vectors $$\vec{q}$$ and $$\vec{q}'$$. We can write \eqref{cosine 1/r expression} as a power series using _Legendre Polynomials_, $$P_n$$:
\begin{equation}\label{legendre expansion}
    \frac{1}{\parallel\vec{q}-\vec{q}'\parallel}=\frac{1}{q}\left(1+t^2-2t\cos{\psi}\right)^{-\frac{1}{2}}=\frac{1}{q}\sum_{n=0}^\infty t^nP_n\left(\cos{\psi}\right)
\end{equation}
Where $$t=\frac{q'}{q}$$ is an expansion parameter. Here we do not study the $$P_n$$ polynomials, using them only as a tool in our calculations, the first few polynomials are:
\begin{equation}
    P_0\left(x\right) = 1 \nonumber
\end{equation}
\begin{equation}
    P_1\left(x\right) = x \nonumber
\end{equation}
\begin{equation}
    P_2\left(x\right) = \frac{1}{2} \left( 3x^2 - 1 \right) \nonumber
\end{equation}
\begin{equation}
    P_3\left(x\right) = \frac{1}{2} \left( 5x^3 - 3x \right) \nonumber
\end{equation}
\begin{equation}
    P_4\left(x\right) = \frac{1}{8} \left( 35x^4 - 30x^2 + 3 \right) \nonumber
\end{equation}
Using \eqref{legendre expansion}:
\begin{equation}
    \frac{\mathcal{G}\mu_1 m_1 m_2'}{m_0'\parallel \vec{R}_2 - \frac{m_0'}{m_1} \vec{r}_1\parallel } = \frac{\mathcal{G}\mu_1m_1m_2'}{R_2 m_0'} \sum _{n=1} ^\infty \left( \frac{m_0'}{m_1} \right)^n \left( \frac{r_1} {R_2} \right)^n P_n \left( \cos{\psi} \right)  
\end{equation}
\begin{equation}
    \frac{\mathcal{G}\mu_1m_1m_2'}{m_1'\parallel \vec{R}_2+\frac{m_1'}{m_1}\vec{r}_1\parallel} = \frac{\mathcal{G}\mu_1m_1m_2'}{R_2m_1'} \sum _{n=1}^\infty \left( -1 \right)^n \left( \frac{m_1'}{m_1} \right)^n \left( \frac{r_1}{R_2} \right)^n P_n \left( \cos{\psi} \right)
\end{equation}
We consider the case where $$m_0'>>m_1',m_2'$$, two planets orbiting a star. Defining $$\delta_1\equiv\frac{m_1'}{m_0'}$$ and $$\delta_2\equiv\frac{m_2'}{m_0'}$$, we expand to second order in $$\delta_i$$:
\begin{equation}
    \frac{\mathcal{G}\mu_1m_1m_2'}{R_2m_0'}\sum _{n=0} ^\infty\left(\frac{m _0'}{m _1 }\right)^n\left(\frac{r _1}{R _2}\right)^n P_n\left(\cos{\psi}\right)=\frac{\mathcal{G}m _0' ^2 }{R_2}\delta _1\delta _2\sum _{n=0}^\infty\left(\frac{r _1}{R _2}\right)^n P _n\left(\cos{\psi}\right)
\end{equation}
\begin{equation}
    \frac{\mathcal{G} \mu_1 m_1 m_2'}{R_2m_1'}\sum _{n=0} ^\infty \left(-1\right)^n\left(\frac{m _1'}{m _1}\right)^n\left(\frac{r _1}{R _2}\right)^n P_n \left(\cos{\psi}\right)=\frac{\mathcal{G}m_0' ^2}{R_2}\left(\delta_2-\left(\frac{r _1}{R _2}\right)P_1\left(\cos{\psi}\right)\delta _1 \delta _2\right)  
\end{equation}

Rewriting our Hamiltonian, \eqref{3 body hamiltonian}, using $$P_0$$ and $$P_1$$:

\begin{equation}
    \mathcal{H} = \frac{1}{2\mu_1} \parallel{\vec{p}}_1\parallel^2 + \frac{m_1 + m_2'}{2m_1 m_2'} \parallel{\vec{P}}_2\parallel^2 - \frac{\mathcal{G}\mu_1 m_1}{r_1} - \frac{\mathcal{G}m_1 m_2'}{R_2} - \frac{\mathcal{G}m_0'^2}{R_2} \delta_1 \delta_2 \sum _{n=2} ^\infty \left( \frac{r_1}{R_2} \right)^n P_n \left( \cos{\psi} \right)\nonumber
\end{equation}
\begin{equation}
    = \frac{1}{2\mu_1} \parallel{\vec{p}}_1\parallel^2 + \frac{m_1 + m_2'}{2m_1 m_2'} \parallel{\vec{P}}_2\parallel^2 - \frac{\mathcal{G}\mu_1 m_1}{r_1} - \frac{\mathcal{G}m_0' m_2'}{R_2} \nonumber
\end{equation}
\begin{equation}
    +\mathcal{G} m_0'^2 \delta_1 \delta_2 \left( -\left( r_1^2 + R_2^2 - 2r_1 R_2 \cos{\psi} \right)^{-\frac{1}{2}} + \frac{r_1}{R_2^2} \cos{\psi} \right) \label{3 body hamiltonian with R}
\end{equation}
The first four terms of \eqref{3 body hamiltonian with R} correspond to two separate two-body problems which we studied previously, and it is clear that the disturbing function is:
\begin{equation}\label{disturbing Function}
    \mathcal{R}=\mathcal{G}m_0'^2\delta_1\delta_2\left(-\left(r_1^2+R_2^2-2r_1R_2\cos{\psi}\right)^{-\frac{1}{2}}+\frac{r_1}{R_2^2}\cos{\psi}\right)
\end{equation}

### II.I Series Expansion of Disturbing Function

Defining the direct and indirect disturbing functions:

\begin{equation}
    \mathcal{R} = \mathcal{R}_D + \mathcal{R}_E \nonumber
\end{equation}

\begin{equation}
    \mathcal{R}_D \equiv -\mathcal{G} m_0'^2 \delta_1 \delta_2 \left( r_1^2 + R_2^2 - 2r_1 R_2 \cos{\psi} \right)^{-\frac{1}{2}} \nonumber
\end{equation}

\begin{equation}
    \mathcal{R}_E \equiv \mathcal{G} m_0'^2 \delta_1 \delta_2 \frac{r_1}{R_2^2} \cos{\psi} \nonumber
\end{equation}

Starting with an expansion of the direct disturbing function. Define:

\begin{equation}
    \frac{1}{\mathcal{F}}\equiv-\frac{\mathcal{R}_D}{\mathcal{G}m_0'^2\delta_1\delta_2}
\end{equation}

Now we define the following:

\begin{equation}
    \epsilon\equiv\cos{\psi}-\cos{\left(\vartheta_1-\vartheta_2\right)} \nonumber
\end{equation}

With $$\vartheta_i\equiv\varpi_i+f_i$$. Thus:
\begin{equation}
    \frac{1}{\mathcal{F}}=(r_1^2+R_2^2-2r_rR_2\cos{(\vartheta_1-\vartheta_2)}-2r_1R_2\epsilon)^{-\frac{1}{2}}
\end{equation}
We now expand around $$\epsilon=0$$:

\begin{equation}
    \frac{1}{\mathcal{F}} = \left( \frac{1}{\mathcal{F}_0} + r_1R_2\epsilon\frac{1}{\mathcal{F}_0^3}  + \frac{3}{2}(r_1R_2\epsilon)^2\frac{1}{\mathcal{F}_0^3} + ... \right) = \sum^{\infty} _{k = 0} \frac{(2k)!}{(k!)^2}\left(\frac{1}{2}r_1R_2\epsilon \right)^k\frac{1}{\mathcal{F}_0^{2k+1}}
\end{equation}

Where $$\mathcal{F}_0=\mathcal{F}\left(\epsilon=0\right)$$. We now expand $$\frac{1}{\mathcal{F}_0^{2k+1}}$$ around $$r_1=a$$ and $$R_2=a_2$$:

\begin{equation} \label{F_0 expansion}
    \frac{1}{\mathcal{F}_0^{2k+1}} = \frac{1}{\rho_0^{2k+1}} + (r_1-a_1)\frac{\partial }{\partial a_1}\left(\frac{1}{\rho_0^{2k+1}}\right)+ (R_2-a_2)\frac{\partial }{\partial a_2}\left(\frac{1}{\rho_0^{2k+1}}\right)+...
\end{equation}

Having defined:

\begin{equation}
    \rho_0\equiv\mathcal{F}_0(r_1=a_1,R_2=a_2)
\end{equation}

We now expand $$\frac{1}{\rho_0^{2k+1}}$$ as a Fourier Series:

\begin{equation}
    \frac{1}{\rho_0^{2k+1}} = (a_1^2 + a_2^2 - 2a_1a_2 \cos{\left( \vartheta_1 - \vartheta_2 \right)})^{-k - \frac{1}{2}} \nonumber
\end{equation}

\begin{equation}
    = a_2^{-2k-1} \left( 1 + \alpha^2 - 2\alpha \cos{\left( \vartheta_1 - \vartheta_2 \right)} \right)^{-k - \frac{1}{2}} \nonumber
\end{equation}

\begin{equation}
    = a_2^{-2k-1} \sum_{j=-\infty}^{\infty} b^{(j)}_{k + \frac{1}{2}}(\alpha) \cos{\left( j \left( \vartheta_1 - \vartheta_2 \right) \right)}
\end{equation}

Where $$\alpha=\frac{a_1}{a_2}$$. $$b^{(j)}_{s}$$ terms are known as _Laplace Coefficients_.

\begin{equation} \label{laplace coefficient definitions}
    b^{(j)}_{s}(\alpha) \equiv \frac{1}{2\pi}\int_0^{2\pi}\frac{\cos{(j{\phi})}d{\phi}}{\left(1+\alpha^2-2\alpha\cos{({\phi})}\right)^s}
\end{equation}

For convenience, we now define the operator $$A_{k,j,m,n}$$:
\begin{equation} \label{def A}
    A_{k,j,m,n} \equiv a_1^ma_2^n\frac{\partial ^{m+n}}{\partial a_1^m\partial a_2^n}\left(a_2^{-2k-1} b^{(j)}_{k+\frac{1}{2}}\right)
\end{equation}
We also define $$\zeta_i$$:
\begin{equation}
    \zeta_1\equiv\frac{r_1}{a_1}-1
\end{equation}
\begin{equation}
    \zeta_2\equiv\frac{R_2}{a_2}-1
\end{equation}
We use these to rewrite \eqref{F_0 expansion}:
\begin{equation}
    \frac{1}{ \mathcal{F} _0 ^{2k+1}} = \sum _{j=-\infty} ^\infty \left(A _{k,j,0,0}+\zeta _1 A _{k,j,1,0}+ \zeta _2 A _{k,j,0,1}+\frac{1}{2}\zeta _1 ^2 A _{k,j,2,0}+\frac{1}{2}\zeta _2^2 A _{k,j,0,2} + \zeta _1 
 \zeta _2 A _{k,j,1,1}+...\right)
\end{equation}
\begin{equation}
    \times\cos{\left(j(\vartheta_1-\vartheta_2)\right)} \nonumber
\end{equation}
We can now write $$\mathcal{R}_D$$ as product of two series:
\begin{equation}
    \mathcal{R}_D = -\mathcal{G} m_0' ^2 \delta_1 \delta_2 \sum _{k=0} ^{\infty} \frac{(2k!)}{(k!)^2}  \left(\frac{1}{2}\frac{r_1}{a_1}\frac{R_2}{a_2} \epsilon\right)^k a_1^k a_2^k \nonumber
\end{equation}  
\begin{equation}   
    \times \sum _{j=-\infty} ^\infty \left(A _{k,j,0,0} +\zeta _1 A _{k,j,1,0} + \zeta _2 A _{k,j,0,1} +\frac{1}{2} \zeta _1 ^2 A _{k,j,2,0} + \frac{1}{2} \zeta _2 ^2 A _{k,j,0,2}+\zeta_1 \zeta _2 A _{k,j,1,1}+...\right)  \nonumber
\end{equation}
\begin{equation}   \label{R_D expression} 
    \times \cos{\left(j(\vartheta _1 -\vartheta _2 )\right)}
\end{equation}

#### II.I.I Series Expansion of Orbital Elements

We now address the $$\cos{\left(j(\vartheta_1-\vartheta_2)\right)}$$ term. We expand trigonometric terms in $$E$$ using Bessel Functions in a power series of $$e$$. Let us write: 
\begin{equation} \label{exp E}
    e^{iE} = \sum_{n=-\infty}^{\infty}A_ne^{in\mathcal{M}}
\end{equation}
It follows, using a Fourier expansion:
\begin{equation}
    A_n = \frac{1}{2\pi}\int_{0}^{2\pi}{e^{iE}e^{-in\mathcal{M}}d\mathcal{M}} = \frac{1}{2\pi}\int_{0}^{2\pi}{e^{i(E-n\mathcal{M})}d\mathcal{M}}
\end{equation}
Using integration by parts:
\begin{equation}
\frac{1}{2\pi}\int_{0}^{2\pi}{e^{i(E-n\mathcal{M})}d\mathcal{M}} = \frac{1}{2\pi}\left.\left(-\frac{1}{in}e^{iE}e^{-in\mathcal{M}} \right)\right\vert_0^{2\pi}+\frac{1}{2\pi}\int_{0}^{2\pi}{\frac{1}{n}e^{-in\mathcal{M}}e^{iE}dE} \nonumber
\end{equation}
\begin{equation}
    = \frac{1}{2n\pi}\int_{0}^{2\pi}{e^{i(E-n\mathcal{M})}dE}
\end{equation}
And, using $$\mathcal{M} = E-e\sin{E}$$, we find:
\begin{equation}
    A_n = \frac{1}{2n\pi}\int_{0}^{2\pi}{e^{i(E-n\mathcal{M})}dE} = \frac{1}{2n\pi}\int_{0}^{2\pi}{e^{-i((n-1)E-ne\sin{E})}dE} = \frac{J_{n-1}(ne)}{n}
\end{equation}
We have used the integral definition of Bessel Functions. In the case of $$n=0$$, we use L'Hopital's rule and recall that $$J_{-1}\left(x\right) = -J_n\left(x\right)$$:
\begin{equation}
   A_0(ne) = \lim_{n \rightarrow 0} \frac{J_{-1}(ne)}{n} = \lim_{n \rightarrow 0} -e\frac{d}{d(ne)}\left( J_1 \left(ne\right) \right) = -\frac{e}{2}
\end{equation}
The real portion of \eqref{exp E} reveals:
\begin{equation}
    \cos{E} = \sum_{n=0}^{\infty}(A_n+A_{-n})\cos{n\mathcal{M}} = -\frac{e}{2}+ \sum_{n=1}^{\infty}\left(\frac{J_{n-1}(ne)-J_{-n-1}(-ne)}{n}\right)\cos{n\mathcal{M}} \nonumber
\end{equation}
\begin{equation}   
     = -\frac{e}{2}+ \sum_{n=1}^{\infty}\left(\frac{J_{n-1}(ne)-J_{n+1}(ne)}{n}\right)\cos{n\mathcal{M}}
\end{equation}
Likewise, with the imaginary portion:
\begin{equation}
    \sin{E} = \sum_{n=0}^{\infty}(A_n-A_{-n})\sin{n\mathcal{M}} = \sum_{n=1}^{\infty}\left(\frac{J_{n-1}(ne)+J_{-n-1}(-ne)}{n}\right)\sin{n\mathcal{M}}\nonumber
\end{equation}
\begin{equation} 
    = \sum_{n=1}^{\infty}\left(\frac{J_{n-1}(ne)+J_{n+1}(ne)}{n}\right)\sin{n\mathcal{M}}
\end{equation}
Now we use our series expansions for Bessel Functions:
\begin{equation}\label{cosE e expansion}
    \cos{E} = \cos{\mathcal{M}}+e\left(-\frac{1}{2}+\frac{1}{2}\cos{2\mathcal{M}} \right)+e^2\left(-\frac{3}{8}\cos{\mathcal{M}}+\frac{3}{8}\cos{3\mathcal{M}} \right)
\end{equation}
\begin{equation}
    +e^3\left(-\frac{1}{3}\cos{2\mathcal{M}}+\frac{1}{3}\cos{4\mathcal{M}} \right) + \mathcal{O}(e^4)\nonumber
\end{equation}
\begin{equation}
    \sin{E} = \sin{\mathcal{M}}+\frac{e}{2}\sin{2\mathcal{M}}+e^2\left(-\frac{1}{8}\sin{\mathcal{M}}+\frac{3}{8}\sin{3\mathcal{M}} \right)
\end{equation}
\begin{equation}
    +e^3\left(-\frac{1}{6}\sin{2\mathcal{M}}+\frac{1}{3}\sin{4\mathcal{M}} \right) + \mathcal{O}(e^4)\nonumber
\end{equation}
From the <a href="https://tlara1.github.io/projects/1_project/">definition of our orbital elements</a>, we find:

\begin{equation}
    E = \mathcal{M}+e\sin{E} = \mathcal{M}+e\sin{\mathcal{M}}+\frac{e^2}{2}\sin{2\mathcal{M}}+e^3\left(-\frac{1}{8}\sin{\mathcal{M}}+\frac{3}{8}\sin{3\mathcal{M}} \right)
\end{equation}
\begin{equation}
    +e^4\left(-\frac{1}{6}\sin{2\mathcal{M}}+\frac{1}{3}\sin{4\mathcal{M}} \right) + \mathcal{O}(e^5)\nonumber
\end{equation}
And:
\begin{equation}\label{zeta expansion e}
\frac{r}{a} = 1-e\cos{E} = 1-e\cos{\mathcal{M}}+e^2\left(\frac{1}{2}-\frac{1}{2}\cos{2\mathcal{M}} \right)
\end{equation}
\begin{equation}
+e^3\left(\frac{3}{8}\cos{\mathcal{M}}-\frac{3}{8}\cos{3\mathcal{M}} \right)+e^4\left(\frac{1}{3}\cos{2\mathcal{M}}-\frac{1
}{3}\cos{4\mathcal{M}} \right) + \mathcal{O}(e^5)\nonumber
\end{equation}
We can also easily get an expansion for $$\zeta_i$$.
\begin{equation}
    \dot{f} = \frac{na^2}{r^2} \sqrt{1-e^2} \nonumber
\end{equation}
\begin{equation}
    \dot{\mathcal{M}} = n \nonumber
\end{equation}
\begin{equation}
    \frac{r}{a} = 1 - e \cos{E} = \frac{d\mathcal{M}}{dE} \nonumber
\end{equation}
\begin{equation}
    \frac{df}{d\mathcal{M}} = \dot{f} \frac{dt}{d\mathcal{M}} = \frac{a^2}{r^2} \sqrt{1-e^2} = \sqrt{1-e^2} \left(\frac{dE}{d\mathcal{M}}\right)^2 \label{df dM eq}
\end{equation}
\begin{equation}
    \rightarrow f = \sqrt{1-e^2} \int_0^{\mathcal{M}} \left( \frac{dE}{d\bar{\mathcal{M}}} \right)^2 d\bar{\mathcal{M}}
\end{equation}
And carrying out the series expansions as done previously:
\begin{equation}
    \frac{dE}{d\mathcal{M}} = 1+e\cos{\mathcal{M}}+e^2\cos{2\mathcal{M}}+e^3\left(-\frac{1}{8}\cos{\mathcal{M}}+\frac{9}{8}\cos{3\mathcal{M}} \right)
\end{equation}
\begin{equation}
    +e^4\left(-\frac{1}{3}\cos{2\mathcal{M}}+\frac{4}{3}\cos{4\mathcal{M}} \right) + \mathcal{O}(e^5)\nonumber
\end{equation}
\begin{equation}
    \left(\frac{dE}{d\mathcal{M}}\right)^2 = 1+2e\cos{\mathcal{M}}+e^2 \left(\cos^2{(\mathcal{M})}+2\cos{2\mathcal{M}} \right)
\end{equation}
\begin{equation}
    +e^3\left(-\frac{1}{4}\cos{\mathcal{M}}+2\cos{\mathcal{M}}\cos{2\mathcal{M}}+\frac{9}{4}\cos{3\mathcal{M}} \right) + \mathcal{O}(e^4) \nonumber
\end{equation}
\begin{equation}
    f=  \sqrt{1-e^2}\mathcal{M}+2e\sqrt{1-e^2}\sin{\mathcal{M}}+\frac{e^2}{4}\sqrt{1-e^2}\left(5\sin{2\mathcal{M}}+2\mathcal{M} \right)
\end{equation}
\begin{equation}
    +\frac{1}{12}e^3\sqrt{1-e^2}\left(9\sin{\mathcal{M}}+13\sin{3\mathcal{M}}\right)+ \mathcal{O}(e^4)\nonumber
\end{equation}
To second order in $$e$$:
\begin{equation} \label{theta expansion in e}
    f = \mathcal{M}+2e\sin{\mathcal{M}}+\frac{5}{4}e^2\sin{2\mathcal{M}} + \mathcal{O}(e^3)
\end{equation}
We are ready to compute $$\sin{f}$$ and $$\cos{f}$$. Expanding to second order in $$e$$ and utilizing trigonometric identities:
\begin{equation} 
    \cos{f} = \frac{\cos{E}-e}{1-e\cos{E}} \simeq \cos{\mathcal{M}} + \left(-\frac{3}{2} + \frac{1}{2}\cos{2\mathcal{M}} + \cos^2{\mathcal{M}} \right)e \nonumber
\end{equation}
\begin{equation}
    + \frac{1}{2}\left(\frac{3}{4}\cos{3\mathcal{M}} + \cos{2\mathcal{M}}\cos{\mathcal{M}} - \frac{7}{4}\cos{\mathcal{M}} + \cos{\mathcal{M}} \left(-3 + \cos{2\mathcal{M}} + 2\cos^2{\mathcal{M}} \right) \right)e^2 \nonumber
\end{equation}
\begin{equation}\label{cos expansion e}
    \simeq \cos{\mathcal{M}} + \left(\cos{2\mathcal{M}} - 1\right)e + \left(\frac{9}{8}\cos{3\mathcal{M}} - \frac{9}{8}\cos{\mathcal{M}} \right)e^2
\end{equation}
To calculate $$\sin{f}$$ we need to be a little more subtle, we use \eqref{df dM eq}, the chain rule, and integrate:
\begin{equation}
    \frac{d\sin{f}}{d\mathcal{M}}=\frac{df}{d\mathcal{M}}\cos{\theta}=\sqrt{1-e^2}\left(\frac{dE}{d\mathcal{M}}\right)^2\cos{f} \nonumber
\end{equation}
\begin{equation}
    \sin{f}=\int_0^\mathcal{M}\sqrt{1-e^2}\left(\frac{dE}{d\bar{\mathcal{M}}}\right)^2\cos{f}d\bar{\mathcal{M}} \nonumber
\end{equation}  
To second order in $$e$$:
\begin{equation} 
    \sin{f} \simeq \sqrt{1-e^2}\int_0^\mathcal{M} \left( 1 + 2e\cos{\mathcal{M}} + e^2 \left(\cos^2{\mathcal{M}} + 2\cos{2\mathcal{M}}\right) \right) \nonumber
\end{equation}
\begin{equation}
    \quad \times \left( \cos{\mathcal{M}} + \left(\cos{2\mathcal{M}}-1\right)e + \left(\frac{9}{8}\cos{3\mathcal{M}} - \frac{9}{8}\cos{\mathcal{M}} \right)e^2 \right) d\mathcal{M} \nonumber
\end{equation}
\begin{equation}
    \simeq \sqrt{1-e^2}\left(\sin\mathcal{M} + 2\cos\mathcal{M}\sin\mathcal{M}e + \left(\frac{9}{2}\cos^{2}\mathcal{M}-\frac{3}{2}\right)\sin\left(\mathcal{M}\right)e^{2}\right) \nonumber
\end{equation}
\begin{equation} \label{sin expansion e}
    \simeq \sin\mathcal{M} + \sin2\mathcal{M}e + \left(\frac{9}{8}\sin3\mathcal{M}-\frac{7}{8}\sin\mathcal{M}\right)e^{2}
\end{equation}
Now, with double-angle relations:
\begin{equation} 
    \cos{(\omega + f)} = \cos{\omega}\cos{f} - \sin{\omega}\sin{f} \nonumber
\end{equation}
\begin{equation} 
    \simeq \cos{(\omega + \mathcal{M})} + \left(\cos{(\omega + 2\mathcal{M})} -\cos{\omega} \right)e \nonumber
\end{equation}
\begin{equation} \label{cos omega + f expansion}
    +\left(-\cos{(\omega + \mathcal{M})}-\frac{1}{8}\cos{(\omega - \mathcal{M})}+\frac{9}{8}\cos{(\omega + 3\mathcal{M})} \right)e^2
\end{equation}
\begin{equation} 
    \sin{(\omega + f)} = \sin{\omega}\cos{f} + \cos{\omega}\sin{f} \nonumber
\end{equation}
\begin{equation} 
    \simeq \sin{(\omega + \mathcal{M})} + \left(\sin{(\omega + 2\mathcal{M})} -\sin{\omega} \right)e \nonumber
\end{equation}
\begin{equation} \label{sin omega + theta expansion}
    +\left(-\sin{(\omega + \mathcal{M})}-\frac{1}{8}\sin{(\omega - \mathcal{M})}+\frac{9}{8}\sin{(\omega + 3\mathcal{M})} \right)e^2
\end{equation}
Now allow us to return to Cartesian coordinates with expansions around $$e$$. We assume that our inclinations are small, that $$I$$ is of order $$\mathcal{O}(e)$$.
\begin{equation}
    \cos{I} = 1-2\sin^2{\frac{I}{2}}
\end{equation}
\begin{equation}
    \sin{I} = 2\sin{\frac{I}{2}}\left(1-\sin^2{\frac{I}{2} }\right)^{\frac{1}{2}} = 2\sin{\frac{I}{2}} + \mathcal{O}\left(\sin^3{\frac{I}{2}}\right)
\end{equation}
Finally, to second order in $$e$$ and $$\sin{\frac{I}{2}}$$:
\begin{equation} 
    \frac{x}{r} \simeq \cos{\Omega}\left( \cos{(\omega + \mathcal{M})} + \left(\cos{(\omega + 2\mathcal{M})} -\cos{\omega} \right)e\right. \nonumber
\end{equation}
\begin{equation} 
    \left.+\left(-\cos{(\omega + \mathcal{M})}-\frac{1}{8}\cos{(\omega - \mathcal{M})}+\frac{9}{8}\cos{(\omega + 3\mathcal{M})} \right)e^2 \right) \nonumber
\end{equation}
\begin{equation} 
    -\sin{\Omega}\cos{I}\left( \sin{(\omega + \mathcal{M})} + \left(\sin{(\omega + 2\mathcal{M})} -\sin{\omega} \right)e\right. \nonumber
\end{equation}
\begin{equation} 
    \left.+\left(-\sin{(\omega + \mathcal{M})}-\frac{1}{8}\sin{(\omega - \mathcal{M})}+\frac{9}{8}\sin{(\omega + 3\mathcal{M})} \right)e^2 \right) \nonumber
\end{equation}
\begin{equation} 
    \simeq \cos{(\Omega+\omega +\mathcal{M})}+\left(\cos{(\Omega+\omega +2\mathcal{M})}-\cos{(\Omega+\omega)}\right)e \nonumber
\end{equation}
\begin{equation} 
    +\left(-\cos{(\Omega+\omega +\mathcal{M})}-\frac{1}{8}\cos{(\Omega+\omega-\mathcal{M})}+\frac{9}{8}\cos{(\Omega+\omega +3\mathcal{M})} \right)e^2 \nonumber
\end{equation}
\begin{equation} 
    +(1-\cos{I})\sin{\Omega} \sin{(\mathcal{M}+\omega)} \nonumber
\end{equation}
\begin{equation} 
    \simeq \cos{(\Omega+\omega +\mathcal{M})}+\left(\cos{(\Omega+\omega +2\mathcal{M})}-\cos{(\Omega+\omega)}\right)e \nonumber
\end{equation}
\begin{equation} 
    +\left(-\cos{(\Omega+\omega +\mathcal{M})}-\frac{1}{8}\cos{(\Omega+\omega-\mathcal{M})}+\frac{9}{8}\cos{(\Omega+\omega +3\mathcal{M})} \right)e^2 \nonumber
\end{equation}
\begin{equation}
    + \sin^2{\frac{I}{2}}\left(\cos{(-\Omega+\omega+\mathcal{M})}-\cos{(\Omega+\omega+\mathcal{M})} \right)
\end{equation}
\begin{equation} 
    \frac{y}{r} \simeq \sin{\Omega}\left( \cos{(\omega + \mathcal{M})} + \left(\cos{(\omega + 2\mathcal{M})} -\cos{\omega} \right)e\right. \nonumber
\end{equation} 
\begin{equation} 
    \left.+\left(-\cos{(\omega + \mathcal{M})}-\frac{1}{8}\cos{(\omega - \mathcal{M})}+\frac{9}{8}\cos{(\omega + 3\mathcal{M})} \right)e^2 \right) \nonumber
\end{equation}
\begin{equation} 
    +\cos{\Omega}\cos{I}\left( \sin{(\omega + \mathcal{M})} + \left(\sin{(\omega + 2\mathcal{M})} -\sin{\omega} \right)e\right. \nonumber
\end{equation}
\begin{equation} 
    \left.+\left(-\sin{(\omega + \mathcal{M})}-\frac{1}{8}\sin{(\omega - \mathcal{M})}+\frac{9}{8}\sin{(\omega + 3\mathcal{M})} \right)e^2 \right) \nonumber
\end{equation}
\begin{equation} 
    \simeq \sin{(\Omega+\omega +\mathcal{M})}+\left(\sin{(\Omega+\omega +2\mathcal{M})}-\sin{(\Omega+\omega)}\right)e \nonumber
\end{equation}
\begin{equation} 
    +\left(-\sin{(\Omega+\omega +\mathcal{M})}-\frac{1}{8}\sin{(\Omega+\omega-\mathcal{M})}+\frac{9}{8}\sin{(\Omega+\omega +3\mathcal{M})} \right)e^2 \nonumber
\end{equation}
\begin{equation} 
    +(1-\sin{I})\sin{\Omega} \sin{(\mathcal{M}+\omega)} \nonumber
\end{equation}
\begin{equation} 
    \simeq \sin{(\Omega+\omega +\mathcal{M})}+\left(\sin{(\Omega+\omega +2\mathcal{M})}-\sin{(\Omega+\omega)}\right)e \nonumber
\end{equation}
\begin{equation} 
    +\left(-\sin{(\Omega+\omega +\mathcal{M})}-\frac{1}{8}\sin{(\Omega+\omega-\mathcal{M})}+\frac{9}{8}\sin{(\Omega+\omega +3\mathcal{M})} \right)e^2 \nonumber
\end{equation}
\begin{equation}
    + \sin^2{\frac{I}{2}}\left(\sin{(-\Omega+\omega+\mathcal{M})}+\sin{(\Omega+\omega+\mathcal{M})} \right)
\end{equation}
\begin{equation} 
    \frac{z}{r} \simeq \sin{I}\left(\sin{(\omega+\mathcal{M})}+\left(\sin{(\omega+2\mathcal{M})}-\sin{\omega}\right)e\right. \nonumber
\end{equation}
\begin{equation} 
    \left.+\left(-\sin{(\omega+\mathcal{M})}-\frac{1}{8}\sin{(\omega-\mathcal{M})}+\frac{9}{8}\sin{(\omega+3\mathcal{M})} \right)e^2\right) \nonumber
\end{equation}
\begin{equation} 
    \simeq 2\sin{\frac{I}{2}}\sin{(\omega+\mathcal{M})}+2\sin{\frac{I}{2}}\left(\sin{(\omega+2\mathcal{M})}-\sin{\omega}\right)e
\end{equation}
We have all the tools we need to find a series representation for $$\cos{\psi}$$, to second order in $$e_1$$, $$I_1$$, $$e_2$$ and $$I_2$$:
\begin{equation}
    \vec{r}_1\cdot\vec{R}_2 = r_1R_2\cos{\psi} \rightarrow \cos{\psi}=\frac{x_1}{r_1}\frac{x_2}{R_2}+\frac{y_1}{r_1}\frac{y_2}{R_2}+\frac{z_1}{r_1}\frac{z_2}{R_2}
\end{equation}
Before rewriting, we recall $$\varpi=\omega +\Omega$$, and $$\lambda = \varpi +\mathcal{M}$$, expressing our expansions in terms of longitudes.
\begin{equation} 
    \frac{x_1}{r_1}\frac{x_2}{R_2} \simeq \cos{\lambda_1}\cos{\lambda_2}+\cos{\lambda_2}\left(\cos{(2\lambda_1-\varpi_1)}-\cos{\varpi_1}\right)e_1+\cos{\lambda_1}\left(\cos{(2\lambda_2-\varpi_2)}-\cos{\varpi_2}\right)e_2 \nonumber
\end{equation}
\begin{equation} 
    +\cos{\lambda_2}\left(-\cos{\lambda_1}-\frac{1}{8}\cos{(-\lambda_1+2\varpi_1)}+\frac{9}{8}\sin{(3\lambda_1-2\varpi_1)} \right)e_1^2 \nonumber
\end{equation}
\begin{equation} 
    +\cos{\lambda_1}\left(-\cos{\lambda_2}-\frac{1}{8}\cos{(-\lambda_2+2\varpi_2)}+\frac{9}{8}\sin{(3\lambda_2-2\varpi_2)} \right)e_2^2 \nonumber
\end{equation}
\begin{equation} 
    +\left(\cos{(2\lambda_1-\varpi_1)}-\cos{\varpi_1}\right)\left(\cos{(2\lambda_2-\varpi_2)}-\cos{\varpi_2}\right)e_1e_2 \nonumber
\end{equation}
\begin{equation} 
    + \cos{\lambda_2}\left(\cos{(\lambda_1-2\Omega_1)}-\cos{\lambda_1} \right)\sin^2{\frac{I_1}{2}}+ \cos{\lambda_1}\left(\cos{(\lambda_2-2\Omega_2)}-\cos{\lambda_2} \right)\sin^2{\frac{I_2}{2}}
\end{equation}
\begin{equation} 
    \frac{y_1}{r_1}\frac{y_2}{R_2} \simeq \sin{\lambda_1}\sin{\lambda_2}+\sin{\lambda_2}\left(\sin{(2\lambda_1-\varpi_1)}-\sin{\varpi_1}\right)e_1+\sin{\lambda_1}\left(\sin{(2\lambda_2-\varpi_2)}-\sin{\varpi_2}\right)e_2  \nonumber
\end{equation}
\begin{equation} 
    +\sin{\lambda_2}\left(-\sin{\lambda_1}-\frac{1}{8}\sin{(-\lambda_1+2\varpi_1)}+\frac{9}{8}\sin{(3\lambda_1-2\varpi_1)} \right)e_1^2  \nonumber
\end{equation}
\begin{equation} 
    +\sin{\lambda_1}\left(-\sin{\lambda_2}-\frac{1}{8}\sin{(-\lambda_2+2\varpi_2)}+\frac{9}{8}\sin{(3\lambda_2-2\varpi_2)} \right)e_2^2  \nonumber
\end{equation}
\begin{equation} 
    +\left(\sin{(2\lambda_1-\varpi_1)}-\sin{\varpi_1}\right)\left(\sin{(2\lambda_2-\varpi_2)}-\sin{\varpi_2}\right)e_1e_2  \nonumber
\end{equation}
\begin{equation} 
    + \sin{\lambda_2}\left(\sin{(\lambda_1-2\Omega_1)}+\sin{\lambda_1} \right)\sin^2{\frac{I_1}{2}}+ \sin{\lambda_1}\left(\sin{(\lambda_2-2\Omega_2)}+\sin{\lambda_2} \right)\sin^2{\frac{I_2}{2}}
\end{equation}
\begin{equation} 
    \frac{z_1}{r_1}\frac{z_2}{R_2} \simeq 4\sin{(\lambda_1-\Omega_1)}\sin{(\lambda_2-\Omega_2)}\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}
\end{equation}
Hence, 
\begin{equation} 
    \cos{\psi} \simeq \cos{(\lambda_1-\lambda_2)} + \cos{(\lambda_2-2\lambda_1+\varpi_1)}e_1-\cos{(\lambda_2-\varpi_1)}e_1 \nonumber
\end{equation}
\begin{equation} 
    + \cos{(\lambda_1-2\lambda_2+\varpi_2)}e_2-\cos{(\lambda_1-\varpi_2)}e_2 \nonumber
\end{equation}
\begin{equation} 
    -\cos{(\lambda_1-\lambda_2)}e_1^2-\frac{1}{8}\cos{(\lambda_1+\lambda_2-2\varpi_1)}e_1^2+\frac{9}{8}\cos{(3\lambda_1-\lambda_2-2\varpi_1)}e_1^2\nonumber
\end{equation}
\begin{equation} 
    -\cos{(\lambda_1-\lambda_2)}e_2^2-\frac{1}{8}\cos{(\lambda_1+\lambda_2-2\varpi_2)}e_2^2+\frac{9}{8}\cos{(3\lambda_2-\lambda_1-2\varpi_2)}e_2^2\nonumber
\end{equation}
\begin{equation} 
    +\cos{(2{\lambda_1}-2\lambda_2-\varpi_1+\varpi_2)}e_1e_2 - \cos{(2\lambda_1-\varpi_1-\varpi_2)}e_1e_2\nonumber
\end{equation}
\begin{equation} 
    - \cos{(2\lambda_2-\varpi_1-\varpi_2)}e_1e_2+\cos{(\varpi_1-\varpi_2)}e_1e_2\nonumber
\end{equation}
\begin{equation} 
    +\cos{(\lambda_1+\lambda_2-2\Omega_1)}\sin^2{\frac{I_1}{2}}-\cos{(\lambda_1+\lambda_2)}\sin^2{\frac{I_1}{2}}\nonumber
\end{equation}
\begin{equation} 
    +\cos{(\lambda_1+\lambda_2-2\Omega_2)}\sin^2{\frac{I_2}{2}}-\cos{(\lambda_1+\lambda_2)}\sin^2{\frac{I_2}{2}}\nonumber
\end{equation}
\begin{equation} 
    + 2\cos{(\lambda_1-\lambda_2-\Omega_1+\Omega_2)}\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}\nonumber
\end{equation}
\begin{equation} 
    - 2\cos{(\lambda_1+\lambda_2-\Omega_1-\Omega_2)}\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}} \label{cos psi expansion}
\end{equation}

Now we note that since the true longitude, $$\vartheta$$, describes a body's anomaly if its' inclination were zero, $$\cos{\left(\vartheta_1-\vartheta_2\right)}$$ can be found by setting the inclination terms of $$\cos{\psi}$$ to zero.

\begin{equation} 
    \cos{\left(\vartheta_1-\vartheta_2\right)} \simeq \cos{(\lambda_1-\lambda_2)} + \cos{(\lambda_2-2\lambda_1+\varpi_1)}e_1-\cos{(\lambda_2-\varpi_1)}e_1\nonumber
\end{equation}

\begin{equation} 
    + \cos{(\lambda_1-2\lambda_2+\varpi_2)}e_2-\cos{(\lambda_1-\varpi_2)}e_2\nonumber
\end{equation}

\begin{equation} 
    -\cos{(\lambda_1-\lambda_2)}e_1^2-\frac{1}{8}\cos{(\lambda_1+\lambda_2-2\varpi_1)}e_1^2+\frac{9}{8}\cos{(3\lambda_1-\lambda_2-2\varpi_1)}e_1^2\nonumber
\end{equation}

\begin{equation} 
    -\cos{(\lambda_1-\lambda_2)}e_2^2-\frac{1}{8}\cos{(\lambda_1+\lambda_2-2\varpi_2)}e_2^2+\frac{9}{8}\cos{(3\lambda_2-\lambda_1-2\varpi_2)}e_2^2\nonumber
\end{equation}

\begin{equation} 
    +\cos{(2{\lambda_1}-2\lambda_1-\varpi_1+\varpi_2)}e_1e_2 - \cos{(2\lambda_1-\varpi_1-\varpi_2)}e_1e_2\nonumber
\end{equation}

\begin{equation} 
    - \cos{(2\lambda_2-\varpi_1-\varpi_2)}e_1e_2+\cos{(\varpi_1-\varpi_2)}e_1e_2
\end{equation}


And, as $$\epsilon=\cos{\psi}-\cos{\left(\vartheta_1-\vartheta_2\right)}$$: 

\begin{equation}
    \epsilon \simeq \cos{(\lambda_1+\lambda_2-2\Omega_1)}\sin^2{\frac{I_1}{2}}-\cos{(\lambda_1+\lambda_2)}\sin^2{\frac{I_1}{2}}\nonumber
\end{equation}

\begin{equation}
    +\cos{(\lambda_1+\lambda_2-2\Omega_2)}\sin^2{\frac{I_2}{2}}-\cos{(\lambda_1+\lambda_2)}\sin^2{\frac{I_2}{2}}\nonumber
\end{equation}

\begin{equation}
    +2\cos{(\lambda_1-\lambda_2-\Omega_1+\Omega_2)}\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}\nonumber
\end{equation}

\begin{equation} \label{epsilon expansion}
    - 2\cos{(\lambda_1+\lambda_2-\Omega_1-\Omega_2)}\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}
\end{equation}


#### II.I.II Series Expansion of Direct Disturbing Function

With \eqref{zeta expansion e} and \eqref{epsilon expansion}:

\begin{equation}
    \frac{1}{2}\frac{r_1}{a_1}\frac{R_2}{a_2}\epsilon \simeq \frac{1}{2}\left(\cos{(\lambda_1+\lambda_2-2\Omega_1)} - \cos{(\lambda_1+\lambda_2)}\right)\sin^2{\frac{I_1}{2}} + \left(\cos{(\lambda_1+\lambda_2-2\Omega_2)} - \cos{(\lambda_1+\lambda_2)}\right)\sin^2{\frac{I_2}{2}}\nonumber
\end{equation}

\begin{equation}
\label{r/a and epsilon expansion}
    + \left(\cos{(\lambda_1-\lambda_2-\Omega_1+\Omega_2)} - \cos{(\lambda_1+\lambda_2-\Omega_1-\Omega_2)}\right)\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}
\end{equation}

As $$\frac{1}{2}\frac{r_1}{a_1}\frac{R_2}{a_2}\epsilon$$ is already of second order, we can ignore $$k>1$$ terms in \eqref{R_D expression}. Now we need an expansion for $$\cos{(j(\vartheta_1-\vartheta_2))}$$, where $$j$$ is an arbitrary integer. We start by noting:

\begin{equation}
    \cos{(j(\vartheta_1-\vartheta_2))} = \cos{(j(\varpi_1 + f_1))}\cos{(j(\varpi_2 + f_2))} + \sin{(j(\varpi_1 + f_1))}\sin{(j(\varpi_2 + f_2))}
\end{equation}

We use our \eqref{theta expansion in e} and expand:

\begin{equation}
    \cos{(j(\varpi+f))} \simeq \cos{\left(j\left(\varpi + \mathcal{M}+2e\sin{(\mathcal{M})}+\frac{5}{4}e^2\sin{(2\mathcal{M})} \right)\right)} \nonumber
\end{equation}

\begin{equation}
    \simeq \cos{\left(j\left(\varpi + \mathcal{M} \right)\right)} -2j\sin{\mathcal{M}}\sin{\left(j\left(\varpi + \mathcal{M} \right)\right)}e \nonumber
\end{equation}

\begin{equation}
    -2j^2 \sin^2{\mathcal{M}}\cos{\left(j\left(\varpi + \mathcal{M} \right)\right)}e^2-\frac{5}{4}j\sin{2\mathcal{M}}\sin{\left(j\left(\varpi + \mathcal{M} \right)\right)}e^2 \nonumber
\end{equation}

\begin{equation}
    \simeq \left(1-j^2e^2\right)\cos{j{\lambda}}+\left(\frac{1}{2}j^2e^2-\frac{5}{8}je^2 \right)\cos{((2-j){\lambda}-2\varpi)} \nonumber
\end{equation}

\begin{equation}
    +\left(\frac{1}{2}j^2e^2+\frac{5}{8}je^2 \right)\cos{((2+j){\lambda}-2\varpi)} \nonumber
\end{equation}

\begin{equation}
    -je\cos{((1-j){\lambda}-\varpi)}+je\cos{((1+j){\lambda}-\varpi)}
\end{equation}

\begin{equation}
    \sin{(j(\varpi+f))} \simeq \sin{\left(j\left(\varpi + \mathcal{M}+2e\sin{\mathcal{M}}+\frac{5}{4}e^2\sin{2\mathcal{M}} \right)\right)} \nonumber
\end{equation}

\begin{equation}
    \simeq \sin{\left(j\left(\varpi + \mathcal{M} \right)\right)} + 2j\sin{\mathcal{M}}\cos{\left(j\left(\varpi + \mathcal{M} \right)\right)}e \nonumber
\end{equation}

\begin{equation}
    -2j^2 \sin^2{\mathcal{M}}\sin{\left(j\left(\varpi + \mathcal{M} \right)\right)}e^2 + \frac{5}{4}j\sin{(2\mathcal{M})}\cos{\left(j\left(\varpi + \mathcal{M} \right)\right)}e^2 \nonumber
\end{equation}

\begin{equation}
    \simeq \left(1-j^2e^2\right)\sin{j{\lambda}}-\left(\frac{1}{2}j^2e^2-\frac{5}{8}je^2 \right)\sin{((2-j){\lambda}-2\varpi)} \nonumber
\end{equation}

\begin{equation}
    +\left(\frac{1}{2}j^2e^2+\frac{5}{8}je^2 \right)\sin{((2+j){\lambda}-2\varpi)} \nonumber
\end{equation}

\begin{equation}
    +je\sin{((1-j){\lambda}-\varpi)}+je\sin{((1+j){\lambda}-\varpi)}
\end{equation}

Expanding $$\cos{(j(\vartheta-\vartheta_2))}$$ to second order:

\begin{equation}
    \cos{(j(\vartheta_1-\vartheta_2))} \simeq \left(1-j^2e_1^2-j^2e_2^2 \right)\cos{(j({\lambda}_1-{\lambda}_2))}  \nonumber
\end{equation}

\begin{equation}
    +\left(\frac{1}{2}j^2e_1^2+\frac{5}{8}je^2 \right)\cos{((2+j){\lambda}_1-j{\lambda}_2-2\varpi_1)}  \nonumber
\end{equation}

\begin{equation}
    +\left(\frac{1}{2}j^2e_1^2-\frac{5}{8}je_1^2 \right)\cos{((2-j){\lambda}_1+j{\lambda}_2-2\varpi_1)}  \nonumber
\end{equation}

\begin{equation}
    +\left(\frac{1}{2}j^2e_2^2+\frac{5}{8}je_2^2 \right)\cos{(j{\lambda}_1-(2+j){\lambda}_2+2\varpi_2)}  \nonumber
\end{equation}

\begin{equation}
    +\left(\frac{1}{2}j^2e_2^2-\frac{5}{8}je_2^2 \right)\cos{(j{\lambda}_1+(2-j){\lambda}_2-2\varpi_2)}  \nonumber
\end{equation}

\begin{equation}
    +je_1\cos{((1+j){\lambda}_1-j{\lambda}_2-\varpi_1)} - je_1\cos{((1-j){\lambda}_1+j{\lambda}_2-\varpi_1)}  \nonumber
\end{equation}

\begin{equation}
    +je_2\cos{(j{\lambda}_1-(1+j){\lambda}_2+\varpi_2)} - je_2\cos{(j{\lambda}_1+(1-j){\lambda}_2-\varpi_2)}  \nonumber
\end{equation}

\begin{equation}
    -j^2e_1e_2\cos{((1+j){\lambda}+(1-j){\lambda}_2-\varpi_1-\varpi_2)}  \nonumber
\end{equation}

\begin{equation}
    -j^2e_1e_2\cos{((1-j){\lambda}_1+(1+j){\lambda}_2-\varpi_1-\varpi_2)}  \nonumber
\end{equation}

\begin{equation}
    +j^2e_1e_2\cos{((1+j){\lambda}_1-(1+j){\lambda}_2-\varpi_1-\varpi_2)}  \nonumber
\end{equation}

\begin{equation}
    +j^2e_1e_2\cos{((1-j){\lambda}_1-(1-j){\lambda}_2-\varpi_1-\varpi_2)} \label{cos vartheta expansion}
\end{equation}

We have all the ingredients to expand $$\mathcal{R}_D$$. From \eqref{r/a and epsilon expansion}, we omit $$k>1$$ terms and since $$\zeta_i$$ is first-order, we omit $$\mathcal{O}\left(\zeta^3\right)$$ terms. With \eqref{R_D expression}: 

\begin{equation} 
    \mathcal{R}_D \simeq-\frac{\mathcal{G}m_0'^2\delta_1 \delta _2} {a _2} \sum _{j=-\infty} ^\infty \left(a _2 A _{0,j,0,0} + a _2 \zeta _1 A _{0,j,1,0} + a _2 \zeta _2 A _{0,j,0,1} +\frac{1}{2}a _2\zeta _1 ^2 A _{0,j,2,0} \right. \nonumber
\end{equation}

\begin{equation}
    \left.+\frac{1}{2}a_2\zeta_2^2 A_{0,j,0,2}+a_2\zeta_1 \zeta_2A_{0,j,1,1}+\frac{r_1}{a_1}\frac{R_2}{a_2}\epsilon a_1a_2^2A_{1,j,0,0}\right)\cos{\left(j(\vartheta_1-\vartheta_2)\right)} \nonumber
\end{equation}

\begin{equation} \label{RDj expression}
    =-\frac{\mathcal{G}m_0'^2\delta_1\delta_2}{a_2}\sum_{j=-\infty}^\infty\mathcal{R}_D^{(j)}
\end{equation}

Using our definition of $$A_{k,j,m,n}$$ \eqref{def A}, transforming derivatives with respect to $$\alpha$$ because $$b^{(j)}_s$$ is a function of $$\alpha$$:

\begin{equation}
    a_2A_{0,j,0,0} = b^{(j)}_{\frac{1}{2}}(\alpha) \nonumber
\end{equation}

\begin{equation}
    a_2A_{0,j,1,0} = \alpha \frac{\partial }{\partial\alpha}\left(b^{(j)}_{\frac{1}{2}}(\alpha)\right) \nonumber
\end{equation}

\begin{equation}
    a_2A_{0,j,0,1} = a_2\frac{\partial }{\partial a_2}\left(b^{(j)} _{\frac{1}{2}} (\alpha)\right) -b^{(j)} _{\frac{1}{2}} (\alpha) = -\alpha\frac{\partial }{\partial\alpha}\left(b^{(j)} _{\frac{1}{2}} (\alpha)\right)-b^{(j)} _{\frac{1}{2}}(\alpha) \nonumber
\end{equation}

\begin{equation}
    a_2A_{0,j,2,0} = \alpha^2 \frac{\partial ^2}{\partial\alpha^2}\left(b^{(j)}_{\frac{1}{2}}(\alpha)\right) \nonumber
\end{equation}

\begin{equation}
    a_2A_{0,j,0,2} = a_2^3 \frac{\partial }{\partial a_2} \left(a_2^{-1} \frac{\partial }{\partial a_2}\left(b^{(j)}_{\frac{1}{2}}(\alpha)\right)-a_2^{-2}b^{(j)} _{\frac{1}{2}} (\alpha) \right) = \alpha^2\frac{\partial ^2}{\partial\alpha^2}\left(b^{(j)} _{\frac{1}{2}}(\alpha)\right) +4\alpha\frac{\partial }{\partial\alpha} \left(b^{(j)} _{\frac{1}{2}} (\alpha)\right)+2b^{(j)} _{\frac{1}{2}}(\alpha) \nonumber
\end{equation}

\begin{equation}
    a_2A_{0,j,1,1} = -\alpha^2\frac{\partial ^2}{\partial\alpha^2}\left(b^{(j)} _{\frac{1}{2}}(\alpha)\right)-2\alpha\frac{\partial }{\partial\alpha}\left(b^{(j)} _{\frac{1}{2}}(\alpha)\right) \nonumber
\end{equation}

\begin{equation}
    a_1a_2^2A_{1,j,0,0} = \alpha b^{(j)}_{\frac{3}{2}}(\alpha) \nonumber
\end{equation}

What follows is a hefty quantity of tedious algebra, using \eqref{epsilon expansion}, \eqref{r/a and epsilon expansion}, and \eqref{cos vartheta expansion}. We expand \eqref{RDj expression} to 2nd order in $$e_i$$ and $$\sin{\frac{I_i}{2}}$$.
We also recall the trigonometric identity: $$\cos{a}\cos{b}=\frac{1}{2}\cos{(a+b)}+\frac{1}{2}\cos{(a-b)}$$. We write $$\mathcal{R}_D^{(j)}=\mathcal{R}_D^{(j)(0)}+\mathcal{R}_D^{(j)(1)}+\mathcal{R}_D^{(j)(2)}$$, categorizing terms by the sum of the coefficients of $${\lambda_1}$$ and $${\lambda_2}$$.

\begin{equation}
    \mathcal{R}_D^{(j)(0)} \simeq \left( 1+\frac{1}{4}(e_1^2+e_2^2)\left(-4j^2+2\alpha\frac{\partial }{\partial\alpha}+\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{(j({\lambda_1}-\lambda_2))} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{4}e _1 e _2\left(2j+4j^2-2\alpha\frac{\partial }{\partial\alpha}-\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1+j){\lambda_1}-(1+j)\lambda_2-\varpi_1+\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{4}e _1 e _2\left(-2j+4j^2-2\alpha\frac{\partial }{\partial\alpha}-\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}-(1-j)\lambda_2-\varpi_1+\varpi _2)} \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{2}\left(\sin^2{\frac{I_1}{2}}+\sin^2{\frac{I_2}{2}} \right)\alpha b^{(j)} _{\frac{3}{2}}(\alpha)\cos{((1+j){\lambda_1}-(1+j)\lambda_2)} \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{2}\left(\sin^2{\frac{I_1}{2}}+\sin^2{\frac{I_2}{2}} \right)\alpha b^{(j)} _{\frac{3}{2}}(\alpha)\cos{((1-j){\lambda_1}-(1-j)\lambda_2)} \nonumber
\end{equation}

\begin{equation}
    +\sin{\frac{I _1}{2}} \sin{\frac{I_2}{2}}\alpha b^{(j)} _{\frac{3}{2}}(\alpha)\cos{((1+j){\lambda_1}-(1+j)\lambda_2-\Omega_1+\Omega_2)} \nonumber
\end{equation}

\begin{equation}
    +\sin{\frac{I _1}{2}} \sin{\frac{I_2}{2}}\alpha b^{(j)} _{\frac{3}{2}}(\alpha)\cos{((1-j){\lambda_1}-(1-j)\lambda_2-\Omega_1+\Omega_2)}
\end{equation}

\begin{equation}
    \mathcal{R} _D^{(j)(1)} \simeq \frac{1}{2}e _1\left(2j-\alpha\frac{\partial }{\partial\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1+j){\lambda_1}-j\lambda_2-\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{2}e_1\left(2j+\alpha\frac{\partial }{\partial\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}+j\lambda_2-\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}e_2\left(1+2j+\alpha\frac{\partial }{\partial\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}-(1+j)\lambda_2+\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}e_2\left(1-2j+\alpha\frac{\partial }{\partial\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}+(1-j)\lambda_2-\varpi_2)}
\end{equation}


\begin{equation}
    \mathcal{R} _D^{(j)(2)} \simeq \frac{1}{8}e_1^2\left(5j+4j^2-2\alpha\frac{\partial }{\alpha}-4j\alpha\frac{\partial }{\alpha}+\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((2+j){\lambda_1}-j\lambda_2-2\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{8}e_1^2\left(-5j+4j^2-2\alpha\frac{\partial }{\partial\alpha}+4j\alpha\frac{\partial }{\partial\alpha}+\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{((2-j){\lambda_1}+j\lambda_2-2\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{4}e_1e_2\left(2j-4j^2-2\alpha\frac{\partial }{\partial\alpha}+4j\alpha\frac{\partial }{\partial\alpha}-\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{((1+j){\lambda_1}+(1-j)\lambda_2-\varpi_1-\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{4}e_1e_2\left(2j+4j^2+2\alpha\frac{\partial }{\partial\alpha}+4j\alpha\frac{\partial }{\partial\alpha}+\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}+(1+j)\lambda_2-\varpi_1-\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{8}e_2^2\left(4+9j+4j^2+6\alpha\frac{\partial }{\partial\alpha}+4j\alpha\frac{\partial }{\partial\alpha}+\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}-(2+j)\lambda_2+2\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{8}e_2^2\left(4-9j+4j^2+6\alpha\frac{\partial }{\partial\alpha}-4j\alpha\frac{\partial }{\partial\alpha}+\alpha^2\frac{\partial ^2}{\partial\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}+(2-j)\lambda_2-2\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}\sin^2{\frac{I_1}{2}}\alpha b^{(j)}_{\frac{3}{2}}(\alpha)\cos{((1-j){\lambda_1}+(1+j)\lambda_2-2\Omega_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}\sin^2{\frac{I_1}{2}}\alpha b^{(j)}_{\frac{3}{2}}(\alpha)\cos{((1+j){\lambda_1}+(1-j)\lambda_2-2\Omega_1)} \nonumber
\end{equation}

\begin{equation}
    -\sin{\frac{I_1}{2}} \sin{\frac{I_2}{2}}\alpha b^{(j)}_{\frac{3}{2}}(\alpha)\cos{((1-j){\lambda_1}+(1+j)\lambda_2-\Omega_1-\Omega_2)} \nonumber
\end{equation}

\begin{equation}
    -\sin{\frac{I_1}{2}} \sin{\frac{I_2}{2}}\alpha b^{(j)}_{\frac{3}{2}}(\alpha)\cos{((1+j){\lambda_1}+(1-j)\lambda_2-\Omega_1-\Omega_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}\sin^2{\frac{I_2}{2}}\alpha b^{(j)}_{\frac{3}{2}}(\alpha)\cos{((1-j){\lambda_1}+(1+j)\lambda_2-2\Omega_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}\sin^2{\frac{I_2}{2}}\alpha b^{(j)}_{\frac{3}{2}}(\alpha)\cos{((1+j){\lambda_1}+(1-j)\lambda_2-2\Omega_2)}
\end{equation}

These equations can be simplified further, notice that all the terms come in pairs, and since our sum of $$j$$ is from $$-\infty$$ to $$\infty$$, we can perform arbitrary index changes $$j \rightarrow \pm j \pm k$$. This allows us to combine terms and reduce from $$23$$ to $$11$$ arguments. 

\begin{equation}
    \mathcal{R}_D^{(j)(0)} \simeq \left( 1+\frac{1}{4}(e_1^2+e_2^2)\left(-4j^2+2\alpha\frac{\partial }{\partial \alpha}+\alpha^2\frac{\partial ^2}{\partial \alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\right) \nonumber
\end{equation}

\begin{equation}
    \left.-\frac{1}{2}\alpha\left(\sin^2{\frac{I _1}{2}}+\sin^2{\frac{I _2}{2}} \right)\left(b^{(j-1)} _{\frac{3}{2}}(\alpha)+b^{(j+1)} _{\frac{3}{2}}(\alpha) \right)\right)\cos{(j({\lambda _1}-\lambda _2))} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}e_1e_2\left(2+6j+4j^2-2\alpha\frac{\partial }{\partial \alpha}-\alpha^2\frac{\partial ^2}{\partial \alpha^2}\right)b^{(j+1)}_{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}-j\lambda_2-\varpi_1+\varpi_2)} \nonumber
\end{equation}

\begin{equation} \label{RD0}
    +2\sin{\frac{I_1}{2}} \sin{\frac{I_2}{2}}\alpha b^{(j+1)}_{\frac{3}{2}}(\alpha)\cos{(j{\lambda_1}-j\lambda_2-\Omega_1+\Omega_2)}
\end{equation}

\begin{equation} 
    \mathcal{R}_D^{(j)(1)} \simeq -e_1\left(2j+\alpha\frac{\partial }{\partial \alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}+j\lambda_2-\varpi_1)} \nonumber
\end{equation}

\begin{equation} \label{RD1}
    +e_2\left(1-2j+\alpha\frac{\partial }{\partial \alpha} \right)b^{(j-1)}_{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}+j\lambda_2-\varpi_2)}
\end{equation}

\begin{equation} 
    \mathcal{R}_D^{(j)(2)} \simeq \frac{1}{4}e_1^2\left(-5j+4j^2-2\alpha\frac{\partial }{\partial \alpha}+4j\alpha\frac{\partial }{\partial \alpha}+\alpha^2\frac{\partial ^2}{\partial \alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((2+j){\lambda_1}+j\lambda_2-2\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}e_1e_2\left(-2+6j-4j^2+2\alpha\frac{\partial }{\partial \alpha}-4j\alpha\frac{\partial }{\partial \alpha}-\alpha^2\frac{\partial ^2}{\partial \alpha^2}\right)b^{(j-1)}_{\frac{1}{2}}(\alpha)\cos{((2-j){\lambda_1}+j\lambda_2-\varpi_1-\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{4}e_2^2\left(2-7j+4j^2-2\alpha\frac{\partial }{\partial \alpha}+4j\alpha\frac{\partial }{\partial \alpha}-\alpha^2\frac{\partial ^2}{\partial \alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{((2-j){\lambda_1}+j\lambda_2-2\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\sin^2{\frac{I_1}{2}}\alpha b^{(j-1)}_{\frac{3}{2}}(\alpha)\cos{((2-j){\lambda_1}+j\lambda_2-2\Omega_1)} \nonumber
\end{equation}

\begin{equation}
    -2\sin{\frac{I_1}{2}} \sin{\frac{I_2}{2}}\alpha b^{(j-1)}_{\frac{3}{2}}(\alpha)\cos{((2-j){\lambda_1}+j\lambda_2-\Omega_1-\Omega_2)} \nonumber
\end{equation}

\begin{equation} \label{RD2}
    +\frac{1}{2}\sin^2{\frac{I_2}{2}}\alpha b^{(j-1)}_{\frac{3}{2}}(\alpha)\cos{((2-j){\lambda_1}+j\lambda_2-2\Omega_2)}
\end{equation}



#### II.I.III Series Expansion of Indirect Disturbing Function

The indirect portion of the disturbing function is much less involved. Rewriting the indirect portion:

\begin{equation}
    \mathcal{R}_E=\mathcal{G}m_0'^2\delta_1\delta_2\frac{\alpha}{a_2}\frac{r_1}{a_1}\left(\frac{a_2}{R_2}\right)^2\cos{\psi}
\end{equation}

We expand in the same way we expanded $$\mathcal{R}_D$$. First, via \eqref{cosE e expansion}:

\begin{equation}
    \left(\frac{a_2}{R_2}\right)^2 = \left(\frac{1}{1-e_2\cos{E_2}}\right)^2 \simeq 1+2\cos{\mathcal{M}_2}e_2+\left(3\cos^2{\mathcal{M}_2}+\cos{2\mathcal{M_2}}-1\right)e_2^2 \nonumber
\end{equation}

\begin{equation}
    \simeq 1+2\cos{(\lambda_2-\varpi_2)}e_2+\frac{1}{2}\left(5\cos{(2(\lambda_2-\varpi_2))}+1\right)e_2^2 
\end{equation}

And consulting \eqref{zeta expansion e} and \eqref{cos psi expansion}:

\begin{equation}
     \frac{\mathcal{R}_Ea_2}{\mathcal{G}m_0'^2\delta_1\delta_2\alpha} \simeq \frac{1}{2}\left(-2+e_1^2+e_2^2+2\sin^2{\frac{I_1}{2}}+2\sin^2{\frac{I_2}{2}}\right) \cos{(\lambda_1-\lambda_2)}
    -\frac{1}{2}e_1\cos{(2\lambda_1-\lambda_2-\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{3}{2}e_1\cos{(\lambda_2-\varpi_1)}-2e_2\cos{(\lambda_1-2\lambda_2+\varpi_2)} 
    -e_1e_2\cos{(2\lambda_1-\lambda_2-\varpi_1+\varpi_2)}+3e_1e_2\cos{(2\lambda_1-\varpi_1-\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{8}e_1^2\cos{(\lambda_1+\lambda_2-2\varpi_1)}-\frac{3}{8}e_1^2\cos{(3\lambda_1-\lambda_2-2\varpi_1)}
    -\frac{1}{8}e_2^2\cos{(\lambda_1+\lambda_2-2\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    -\frac{27}{8}e_2^2\cos{(\lambda_1-3\lambda_2+2\varpi_2)} -2\sin^2{\frac{I_1}{2}}\cos{(\lambda_1+\lambda_2-2\Omega_1)}
    -2\sin^2{\frac{I_2}{2}}\cos{(\lambda_1+\lambda_2-2\Omega_2)} \nonumber
\end{equation}

\begin{equation}
    +2\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}\cos{(\lambda_1+\lambda_2-\Omega_1-\Omega_2)} -2\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}\cos{(\lambda_1-\lambda_2-\Omega_1+\Omega_2)}   \nonumber 
\end{equation}





### II.II Using the Disturbing Function

From our Planetary Equations, the time variations in our orbital elements (excluding the orbital $$\lambda$$ changes from the non-perturbed Hamiltonian) are proportional to $$\sim\frac{1}{\mu_1\sqrt{\mathcal{G}m_1a_1}}\frac{\partial R}{\partial i}$$, so from our disturbing function, the time variation in our elements is $$\sim\frac{\sqrt{\mathcal{G}}m_1'm_2'}{\mu_1R_2\sqrt{m_1a_1}}=\frac{\sqrt{\mathcal{G}m_1}\delta_2}{R_2\sqrt{a_1}}\approx n\delta_2$$, where we have approximated $$R_2\approx a_1$$, which is reasonable in our proportionality arguments. Thus, our orbital elements vary $$\sim\delta_2$$ times slower than the orbital period. We call these elements _secular_, varying much slower than planetary orbits, so, to evaluate the impact of our Disturbing Function, we can average over the orbital cycles of $$\lambda_1$$ and $$\lambda_2$$.

\begin{equation}
    \langle\langle\mathcal{R}\rangle\rangle=\frac{1}{4\pi^2}\int_0^{2\pi}\int_0^{2\pi}\mathcal{R}d\lambda_1d\lambda_2
\end{equation}

As all the terms in our disturbing function feature trigonometric terms of $$\lambda_1$$ and $$\lambda_2$$. It is only terms without these angles that remain post-averaging. The only contributing term is $$\mathcal{R} _D
^{(0)(0)}$$:

\begin{equation}
    -\langle\langle\frac{a_2\mathcal{R}}{\mathcal{G}m_0'^2\delta_1\delta _2}\rangle\rangle = -\frac{a_2\mathcal{R} _D^{(0)(0)}}{\mathcal{G}m _0'^2\delta _1\delta_2} \simeq b^{(0)} _{\frac{1}{2}}(\alpha) + \frac{1}{4}(e_1^2 + e_2^2) \left( 2\alpha \frac{\partial }{\partial\alpha} + \alpha^2 \frac{\partial ^2}{\partial\alpha^2} \right) b^{(0)} _{\frac{1}{2}}(\alpha) \nonumber
\end{equation}

\begin{equation}
    -\alpha \left( \sin^2{\frac{I_1}{2}} + \sin^2{\frac{I_2}{2}} \right) b^{(1)}_{\frac{3}{2}}(\alpha) \nonumber
\end{equation}

\begin{equation}
    + \frac{1}{2} e_1 e_2 \left( 2 - 2\alpha \frac{\partial }{\partial\alpha} - \alpha^2 \frac{\partial ^2}{\partial\alpha^2} \right) b^{(1)}_{\frac{1}{2}}(\alpha) \cos{(\varpi_1 - \varpi_2)} \nonumber
\end{equation}

\begin{equation}
    + 2 \sin{\frac{I_1}{2}} \sin{\frac{I_2}{2}} \alpha b^{(1)}_{\frac{3}{2}}(\alpha) \cos{(\Omega_1 - \Omega_2)}
\end{equation}


We have made use of the fact that $$b_s^{(-j)}(\alpha)=b_s^{(j)}(\alpha)$$. With the properties of Laplace coefficients, which can be derived from \eqref{laplace coefficient definitions}:

\begin{equation}
    \left( 2\alpha \frac{\partial }{\partial\alpha} + \alpha^2 \frac{\partial ^2}{\partial\alpha^2} \right) b^{(0)} _{\frac{1}{2}}(\alpha) = \alpha b^{(1)} _{\frac{3}{2}}(\alpha) \nonumber
\end{equation}

\begin{equation}
    \left( 2 - 2\alpha \frac{\partial }{\partial\alpha} - \alpha^2 \frac{\partial ^2}{\partial\alpha^2} \right) b^{(0)} _{\frac{1}{2}}(\alpha) = -\alpha b^{(2)} _{\frac{3}{2}}(\alpha)
\end{equation}

And, taking $$\sin{I_i}\simeq I_i$$:

\begin{equation}
    -\langle\langle \frac{a_2 \mathcal{R}}{\mathcal{G} m_0'^2 \delta_1 \delta_2} \rangle \rangle \simeq b^{(0)} _{\frac{1}{2}}(\alpha) + \frac{1}{4} (e_1^2 + e_2^2) \alpha b^{(1)} _{\frac{3}{2}}(\alpha) - \frac{1}{4} (I_1^2 + I_2^2) \alpha b^{(1)} _{\frac{3}{2}}(\alpha) \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{2} e_1 e_2 \alpha b^{(2)}_{\frac{3}{2}}(\alpha) \cos{(\varpi_1 - \varpi_2)} + \frac{1}{2} I_1 I_2 \alpha b^{(1)} _{\frac{3}{2}}(\alpha) \cos{(\Omega_1 - \Omega_2)}
\end{equation}

Now in terms of our simplifying variables which we described in <a href="https://tlara1.github.io/projects/1_project/">our derivation of the Lagrange Planetary Equations</a>:

\begin{equation}
    \langle\langle \mathcal{R} \rangle \rangle \simeq -\frac{\mathcal{G} m_0'^2 \delta_1 \delta_2}{a_2} \alpha \left( \frac{1}{4} \left( h_1^2 + h_2^2 + k_1^2 + k_2^2 \right) b^{(1)} _{\frac{3}{2}}(\alpha) - \frac{1}{4} \left( p_1^2 + p_2^2 + q_1^2 + q_2^2 \right) b^{(1)} _{\frac{3}{2}}(\alpha) \right)
\end{equation}

\begin{equation}
    \left. - \frac{1}{2} \left( h_1 h_2 + k_1 k_2 \right) b^{(2)}_{\frac{3}{2}}(\alpha) + \frac{1}{2} \left( p_1 p_2 + q_1 q_2 \right) b^{(1)} _{\frac{3}{2}}(\alpha) \right)
\end{equation}

Because we are assuming $$\alpha$$ is constant (recall that variations in $$a_i$$ are much slower than those for other secular elements), we have omitted the $$b^{(0)} _{\frac{1}{2}}\left(\alpha\right)$$ term. Our evolution equations for our simplified elements are:

\begin{equation}
    \dot{h}_1 = \frac{n_1 \alpha^2}{2} \delta_2 \left( k_1 b^{(1)} _{\frac{3}{2}} - k_2 b^{(2)} _{\frac{3}{2}} \right)
\end{equation}

\begin{equation}
    \dot{k}_1 = -\frac{n_1 \alpha^2}{2} \delta _2 \left( h_1 b^{(1)} _{\frac{3}{2}} - h_2 b^{(2)} _{\frac{3}{2}} \right)
\end{equation}

\begin{equation}
    \dot{p}_1 = \frac{n_1 \alpha^2}{2} \delta _2 \left( -q_1 b^{(1)} _{\frac{3}{2}} + q_2 b^{(1)} _{\frac{3}{2}} \right)
\end{equation}

\begin{equation}
    \dot{q}_1 = -\frac{n _1 \alpha^2}{2} \delta _2 \left( -p_1 b^{(1)} _{\frac{3}{2}} + p_2 b^{(1)} _{\frac{3}{2}} \right)
\end{equation}


We can use \eqref{3 body hamiltonian with R} to do something similar for $$m_2'$$, identifying $$\mu_2=\frac{m_0'm_2'+m_1'm_2'}{m_0'+m_1'+m_2'}$$ and $$m_2=\frac{m_0'm_2'}{\mu_2}$$ as the variables to utilize in our evolution equations:

\begin{equation}
    \dot{h}_2 = \sqrt{\frac{\mathcal{G}m_2}{a_2^3}} \alpha \delta_1 \left( k_2 b^{(1)} _{\frac{3}{2}} - k_1 b^{(2)} _{\frac{3}{2}} \right)
\end{equation}

\begin{equation}
    \dot{k}_2 = -\sqrt{\frac{\mathcal{G}m_2}{a_2^3}} \alpha \delta_1 \left( h_2 b^{(1)} _{\frac{3}{2}} - h_1 b^{(2)} _{\frac{3}{2}} \right)
\end{equation}

\begin{equation}
    \dot{p}_2 = \sqrt{\frac{\mathcal{G}m_2}{a_2^3}} \alpha \delta_1 \left( -q_2 b^{(1)} _{\frac{3}{2}} + q_1 b^{(1)} _{\frac{3}{2}} \right)
\end{equation}

\begin{equation}
    \dot{q}_2 = -\sqrt{\frac{\mathcal{G}m_2}{a_2^3}} \alpha \delta_1 \left( -p_2 b^{(1)} _{\frac{3}{2}} + p_1 b^{(1)} _{\frac{3}{2}} \right)
\end{equation}

So, to second order in $$e_i$$ and $$I_i$$ and in $$\delta_i$$, averaged over long-timescales, and ignoring variations in $$a_i$$, the effect of the disturbing function reduces to an eigenvalue problem.



## III. The Perihelion Precession of Mercury

### III.I Gravitational Effects

We are ready to apply what we have learned to study the precession of Mercury's perihelion. We consider a three-body system of the Sun, Mercury, and each of the other seven planets. 

Beginning with $$m_1'$$, Mercury, $$m_2'$$, Venus, we have the following values for constants in units of AU, and earth masses:

\begin{equation}
    n_1 = 26.098 \nonumber
\end{equation}

\begin{equation}
    \alpha = 0.535 \nonumber
\end{equation}

\begin{equation}
    a_2 = 0.732 \nonumber
\end{equation}

\begin{equation}
    \delta_1 = 1.66 \times 10^{-7} \nonumber
\end{equation}

\begin{equation}
    \delta_2 = 2.448 \times 10^{-6} \nonumber
\end{equation}

\begin{equation}
    m_2 = 0.815 \nonumber
\end{equation}

\begin{equation}
     b^{(1)} _{\frac{3}{2}}(\alpha) = 1.519 \nonumber
\end{equation}

\begin{equation}
      b^{(2)} _{\frac{3}{2}}(\alpha) = 0.976 \nonumber
\end{equation}

As an eigenvalue problem for $$h_1$$, $$k_1$$, $$h_2$$, and $$k_2$$:

$$\begin{equation}
    \begin{pmatrix}
        \dot{h}_1\\
        \dot{h}_2\\
        \dot{h}_1\\
        \dot{k}_2\\
    \end{pmatrix}=
    \begin{pmatrix}
        0 & 0 & 1.39\times10^{-5} & -8.93\times10^{-6}\\
        0 & 0 & -8.87\times10^{-7} & 1.38\times10^{-6}\\
        -1.39\times10^{-5} & 8.93\times10^{-6} & 0 & 0\\
        8.87\times10^{-7} & -1.38\times10^{-6} & 0 & 0       
    \end{pmatrix}
    \begin{pmatrix}
        h_1\\
        h_2\\
        k_1\\
        k_2\\
    \end{pmatrix}
\end{equation}$$

We use the current orbital elements of Mercury and Venus as initial parameters. 

\begin{equation}
    e_1 = 0.206 \nonumber
\end{equation}
\begin{equation}
    e_2=0.0068 \nonumber
\end{equation}
\begin{equation}
   I_1 = 7.004^{\circ} \nonumber
\end{equation}
\begin{equation}
    I_2 = 3.394^{\circ}\nonumber
\end{equation}
\begin{equation}
    \varpi_1 = 77.456^{\circ} \nonumber
\end{equation}
\begin{equation}
    \varpi_2 = 131.533^{\circ} \nonumber
\end{equation}
\begin{equation}
   \Omega_1 = 48.332^{\circ} \nonumber
\end{equation}
\begin{equation}
    \Omega_2=76.681^{\circ} \nonumber
\end{equation}

\begin{equation}
    h_1(0) = 0.201  \nonumber
\end{equation}
\begin{equation}
     h_2(0)=0.00509  \nonumber
\end{equation}
\begin{equation}
    k_1(0)=0.0447 \nonumber
\end{equation}
\begin{equation}
    k_2(0) =-0.00451 \nonumber
\end{equation}


Solving the eigenvalue problem:

\begin{equation}
    h_1(t) = 0.0121\cos{\left(7.763 \times 10^{-7}t \right)}+ 0.189\cos{\left(1.450\times 10^{-5}t \right)}
\end{equation}

\begin{equation}
    -9.70 \times 10^{-4}\sin{\left(7.763 \times 10^{-7}t \right)}+0.0456\sin{\left(1.450 \times 10^{-5}t \right)}
\end{equation}

\begin{equation}
    k_1(t) = -0.0121\sin{\left(7.763 \times 10^{-7}t \right)}- 0.189\sin{\left(1.450\times 10^{-5}t \right)}
\end{equation}

\begin{equation}
    -9.70 \times 10^{-4}\cos{\left(7.763 \times 10^{-7}t \right)}+0.0456\cos{\left(1.450 \times 10^{-5}t \right)}
\end{equation}

And calculating, we find the precession of Mercury's perihelion in arcseconds per century from the influence of Venus. 

\begin{equation}
    \dot{\varpi}_1=\frac{\dot{h}_1k_1-h_1\dot{k}_1}{h_1^2+k_1^2}\approx283.114^{"}\text{ century}^{-1}
\end{equation}

Repeating the analysis with the other planets of the solar system we find the following:

\begin{equation}
    \text{Venus- } 283.114^{"}\text{ century}^{-1} \nonumber
\end{equation}

\begin{equation}
    \text{Earth- }  92.065^{"}\text{ century}^{-1} \nonumber
\end{equation}

\begin{equation}
    \text{Mars- }  2.476^{"}\text{ century}^{-1} \nonumber
\end{equation}

\begin{equation}
    \text{Jupiter- }  158.566^{"}\text{ century}^{-1} \nonumber
\end{equation}

\begin{equation}
    \text{Saturn- }  7.554^{"}\text{ century}^{-1} \nonumber
\end{equation}

\begin{equation}
    \text{Uranus- }  0.145^{"}\text{ century}^{-1} \nonumber
\end{equation}

\begin{equation}
    \text{Neptune- }  0.0438^{"}\text{ century}^{-1}  \nonumber
\end{equation}

\begin{equation}
    \text{Total- }  543.964^{"}\text{ century}^{-1} \nonumber
\end{equation}

Our total precession $$\approx544^{"}$$ per century is puzzling, as it is lower than the actual precession of Mercury's perihelion which is nearer to $$\approx 585^{"}$$ per century. Even considering our result as a second-order approximation does not account for this deviation, to find the missing source of precession, we must consider Einstein's General Relativity.

## III.II The Relativistic Disturbing Function

From relativistic effects, an extra term is added to the two-body Hamiltonian:

\begin{equation}
    \mathcal{H}=\frac{1}{2\mu}\parallel\vec{p}\parallel^2-\frac{\mathcal{G}\mu m}{\parallel{\vec{r}}\parallel}-\frac{\mathcal{G}L^2 m}{\mu c^2{\parallel{\vec{r}}\parallel}^3}
\end{equation}

The disturbing function is easy to recognize:

\begin{equation}
    \mathcal{R}=-\frac{\mathcal{G}L^2 m}{\mu c^2r^3}=-\frac{\mathcal{G}^2\mu m^2a}{c^2r^3}
\end{equation}

Fortunately, dealing with this disturbing function is much easier than in the three-body case. Again, we will average over orbits to find the secular perturbations brought about by $$\mathcal{R}$$. We calculate:

\begin{equation}
    \langle\mathcal{R}\rangle=\frac{1}{2\pi}\int_0^{2\pi}\mathcal{R}d\mathcal{M}
\end{equation}

Using <a href="https://tlara1.github.io/projects/1_project/">orbital elements</a>:

\begin{equation}\label{dM equation}
    d\mathcal{M}=\left(1-e\cos{E}\right)dE=\frac{r}{a}dE=\frac{1-e^2}{1+e\cos{f}}dE
\end{equation}

Similarly:

\begin{equation}
    \cos{E} = \frac{r}{a}\cos{f} + e = \frac{\cos{f} + e}{1 + e\cos{f}} \label{cos E f equation}
\end{equation}

\begin{equation}
    \sin{E} = \frac{r}{a\sqrt{1-e^2}}\sin{f} = \frac{\sqrt{1-e^2}\sin{f}}{1+e\cos{f}} \label{sin E f equation}
\end{equation}



We continue, expressing $$dE$$ in terms of $$df$$:

\begin{equation}
    \cos{E}dE=\frac{\sqrt{1-e^2}\left(\cos{f}+e\right)}{\left(1+e\cos{f}\right)^2}df\rightarrow dE=\frac{\sqrt{1-e^2}}{1+e\cos{f}}df
\end{equation}

Thus:

\begin{equation}
    d\mathcal{M}=\frac{\left(1-e^2\right)^{\frac{3}{2}}}{\left(1+e\cos{f}\right)^2}df
\end{equation}

Writing $$\frac{1}{r^3}$$ in terms of $$f$$:

\begin{equation}
    \frac{1}{r^3}=\frac{\left(1+e\cos{f}\right)^3}{a^3\left(1-e^2\right)^3}
\end{equation}

Averaging our disturbing function:

\begin{equation}
    \langle\mathcal{R}\rangle=\frac{1}{2\pi}\int_0^{2\pi}\mathcal{R}d\mathcal{M}=-\frac{\mathcal{G}^2\mu m^2a}{c^2}
    \frac{1}{2\pi}\int_0^{2\pi}\frac{1+e\cos{f}}{a^3\left(1-e^2\right)^\frac{3}{2}}df=-\frac{\mathcal{G}^2\mu m^2}{a^2c^2\left(1-e^2\right)^\frac{3}{2}}
\end{equation}

With <a href="https://tlara1.github.io/projects/1_project/">the plantery equations</a>:

\begin{equation}
    \dot{\varpi}=-\frac{\sqrt{1-e^2}}{\mu e\sqrt{\mathcal{G}ma}}\frac{\partial \mathcal{R}}{\partial e}=\frac{3\left(\mathcal{G}ma\right)^{\frac{3}{2}}}{a^4c^2\left(1-e^2\right)^2}
\end{equation}

And, somewhat unsurprisingly, using current values, we find:

\begin{equation}
    \dot{\varpi}=44.908^{"} \text{ century}^{-1}
\end{equation}

This brings the total precession to $$\approx588.872^{"}$$, much closer to the observed value.

Of course, there are other sources of perihelion precession such as the oblateness of the sun and the interactions of other planets with each other, but these corrections are of a higher order than the second-order approximations we have carried out.


