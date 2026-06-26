---
layout: page
title: Block-Structured AMR
description:
img: assets/img/Final_Project_Figures/image1.png
importance: 1
category: 2026
related_publications: false
---

For my class on numerical methods for partial differential equations, my final project involved an implementation of Adaptive Mesh Refinement (AMR) in two dimensions. Having done a good bit of AMR in the past, I thought this would be fairly straightforward, but it turned out to be waaaaaaaay more complex than I expected. For such a straightforward idea, the amount of code that goes under the hood of AMR is staggering. My implementation was for the axisymmetric vorticity equations in polar coordinates.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/omega_fouer_test1.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    An example simulation of an arbitrary vorticity field. Note the blocks and refined areas of the grid follow the deforming flow such that computational importance is centered on regions where it is most necessary.
</div>


{% include figure.liquid loading="eager" path="assets/img/Final_Project_Figures/convergence_analytic_with_snapshots_v2.png" title="Convergence as levels increases" class="img-fluid rounded z-depth-0" width="auto" height="600" %}

I'm happy to report the code worked swimmingly. The level management and patch allocation/reallocation functioned as intended. With more levels, the computation accelerated without increasing computational cost quadratically.

The full project is available on this <a href="https://github.com/TLara1/18.336-AMR-Final-Project"> Github </a>. There are more cool videos here, which are always fun to watch. In the future, I may continue to update this to improve the AMR procedure or expand to more complex problems. 

My project report is available <a href="https://drive.google.com/file/d/16At_xwcDBZ-FZoZkqJeEDPnJMBCmLB4F/view?usp=sharing"> here </a> and my presentation is <a href="https://docs.google.com/presentation/d/1MJvueVZi-A1WOC3QMkgT_NwHn5Uw3Amp/edit?usp=sharing&ouid=101752269380611784296&rtpof=true&sd=true"> here </a>. This was also the first time making a presentation in PowerPoint and not Google Slides, and oh boy, I will never go back.
