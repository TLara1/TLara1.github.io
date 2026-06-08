---
layout: page
title: On Kalman Filters
description:
img: 
importance: 1
category: Maths
related_publications: false
toc:
  beginning: true
---

## Introduction
Back when I was working on my <a href="https://tlara1.github.io/projects/14_project/"> magnetonavigatory bird project</a>, I became interested in sensing and filtering techniques. My birds used a flavour of sensing filter based on certain biological assumptions, but the more time I spent working on the project, the more I wondered if there wasn't a better way to go about the problem of noisy sensing. I, being a physicist and mathematician, had never encountered control theory, which, in my experience, is more often taught in engineering departments. And what a shame, because it turns out Kalman filters are quite fascinating!

Here, we derive and discuss a basic Kalman filter. The idea being that, given a noisy signal with noisy sampling, we define a cost function and a filter that operates to minimize this loss function, giving us the best estimate of the signal subject to our sensory limitations. 

## The Mean Squared Error
Define our signal,
\begin{equation}
\mathbf{y}_k=A_kx+n_k,
\end{equation}
where $y_k$ is our time-dependent observed signal at time $t_k$, $a_k$ is a gain term connecting the information data $x_k$ to $y_k$. $n_k$ is an additive noise term arising from our imperfect sensing mechanisms. Note that

Our objective is to estimate $x_k$, and let $\hat{x}_k$ be our best estimate of $x_k$. We wish to minimise the mean-squared error
