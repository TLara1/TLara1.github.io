---
layout: page
title: Celestial Mechanics and the Precession of Mercury
description: with background image
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

A time-independent coordinate transform $q_i\rightarrow Q_i$ and $p_i\rightarrow P_i$ is said to be canonical if it preserves Hamilton's equations of motion. Specifically, letting the new Hamiltonian $\mathcal{K}\left(Q_i,P_i\right)=\mathcal{H}\left(q\left(Q_i,P_i\right),p_i\left(Q_i,P_i\right)\right)$, then we have:

\begin{equation}
    \dot{Q}_i&=\pdv{\mathcal{K}}{P_i}\\
    \dot{P}_i&=-\pdv{\mathcal{K}}{Q_i}
\end{equation}

The most useful criteria for determining if a transform is canonical are \textit{Poisson brackets}. Given coordinates $q_i$ and $p_i$, the Poisson bracket of functions $Q_j\left(q_i,p_i\right)$ and $P_j\left(q_i,p_i\right)$ is given by:
\begin{equation}
    \{Q_j,P_j\}=\sum_i\pdv{Q_j}{q_i}\pdv{P_j}{p_i}-\pdv{Q_j}{p_i}\pdv{P_j}{q_i}
\end{equation}
We show that a transform is canonical if and only if:
\begin{align}
    \{Q_i,Q_j\}&=0\label{cannonical 1}\\
    \{P_i,P_j\}&=0\\
    \{Q_i,P_j\}&=\delta_{ij}\label{cannonical 3}
\end{align}
Poisson Brackets can also be used to determine if a function of coordinates $f\left(p_i,q_i\right)$ is constant in time:
\begin{equation}\label{const function}
    \frac{df}{dt}=\sum_i\pdv{f}{q_i}\dot{q}_i+\pdv{f}{p_i}\dot{p}_i=\{f,\mathcal{H}\}
\end{equation}
