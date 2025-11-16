---
layout: page
title: Efficient Cross-View Geolocalization
description: A highly efficient, real-time framework for cross-view geolocalization.
img: /assets/img/cvg_architecture.jpg
importance: 1
category: work
related_publications: true
---

<div class="alert alert-info" role="alert">
  <strong>Note:</strong> This work has been submitted to a top-tier conference and is currently under review.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cvg_architecture.jpg" title="Model Architecture and Refinement" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The top panel illustrates our model's architecture. Ground ($\mathbf{I}_g$) and satellite ($\mathbf{I}_s$) features are extracted, then fused by a Cross-Attention block to produce a visual representation, $\mathbf{f}_{vis}$. This is concatenated with a pose hypothesis $\mathbf{q}_0$ and fed into two regression heads to predict the probabilistic displacement (distance and direction). The bottom panel shows our iterative refinement algorithm, where a population of random hypotheses (red dots) iteratively "flows" to a converged, robust estimate (yellow dot).
</div>


This paper introduces **a lightweight and highly efficient framework** for fine-grained cross-view geolocalization (FG-CVG).

### The Problem

Current methods for FG-CVG force a difficult trade-off: high-accuracy models are too slow for real-time applications, while fast models are often inaccurate. This is a major barrier for practical deployment in autonomous navigation or augmented reality.

### Our Solution

Our model breaks this accuracy-speed trade-off. We designed a lightweight, probabilistic regression model that achieves state-of-the-art efficiency while maintaining highly competitive accuracy.

Our method has two key components:
1.  **An Efficient Architecture:** We use a lightweight EfficientNet backbone and a cross-attention module to extract visual context. This expensive step is run **only once**.
2.  **Iterative Refinement:** Our novel inference algorithm. Instead of trusting one guess, it refines a population of random hypotheses. Because this iterative loop only runs on a tiny MLP (not the full backbone), it is **exceptionally fast**.

This design allows our model to be both iterative (for robustness) and extremely fast (for real-time use), running at **~29 FPS**.

### Key Results

Our model is not only fast but also highly accurate. We achieve competitive mean-error results on the challenging **KITTI** and **VIGOR** datasets, outperforming other SOTA methods in key efficiency metrics.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cvg_qualitative.jpg" title="Qualitative Results" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cvg_heatmap.jpg" title="Refinement Convergence" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <b>Left:</b> Qualitative examples showing how our learned regression field guides random initial hypotheses (colored dots) toward the ground truth (red X) over 10 refinement rounds.
    <b>Right:</b> A visualization of our refinement dynamics, showing how a scattered set of hypotheses (R=1) converges into a tight, confident cluster by round 4 (R=4).
</div>

A full analysis of our method and results has been submitted for publication.
