---
layout: page
title: Investigating the Fast Multipole Method (FMM)
description:
img: assets/img/website_figure/figureA_B.png
importance: 1
category: 2025
related_publications: false
---

For my numerical methods class, I studied the Fast Multipole Method (FMM). This clever technique allows for quick distance-independent calculations of far-field potential functions between many points. Envision a cluster of $$n$$ stars interacting with each other gravitationally. To calculate the gravitational potential at each star from each other star, we would ordinarily need $$\mathcal{O}\left(n^2\right)$$ operations, but with the FMM, this can be accelerated to a linear $$\mathcal{O}\left(n\right)$$ operation.


<div class="row">
  <div style="text-align: center;">
    {% include figure.liquid loading="eager" path="assets/img/website_figure/error_figure.png" title="Error_figure" class="img-fluid rounded z-depth-0" width="450" height="auto" %}
  </div>
  <div style="text-align: center;">
    {% include figure.liquid loading="eager" path="assets/img/website_figure/complexity_figure.png" title="Complexity_figure" class="img-fluid rounded z-depth-0" width="450" height="auto" %}
  </div>
</div>







