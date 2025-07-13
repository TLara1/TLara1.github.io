---
layout: page
title: NEGF simulations for Quantum Transport in Carbon Nanotubes
description:
img: assets/img/images_website_Sawant_2024/CNTFigureLeonard2006.png
importance: 1
category: 2024
related_publications: false
---

During the summer of 2024, I undertook an internship at the Lawrence Berkeley National Laboratory (LBNL), working on simulating quantum transport in carbon nanotubes (CNTs). The Non-Equilibrium-Green's Function (NEGF) formalism has become widely adopted in quantum transport simulations, which are crucial in developing an understanding of CNT operations. We built on <a href="https://github.com/AMReX-Microelectronics/ELEQTRONeX"> ELEQTRONeX</a>, a fast, parallelizable NEG framework. Our work has two major aspects: implementing fast methods for computationally complex self-energy calculations and adding external charge sources to allow for broader applications.

<p> The existing ELEQTRONeX framework used an analytical self-energy solution, valid specifically for CNTs with basic lead configurations. To calculate more general self-energies, we used a tight-binding approximation, leading to an iterative and eigenfunction-based self-energy approach. Using randomly generated matrices, we showed that our methods are much more efficient than alternative direct inversions, allowing for faster and more complex NEGF geometries.

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/images_website_Sawant_2024/TopgateDiagram.png" title="Topgate Diagram" class="img-fluid rounded z-depth-0" width="auto" height="600" %}
</div>

<p> Motivated by discrepancies with experimental results, we also implemented point charges as external boundary conditions, which we demonstrated to have drastic impacts on our simulations.

<p> My final report can read <a href="https://drive.google.com/file/d/16Znx879Naj6zRpNXD1cFaAO-uI8B4h6g/view?usp=sharing"> here </a> and my poster can be found <a href="https://drive.google.com/file/d/1KLGDdQcSs8IwyPmsHNvougbv114AbVYe/view?usp=sharing"> here </a>.

