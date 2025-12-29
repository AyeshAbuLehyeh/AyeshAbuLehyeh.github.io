---
layout: page
title: Efficient Cross-View Geolocalization
description: A lightweight, real-time framework for fine-grained cross-view geolocalization.
img: /assets/img/cvg_architecture.jpg
importance: 1
category: work
related_publications: true
---

<div class="alert alert-info" role="alert">
  <strong>Status:</strong> This work has been submitted to a top-tier conference and is currently under review.  
  Code and full technical details will be released upon acceptance.
</div>

This project introduces a **lightweight and real-time framework for fine-grained cross-view geolocalization**, designed to overcome the accuracy–efficiency trade-off that limits practical deployment.

---

## Problem

Fine-grained cross-view geolocalization (FG-CVG) requires precise localization while operating under strict runtime constraints.  
Existing approaches often trade accuracy for speed or rely on heavy iterative inference, making them unsuitable for real-time applications such as robotics, autonomous navigation, and augmented reality.

---

## Key Idea

We decouple expensive visual reasoning from fast geometric refinement:

1. **Single-pass visual encoding:**  
   Ground and satellite images are processed once using a lightweight backbone and a cross-attention module to extract a shared visual representation.

2. **Fast iterative refinement:**  
   Localization is performed by iteratively refining multiple pose hypotheses using a tiny MLP, enabling robustness without repeatedly running the visual backbone.

This design enables iterative and uncertainty-aware localization while remaining efficient for real-time use.

---

{% include figure.liquid path="/assets/img/cvg_architecture.jpg" title="Model architecture and iterative refinement process" class="img-fluid rounded mx-auto d-block" style="max-width:900px;" %}

---

## Results

The proposed framework achieves compelling localization accuracy on benchmarks such as **KITTI** and **VIGOR**, while showing strong runtime efficiency.

---

<div class="row justify-content-center">
  <div class="col-md-7">
    {% include figure.liquid path="/assets/img/cvg_qualitative.jpg" title="Iterative refinement of pose hypotheses" class="img-fluid rounded mx-auto d-block" style="max-width:700px;" %}
  </div>
  <div class="col-md-5">
    {% include figure.liquid path="/assets/img/cvg_heatmap.jpg" title="Convergence behavior across refinement rounds" class="img-fluid rounded mx-auto d-block" style="max-width:500px;" %}
  </div>
</div>

