---
layout: page
title: Fluid-Immersed Eulerian Frictional Contacts
description:
img: assets/img/RMT_videos_img/flappers_n20_vorticity.gif
importance: 1
category: 2026
related_publications: false
---

I recently presented this work at a webinar of the student chapter of the US Association of Computational Mechanics. My slides can be found <a href="https://1drv.ms/p/c/862b1b0b1baeb400/IQDNN1aMA-a-RIctqTugPHSyAbrQ5h3VgHGd6lQfeHrQ9zY?e=gAGnzF"> here</a>, and the presentation was recorded <a href="https://www.youtube.com/watch?v=52YMncqQZ78"> here</a>!

In an extension of my work modeling Eulerian fluid-immersed solid contacts, we improved our contact model by incorporating frictional forces. A frictional contact between tangentially sliding bodies requires a notion of the velocities of those bodies. Usually this is straightforward when modeling rigid bodies since each body will have its own velocity, but in our Eulerian framework, all we have is a global velocity field. There is no concept of a single body's velocity, so adding frictional forces is nontrivial. To resolve this, we introduce a solid-body velocity-averaging procedure that averages the velocity field across the fluid gap between bodies near the fluid-solid interface. This averaging procedure involves a local integral calculation similar to that in our contact formalism, so much so that we can perform it at the same time as the calculation for the self-contact forces. Our friction method allows us to model tangential shearing contact between sliding bodies, while remaining in a fluid bath and interacting with the surrounding fluid flow. 


<p> We have validated our model on several benchmarks, including convergence to the classical analytic Hertz-Mindlin solution for weakly deforming shearing disks, a block sliding on a ramp, a ball-bearing rotating disk inside a hoop to assess frictional torque balance, and a periodically shearing U "violin" shape demonstrating a closed hysteresis loop. 


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/RMT_videos_img/supplemental_video_1_sliding_bent_U_mu05.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
A shearing "violin" shape with frictional self-contacts. Friction forces act opposite to the shearing motion and are equal in magnitude across both faces of the sliding U.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/RMT_videos_img/supplemental_video_4_squished_bent_U - Trim.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
A sandwiched U shape between two shearing rectangles. Frictional interactions cause the U to both translate and rotate along with the moving rods. The arms of the U also come into contact, experiencing frictional self-sliding.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/RMT_videos_img/rotating_hoop_fixed.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>

<div class="caption">
A disk rotating within a hoop. Friction forces produce equal and opposite torques on the curved surfaces.
</div>

Because the friction technique slots nicely into the existing RMT mechanism, we can do fun things with many falling, waving, touching objects, or even active swimmers all squirming frictionally past each other in "creepy" aquariums. All simulations here are Eulerian with a single levelset field, which is very computationally efficient compared to similar fluid-structure interaction simulation techniques.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/RMT_videos_img/supplemental_video_3_wavy_rods_mu1_fixed.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>

<div class="caption">
Disks and wavy rods colliding and settling due to gravity; all contacts here are frictional.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/RMT_videos_img/flappers_n20_vorticity_fixed.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>

<div class="caption">
A tank of creepy flappers swimming into each other and touching.
</div>


