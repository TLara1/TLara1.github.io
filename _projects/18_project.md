---
layout: page
title: On Kalman Filters - 6/26
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

## The Mean-Squared Error
Define our signal,
\begin{equation}\label{eq: signal update equation}
\mathbf{y}_k=\mathbf{A}\mathbf{x}_k+\mathbf{n}_k,
\end{equation}
where $$\mathbf{x}_k$$ is our time-dependent observed observation at time $$t_k$$, $$\mathbf{A}$$ is a time-independent  matrix connecting the information data $$\mathbf{x}_k$$ to $$\mathbf{Y}_k$$. $$\mathbf{n}_k$$ is an additive noise term arising from our imperfect sensing mechanisms. Note that all the terms are $$n$$-dimensional vectors for $$n$$ datapoints.

Our objective is to estimate $$\mathbf{x}_k$$, and let $$\hat{\mathbf{x}}_k$$ be our best estimate of $$\mathbf{x}_k$$. The loss function for our estimator is the squared norm of the error vector,
\begin{equation}
e_k=\left(\hat{\mathbf{x}}_k-{\mathbf{x}}_k\right)^T\left(\hat{\mathbf{x}}_k-{\mathbf{x}}_k\right).
\end{equation}
We want our filter to work over a long period of time, so we define the mean-squared error function, which is the average of the loss function over all of our samples,
\begin{equation}
\epsilon_k=\mathbb{E}[e_k].
\end{equation}
The mean-squared covariance matrix is the outer product of the error vectors, averaged over time,
\begin{equation}\label{eq: mean-squared covariance}
\mathbf{P}_k=\mathbb{E}\left[\left(\hat{\mathbf{x}}_k-{\mathbf{x}}_k\right)\left(\hat{\mathbf{x}}_k-{\mathbf{x}}_k\right)^T\right],
\end{equation}
which will be helpful later.

Good, now we proceed with the filter.

## State Space Derivation
Now we assume that the data variable evolves in time as,
\begin{equation}
\mathbf{x}_{k+1}=\mathbf{F}\mathbf{x}_k+\mathbf{w}_k,
\end{equation}
where $$\mathbf{F}$$ is some unknown time-independent evolution matrix which brings the state from $$k$$ to $$k+1$$, and $$\mathbf{w}_k$$ is the associated white noise of the process. The covariances of the noises are assumed to be time-independent and are given by,
\begin{equation}
\mathbf{Q}=\mathbb{E}\left[\mathbf{w}_k\mathbf{w}_k^T\right], \quad\mathbf{R}=\mathbb{E}\left[\mathbf{n}_k\mathbf{n}_k^T\right].
\end{equation}

Suppose we have some prior estimate of our system gained by our previous knowledge and possibly previous estimates called $$\hat{\mathbf{x}}_k'$$ that we wish to update using a new data measurement. We write our new estimate using the old estimate as,

\begin{equation}\label{eq: x_k estimate update}
\hat{\mathbf{x}}_k=\hat{\mathbf{x}}_k'+\mathbf{K}_k\left(\mathbf{y}_k-\mathbf{A}\hat{\mathbf{x}}_k'\right).
\end{equation}

$$\mathbf{y}_k$$ is our signal at time $$k$$, Eq. \ref{eq: signal update equation}, and $$\mathbf{K}_k$$ is the time-_dependent_ Kalman gain, which we will derive shortly. The term $$\mathbf{y}_k-\mathbf{A}\hat{\mathbf{x}}_k'$$ is called the innovation $$\mathbf{i}_k$$, and substituting Eq. \ref{eq: signal update equation}, we obtain,
\begin{equation}
\mathbf{i}_k=\mathbf{A}\mathbf{x}_k+\mathbf{n}_k-\mathbf{A}\hat{\mathbf{x}}_k'.
\end{equation}
Now inserting the updated estimate, Eq. \ref{eq: x_k estimate update} into the mean-squared covariance, Eq. \ref{eq: mean-squared covariance},
\begin{equation}
\mathbf{P}_k=\mathbb{E}\left[\left(\left(\mathbf{I}-\mathbf{K}_k\mathbf{A}\right)\left(\hat{\mathbf{x}}_k'-{\mathbf{x}}_k\right)+\mathbf{K}_k\mathbf{n}_k\right)\left(\left(\mathbf{I}-\mathbf{K}_k\mathbf{A}\right)\left(\hat{\mathbf{x}}_k'-{\mathbf{x}}_k\right)+\mathbf{K}_k\mathbf{n}_k\right)^T\right].
\end{equation}
We can recognize that error of the prior estimate, $$\hat{\mathbf{x}}_k'-{\mathbf{x}}_k$$ is uncorrelated with the measurement noise, $$\mathbf{n}_k$$, so the covariance may be rewritten as,
\begin{equation}\label{eq: covariance matrix from updated xk}
\mathbf{P}_k=\left(\mathbf{I}-\mathbf{K}_k\mathbf{A}\right)\mathbb{E}\left[\left(\hat{\mathbf{x}}_k'-{\mathbf{x}}_k\right)\left(\hat{\mathbf{x}}_k'-{\mathbf{x}}_k\right)^T\right]\left(\mathbf{I}-\mathbf{K}_k\mathbf{A}\right)^T+\mathbf{K}_k\mathbb{E}\left[\mathbf{n}_k\mathbf{n}_k^T\right]\mathbf{K}_k^T.
\end{equation}
The $$\mathbb{E}\left[\left(\hat{\mathbf{x}}_k'-{\mathbf{x}}_k\right)\left(\hat{\mathbf{x}}_k'-{\mathbf{x}}_k\right)^T\right]$$ in Eq. \ref{eq: covariance matrix from updated xk} is nothing more than the mean-squared covariance of the prior estimate, $$\mathbf{P}_k'$$, so we may update the mean-squared covariance directly using,
\begin{equation}
\mathbf{P}_k=\left(\mathbf{I}-\mathbf{K}_k\mathbf{A}\right)\mathbf{P}_k'\left(\mathbf{I}-\mathbf{K}_k\mathbf{A}\right)^T+\mathbf{K}_k\mathbf{R}\mathbf{K}_k^T,
\end{equation}
where we have used the measurement noise covariance $$\mathbf{R}$$.




### Sources
This derivation essentially follows from these, <a href="https://web.mit.edu/kirtley/kirtley/binlustuff/literature/control/Kalman%20filter.pdf"> lecture notes</a>.

