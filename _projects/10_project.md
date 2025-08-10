---
layout: page
title: Modelling Fluid-Solid Interaction and Collision Problems
description:
img: assets/img/Figures_Solidmech_Notes/matlab_psi_examples.png
importance: 2
category: 2025
related_publications: false
---

My longest continued research project involves modelling immersed solid self-contact in an entirely Eulerian framework. Most fluid-structure interaction formalisms model fluid and solid regions as distinct entities, usually using a fixed Eulerian grid for the former and a set of evolving Lagrangian points for the latter. Our method is entirely Eulerian, placing the fluid and solid on equal footing on a constant grid. This is advantageous in its simplicity and efficiency, but with only one universal velocity field, simulating solid contacts is tricky. Specifically, solid self-contacts are complicated as solids cannot "see" themselves and have no natural way to prevent self-penetration.

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/Figures_Solidmech_Notes/Accordian_vectors_v2.png" title="Accordian force vectors" class="img-fluid rounded z-depth-0" width="auto" height="400" %}
</div>

<p> We have developed a secondary repulsion field to prevent these self-contacts, allowing for solids to touch themselves while staying immersed in the fluid region. We validated our method using Hertzian analytical contact solutions and showed its functionality in complex contact situations involving multiple self-contacting bodies. 

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/Figures_Solidmech_Notes/Circle_snapshots_3panel.png" title="Circle Snapshots figure" class="img-fluid rounded z-depth-0" width="auto" height="400" %}
</div>

<div style="text-align: center;">
  {% include figure.liquid loading="eager" path="assets/img/Figures_Solidmech_Notes/Accordian_snapshots_v2.png" title="Accordian snapshots" class="img-fluid rounded z-depth-0" width="auto" height="400" %}
</div>

<p> We have published <a href="https://www.sciencedirect.com/science/article/abs/pii/S0045782525000179?via%3Dihub"> one publication</a> related to this work, and are currently working to extend our formalism to involve frictional contacts. 

<p> I recently presented my work at the USNCCM18 Conference in Chicago, Illinois. My presentation can be found <a href="https://docs.google.com/presentation/d/1tAO3QS8aAjAiHbTJm3rTAeqcX5P3auQOAXWGJ3dWSbY/edit?usp=sharing"> here</a>. I also presented a poster, which can be found <a href="https://docs.google.com/presentation/d/1tAO3QS8aAjAiHbTJm3rTAeqcX5P3auQOAXWGJ3dWSbY/edit?usp=sharing"> here</a>.
  
