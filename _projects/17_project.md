---
layout: page
title: Block-Structured AMR
description:
img:
importance: 2
category: 2026
related_publications: false
---

For my class on numerical methods for partial differential equations, my final project involved an implementation of Adaptive Mesh Refinement (AMR) in two dimensions. Having done a good bit of AMR in the past, I thought this would be fairly straightforward, but it turned out to be waaaaaaaay more complex than I expected. For such a straightforward idea, the amount of code that goes under the hood of AMR is staggering. My implementation was for the axisymmetric vorticity equations in polar coordinates.

I'm happy to report the code did work swimmingly, the full project is available on this <a href="https://github.com/TLara1/18.336-AMR-Final-Project"> Github </a>. There are also some cool videos here, which are always fun to watch. In the future, I may continue to update this to improve the AMR procedure or expand to more complex problems. 

My project report is available <a href="https://drive.google.com/file/d/16At_xwcDBZ-FZoZkqJeEDPnJMBCmLB4F/view?usp=sharing"> here </a> and my presentation is <a href="https://docs.google.com/presentation/d/1MJvueVZi-A1WOC3QMkgT_NwHn5Uw3Amp/edit?usp=sharing&ouid=101752269380611784296&rtpof=true&sd=true"> here </a>. This was also the first time making a presentation in PowerPoint and not Google Slides, and oh boy, I will never go back.




For my applied mathematics seminar class, we were given the opportunity to explore an interesting phenomenon of our choice. An intelligent student would've adopted one of their two ongoing research projects for their class. Unfortunately, I was encouraged by John Bush to take a more adventerous route, suggesting animal magnetoreception. John is a fan of whales, but I'm a bigger fan of birds, and I did a project on the mechanics of avian magnetonavigation, a word that I made up.

{% include figure.liquid loading="eager" path="assets/img/radical_pair_diagram.png" title="Radical Pair Schematic" class="img-fluid rounded z-depth-0" width="auto" height="300" %}
_Cool schematic of magnetoreceptive mechanisms in birds._
Birds are actually really cool, and the mechanism of how they navigate from point A to point B is fascinating. Basically, they use the Earth's magnetic field in a process that is somewhat still poorly understood, and using this field, they orient themselves during migration. In this project, I developed a minimal-ish model to represent this migration and tested it against actual flight trajectories of European Turtle Doves. The model is, as far as I know, novel, but I think the underpinning physical assumptions are somewhat iffy. There is, for sure, something of interest here that I may develop more in the future.

{% include figure.liquid loading="eager" path="assets/img/migration_paths_comparison_v2.png" title="Path Dependence Noise" class="img-fluid rounded z-depth-0" width="auto" height="300" %}
_When the sensing noise increases, trajectories become less able to reach their goal._
There is also an interesting idea of a less biologically motivated problem. From a mathematical perspective, I wonder how an agent can get from point A to point B, given a known field signature at these points and knowledge of a field at its location. The crux being the agent has no knowledge of the field gradient but can use previous measurements along its trajectory. Surely there is some action minimization to optimise paths, but not knowing the local gradient is tricky. Also, things become complicated in the presence of noise. My treatment of noise in my work is somewhat naive, I think there is a more sophisticated model to be constructed for problems of this class.

The project ended up being closer to a thesis than to a class project. The full paper is here and my very long slidedeck presentation is here for anyone interested in this work.
