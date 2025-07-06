---
layout: page
title: Observing Walking Fluid Droplet Dynamics
img: assets/img/1.jpg
importance: 1
category: [2022]

---

Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
  <div class="col-sm mt-2 mt-md-0">
    <video class="img-fluid rounded z-depth-0" width="auto" height="600" controls>
      <source src="assets/img/Images_Figures_Videos_website_bush_22/davis_1_short.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>
  <div class="col-sm mt-2 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/Images_Figures_Videos_website_bush_22/davis_1_short.mp4" title="Video Droplet Bouncing Short" class="img-fluid rounded z-depth-0" width="auto" height="600" %}
  </div>
</div>

