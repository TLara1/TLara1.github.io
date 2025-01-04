---
layout: page
title: Celestial Mechanics and the Precession of Mercury
description: with background image
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

\section{Mechanics}
\subsection{Canonical Transforms}

A time-independent coordinate transform $$q_i\rightarrow Q_i$$ and $$p_i\rightarrow P_i$$ is said to be canonical if it preserves Hamilton's equations of motion. Specifically, letting the new Hamiltonian $$\mathcal{K}\left(Q_i,P_i\right)=\mathcal{H}\left(q\left(Q_i,P_i\right),p_i\left(Q_i,P_i\right)\right)$$, then we have:

\begin{equation}
    \dot{Q}_i=\frac{\partial\mathcal{K}}{\partial P_i}
\end{equation}
\begin{equation
    \dot{P}_i=-\frac{\partial\mathcal{K}}{\partial Q_i}
\end{equation}{

The most useful criteria for determining if a transform is canonical are \textit{Poisson brackets}. Given coordinates $$q_i$$ and $$p_i$$, the Poisson bracket of functions $$Q_j\left(q_i,p_i\right)$$ and $$P_j\left(q_i,p_i\right)$$ is given by:
\begin{equation}
    \{Q_j,P_j\}=\sum_i\frac{\partial Q_j}{\partial q_i}\frac{\partial P_j}{\partial p_i}-\frac{\partial Q_j}{\partial p_i}\frac{\partial P_j}{\partial q_i}
\end{equation}
We show that a transform is canonical if and only if:
\begin{equation}
    \{ Q_i,Q_j \}=0\label{cannonical 1}\\
    \{P_i,P_j\}=0\\
    \{Q_i,P_j\}=\delta_{ij}\label{cannonical 3}
\end{equation}
Poisson Brackets can also be used to determine if a function of coordinates $$f\left(p_i,q_i\right)$$ is constant in time:
\begin{equation}\label{const function}
    \frac{df}{dt}=\sum_i\frac{\partial f}{\partial q_i}\dot{q}_i+\frac{\partial f}{\partial p_i}\dot{p}_i=\{f,\mathcal{H}\}
\end{equation}

\subsection{The Hamilton-Jacobi Equation}

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
\end{align}
Now, suppose we want our transformed Hamiltonian, $$\mathcal{K}=0$$ such that $$\dot{Q}_i=0$$ and $$\dot{P}_i=0$$. So, we look for a generating function with:
\begin{equation}\label{HJ Equation}
    \mathcal{H}\left(q_i,\frac{\partial S}{\partial q_i},t\right)+\frac{\partial S}{\partial t}=0
\end{equation}
This is the Hamilton-Jacobi Equation.
