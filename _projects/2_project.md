---
layout: page
title: Derivation of the Lagrange Planetary Equations
description:
img: assets/img/3.jpg
importance: 2
category: Physics
giscus_comments: false
---


<h4>V.I.II Series Expansion of Direct Disturbing Function</h4>

With \cref{zeta expansion e} and \cref{epsilon expansion}:

\begin{equation}
    \frac{1}{2}\frac{r_1}{a_1}\frac{R_2}{a_2}\epsilon \simeq \frac{1}{2}\left(\cos{(\lambda_1+\lambda_2-2\Omega_1)} - \cos{(\lambda_1+\lambda_2)}\right)\sin^2{\frac{I_1}{2}} + \left(\cos{(\lambda_1+\lambda_2-2\Omega_2)} - \cos{(\lambda_1+\lambda_2)}\right)\sin^2{\frac{I_2}{2}}\nonumber
\end{equation}

\begin{equation}
\label{r/a and epsilon expansion}
    + \left(\cos{(\lambda_1-\lambda_2-\Omega_1+\Omega_2)} - \cos{(\lambda_1+\lambda_2-\Omega_1-\Omega_2)}\right)\sin{\frac{I_1}{2}}\sin{\frac{I_2}{2}}
\end{equation}

As $$\frac{1}{2}\frac{r_1}{a_1}\frac{R_2}{a_2}\epsilon$$ is already of second order, we can ignore $$k>1$$ terms in \cref{R_D expression}. Now we need an expansion for $$\cos{(j(\vartheta_1-\vartheta_2))}$$, where $$j$$ is an arbitrary integer. We start by noting:

\begin{equation}
    \cos{(j(\vartheta_1-\vartheta_2))} = \cos{(j(\varpi_1 + f_1))}\cos{(j(\varpi_2 + f_2))} + \sin{(j(\varpi_1 + f_1))}\sin{(j(\varpi_2 + f_2))}
\end{equation}

We use our \cref{theta expansion in e} and expand:

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

We have all the ingredients to expand $$\mathcal{R}_D$$. From \cref{r/a and epsilon expansion}, we omit $$k>1$$ terms and since $$\zeta_i$$ is first-order, we omit $$\mathcal{O}\left(\zeta^3\right)$$ terms. With \cref{R_D expression}: 

\begin{equation} 
    \mathcal{R}_D \simeq-\frac{\mathcal{G}m_0'^2\delta_1 \delta _2} {a _2} \sum _{j=-\infty} ^\infty \left(a _2 A _{0,j,0,0} + a _2 \zeta _1 A _{0,j,1,0} + a _2 \zeta _2 A _{0,j,0,1} +\frac{1}{2}a _2\zeta _1 ^2 A _{0,j,2,0} \right. \nonumber
\end{equation}

\begin{equation}
    \left.+\frac{1}{2}a_2\zeta_2^2 A_{0,j,0,2}+a_2\zeta_1 \zeta_2A_{0,j,1,1}+\frac{r_1}{a_1}\frac{R_2}{a_2}\epsilon a_1a_2^2A_{1,j,0,0}\right)\cos{\left(j(\vartheta_1-\vartheta_2)\right)} \nonumber
\end{equation}

\begin{equation} \label{RDj expression}
    =-\frac{\mathcal{G}m_0'^2\delta_1\delta_2}{a_2}\sum_{j=-\infty}^\infty\mathcal{R}_D^{(j)}
\end{equation}

Using our definition of $$A_{k,j,m,n}$$ (\cref{def A}), transforming derivatives with respect to $$\alpha$$ because $$b^{(j)}_s$$ is a function of $$\alpha$$:

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

What follows is a hefty quantity of tedious algebra, using \cref{epsilon expansion}, \cref{r/a and epsilon expansion}, and \cref{cos vartheta expansion}. We expand \cref{RDj expression} to 2nd order in $$e_i$$ and $$\sin{\frac{I_i}{2}}$$.
We also recall the trigonometric identity: $$\cos{a}\cos{b}=\frac{1}{2}\cos{(a+b)}+\frac{1}{2}\cos{(a-b)}$$. We write $$\mathcal{R}_D^{(j)}=\mathcal{R}_D^{(j)(0)}+\mathcal{R}_D^{(j)(1)}+\mathcal{R}_D^{(j)(2)}$$, categorizing terms by the sum of the coefficients of $${\lambda_1}$$ and $${\lambda_2}$$.

\begin{equation}
    \mathcal{R}_D^{(j)(0)} \simeq \left( 1+\frac{1}{4}(e_1^2+e_2^2)\left(-4j^2+2\alpha\frac{\partial }{\alpha}+\alpha^2\frac{\partial ^2}{\alpha^2}\right)\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{(j({\lambda_1}-\lambda_2))} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{4}e _1 e _2\left(2j+4j^2-2\alpha\frac{\partial }{\alpha}-\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1+j){\lambda_1}-(1+j)\lambda_2-\varpi_1+\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{4}e _1 e _2\left(-2j+4j^2-2\alpha\frac{\partial }{\alpha}-\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}-(1-j)\lambda_2-\varpi_1+\varpi _2)} \nonumber
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
    \mathcal{R} _D^{(j)(1)} \simeq \frac{1}{2}e _1\left(2j-\alpha\frac{\partial }{\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1+j){\lambda_1}-j\lambda_2-\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{2}e_1\left(2j+\alpha\frac{\partial }{\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}+j\lambda_2-\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}e_2\left(1+2j+\alpha\frac{\partial }{\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}-(1+j)\lambda_2+\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{2}e_2\left(1-2j+\alpha\frac{\partial }{\alpha} \right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}+(1-j)\lambda_2-\varpi_2)}
\end{equation}


\begin{equation}
    \mathcal{R} _D^{(j)(2)} \simeq \frac{1}{8}e_1^2\left(5j+4j^2-2\alpha\frac{\partial }{\alpha}-4j\alpha\frac{\partial }{\alpha}+\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)} _{\frac{1}{2}}(\alpha)\cos{((2+j){\lambda_1}-j\lambda_2-2\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{8}e_1^2\left(-5j+4j^2-2\alpha\frac{\partial }{\alpha}+4j\alpha\frac{\partial }{\alpha}+\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{((2-j){\lambda_1}+j\lambda_2-2\varpi_1)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{4}e_1e_2\left(2j-4j^2-2\alpha\frac{\partial }{\alpha}+4j\alpha\frac{\partial }{\alpha}-\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{((1+j){\lambda_1}+(1-j)\lambda_2-\varpi_1-\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    -\frac{1}{4}e_1e_2\left(2j+4j^2+2\alpha\frac{\partial }{\alpha}+4j\alpha\frac{\partial }{\alpha}+\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{((1-j){\lambda_1}+(1+j)\lambda_2-\varpi_1-\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{8}e_2^2\left(4+9j+4j^2+6\alpha\frac{\partial }{\alpha}+4j\alpha\frac{\partial }{\alpha}+\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}-(2+j)\lambda_2+2\varpi_2)} \nonumber
\end{equation}

\begin{equation}
    +\frac{1}{8}e_2^2\left(4-9j+4j^2+6\alpha\frac{\partial }{\alpha}-4j\alpha\frac{\partial }{\alpha}+\alpha^2\frac{\partial ^2}{\alpha^2}\right)b^{(j)}_{\frac{1}{2}}(\alpha)\cos{(j{\lambda_1}+(2-j)\lambda_2-2\varpi_2)} \nonumber
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



<h4>V.I.III Series Expansion of Indirect Disturbing Function</h4>
The indirect portion of the disturbing function is much less involved. Rewriting the indirect portion:

\begin{equation}
    \mathcal{R}_E=\mathcal{G}m_0'^2\delta_1\delta_2\frac{\alpha}{a_2}\frac{r_1}{a_1}\left(\frac{a_2}{R_2}\right)^2\cos{\psi}
\end{equation}

We expand in the same way we expanded $$\mathcal{R}_D$$. First, via \cref{cosE e expansion}:

\begin{equation}
    \left(\frac{a_2}{R_2}\right)^2 = \left(\frac{1}{1-e_2\cos{E_2}}\right)^2 \simeq 1+2\cos{\mathcal{M}_2}e_2+\left(3\cos^2{\mathcal{M}_2}+\cos{2\mathcal{M_2}}-1\right)e_2^2 \nonumber
\end{equation}

\begin{equation}
    \simeq 1+2\cos{(\lambda_2-\varpi_2)}e_2+\frac{1}{2}\left(5\cos{(2(\lambda_2-\varpi_2))}+1\right)e_2^2 
\end{equation}

And consulting \cref{zeta expansion e} and \cref{cos psi expansion}:

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





<h3>V.II Using the Disturbing Function</h3>
From our Planetary Equations, the time variations in our orbital elements (excluding the orbital $$\lambda$$ changes from the non-perturbed Hamiltonian) are proportional to $$\sim\frac{1}{\mu_1\sqrt{\mathcal{G}m_1a_1}}\pdv{R}{i}$$, so from our disturbing function, the time variation in our elements is $$\sim\frac{\sqrt{\mathcal{G}}m_1'm_2'}{\mu_1R_2\sqrt{m_1a_1}}=\frac{\sqrt{\mathcal{G}m_1}\delta_2}{R_2\sqrt{a_1}}\approx n\delta_2$$, where we have approximated $$R_2\approx a_1$$, which is reasonable in our proportionality arguments. Thus, our orbital elements vary $$\sim\delta_2$$ times slower than the orbital period. We call these elements \textit{secular}, varying much slower than planetary orbits, so, to evaluate the impact of our Disturbing Function, we can average over the orbital cycles of $$\lambda_1$$ and $$\lambda_2$$.

\begin{equation}
    \langle\langle\mathcal{R}\rangle\rangle=\frac{1}{4\pi^2}\int_0^{2\pi}\int_0^{2\pi}\mathcal{R}d\lambda_1d\lambda_2
\end{equation}

As all the terms in our disturbing function feature trigonometric terms of $$\lambda_1$$ and $$\lambda_2$$. It is only terms without these angles that remain post-averaging. The only contributing term is $$\mathcal{R} _D
^{(0)(0)}$$:

\begin{equation}
    -\langle\langle\frac{a_2\mathcal{R}}{\mathcal{G}m_0'^2\delta_1\delta _2}\rangle\rangle = -\frac{a_2\mathcal{R} _D^{(0)(0)}}{\mathcal{G}m _0'^2\delta _1\delta_2} \simeq b^{(0)} _{\frac{1}{2}}(\alpha) + \frac{1}{4}(e_1^2 + e_2^2) \left( 2\alpha \pdv{}{\alpha} + \alpha^2 \pdv{^2}{\alpha^2} \right) b^{(0)} _{\frac{1}{2}}(\alpha) \noname
\end{equation}

\begin{equation}
    -\alpha \left( \sin^2{\frac{I_1}{2}} + \sin^2{\frac{I_2}{2}} \right) b^{(1)}_{\frac{3}{2}}(\alpha) \noname
\end{equation}

\begin{equation}
    + \frac{1}{2} e_1 e_2 \left( 2 - 2\alpha \pdv{}{\alpha} - \alpha^2 \pdv{^2}{\alpha^2} \right) b^{(1)}_{\frac{1}{2}}(\alpha) \cos{(\varpi_1 - \varpi_2)} \noname
\end{equation}

\begin{equation}
    + 2 \sin{\frac{I_1}{2}} \sin{\frac{I_2}{2}} \alpha b^{(1)}_{\frac{3}{2}}(\alpha) \cos{(\Omega_1 - \Omega_2)}
\end{equation}


We have made use of the fact that $$b_s^{(-j)}(\alpha)=b_s^{(j)}(\alpha)$$. With the properties of Laplace coefficients (\cref{laplace coefficient definitions}):

\begin{equation}
    \left( 2\alpha \pdv{}{\alpha} + \alpha^2 \pdv{^2}{\alpha^2} \right) b^{(0)}_{\frac{1}{2}}(\alpha) = \alpha b^{(1)}_{\frac{3}{2}}(\alpha) \noname
\end{equation}

\begin{equation}
    \left( 2 - 2\alpha \pdv{}{\alpha} - \alpha^2 \pdv{^2}{\alpha^2} \right) b^{(0)}_{\frac{1}{2}}(\alpha) = -\alpha b^{(2)}_{\frac{3}{2}}(\alpha)
\end{equation}

And, taking $$\sin{I_i}\simeq I_i$$:

\begin{equation}
    -\langle\langle \frac{a_2 \mathcal{R}}{\mathcal{G} m_0'^2 \delta_1 \delta_2} \rangle \rangle \simeq b^{(0)}_{\frac{1}{2}}(\alpha) + \frac{1}{4} (e_1^2 + e_2^2) \alpha b^{(1)}_{\frac{3}{2}}(\alpha) - \frac{1}{4} (I_1^2 + I_2^2) \alpha b^{(1)} _{\frac{3}{2}}(\alpha) \noname
\end{equation}

\begin{equation}
    -\frac{1}{2} e_1 e_2 \alpha b^{(2)}_{\frac{3}{2}}(\alpha) \cos{(\varpi_1 - \varpi_2)} + \frac{1}{2} I_1 I_2 \alpha b^{(1)} _{\frac{3}{2}}(\alpha) \cos{(\Omega_1 - \Omega_2)}
\end{equation}

Now in terms of our simplifying variables (\cref{orbital convert 1}-\cref{orbital convert end}):

\begin{equation}
    \langle\langle \mathcal{R} \rangle \rangle \simeq -\frac{\mathcal{G} m_0'^2 \delta_1 \delta_2}{a_2} \alpha \left( \frac{1}{4} \left( h_1^2 + h_2^2 + k_1^2 + k_2^2 \right) b^{(1)} _{\frac{3}{2}}(\alpha) - \frac{1}{4} \left( p_1^2 + p_2^2 + q_1^2 + q_2^2 \right) b^{(1)} _{\frac{3}{2}}(\alpha) \right)
\end{equation}

\begin{equation}
    \left. - \frac{1}{2} \left( h_1 h_2 + k_1 k_2 \right) b^{(2)}_{\frac{3}{2}}(\alpha) + \frac{1}{2} \left( p_1 p_2 + q_1 q_2 \right) b^{(1)} _{\frac{3}{2}}(\alpha) \right)
\end{equation}

Because we are assuming $$\alpha$$ is constant (recall that variations in $$a_i$$ are much slower than those for other secular elements), we have omitted the $$b^{(0)}_{\frac{1}{2}}\left(\alpha\right)$$ term. Our evolution equations for our simplified elements using \cref{lagrange simple start}-\cref{lagrange simple end}:

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


We can use \cref{3 body hamiltonian with R} to do something similar for $$m_2'$$, identifying $$\mu_2=\frac{m_0'm_2'+m_1'm_2'}{m_0'+m_1'+m_2'}$$ and $$m_2=\frac{m_0'm_2'}{\mu_2}$$ as the variables to utilize in our evolution equations:

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



<h2>VI. The Perihelion Precession of Mercury</h2>

<h3>VI. Gravitational Effects</h3>

We are ready to apply what we have learned to study the precession of Mercury's perihelion. We consider a three-body system of the Sun, Mercury, and each of the other seven planets. 

Beginning with $$m_1'$$, Mercury, $$m_2'$$, Venus, we have the following values for constants in units of AU, and earth masses:

\begin{equation}
    n_1=26.098 && \alpha=0.535 && a_2=0.732 && \delta_1=1.66\times10^{-7} && \delta_2=2.448\times10^{-6} && m_2 = 0.815 \noname
\end{equation}

\begin{equation}
     b^{(1)} _{\frac{3}{2}}(\alpha) = 1.519 && b^{(2)} _{\frac{3}{2}}(\alpha) = 0.976 \noname
\end{equation}

As an eigenvalue problem for $$h_1$$, $$k_1$$, $$h_2$$, and $$k_2$$:

\begin{equation}
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
\end{equation}

We use the current orbital elements of Mercury and Venus as initial parameters. 

\begin{equation}
    e_1 = 0.206 && e_2=0.0068 && I_1 = 7.004^{\circ} && I_2 = 3.394^{\circ}\\ \varpi_1 = 77.456^{\circ} && \varpi_2 = 131.533^{\circ} && \Omega_1 = 48.332^{\circ} && \Omega_2=76.681^{\circ} \noname
\end{equation}

\begin{equation}
    h_1(0) = 0.201 && h_2(0)=0.00509 && k_1(0)=0.0447 && k_2(0) =-0.00451 \noname
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
    \dot{\varpi}_1=\frac{\dot{h}_1k_1-h_1\dot{k}_1}{h_1^2+k_1^2}\approx283.114''\text{ century}^{-1}
\end{equation}

Repeating the analysis with the other planets of the solar system we find the results of \cref{table precess}.

\begin{table}\label{table precess}
    \centering
    \begin{tabular}{c|c}
         Planet & $$\dot{\varpi}_1$$
         century$$^{-1}$$\\
         \hline Venus & 283.114'' \\
         Earth & 92.065'' \\
         Mars & 2.476'' \\
         Jupiter & 158.566'' \\
         Saturn & 7.554'' \\
         Uranus & 0.145'' \\
         Neptune & 0.0438'' \\
         \hline Total & 543.964''
    \end{tabular}
    \caption{Influence of other planets on Mercury's Nodal Precession}
\end{table}

Our total precession $$\approx544''$$ per century is puzzling, as it is lower than the actual precession of Mercury's perihelion which is nearer to $$\approx 585''$$ per century. Even considering our result as a second-order approximation does not account for this deviation, to find the missing source of precession, we must consider Einstein's General Relativity.


