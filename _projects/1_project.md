---
layout: page
title: "GeoFlow: Real-Time Fine-Grained Cross-View Geolocalization via Iterative Flow Prediction"
description: A lightweight, real-time framework for fine-grained cross-view geolocalization.
img: /assets/img/cvg_architecture.jpg
importance: 1
category: work
related_publications: true
---

<div class="alert alert-info" role="alert">
  <strong>Status:</strong> This work has been accepted to CVPR 2026 (main conference track).  
  Code, Paper and full technical details will be released soon.
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
   Ground and satellite images are processed once using lightweight CNN backbones and a cross-attention module to extract a shared visual representation.

2. **Fast iterative refinement:**  
   Localization is performed by iteratively refining multiple pose hypotheses using a compact MLP, enabling robustness without repeatedly running the visual backbone.

This design enables iterative and uncertainty-aware localization while remaining efficient for real-time use.

---

<div class="project-figure-large">
  {% include figure.liquid
     path="/assets/img/cvg_architecture.jpg"
     title="Model architecture and iterative refinement"
  %}
</div>

---

## Technical Details

This framework was implemented with a strong emphasis on **efficiency, modularity, and real-time deployment**:

- **Framework:** PyTorch  
- **Visual encoders:** Lightweight CNN backbones (e.g., EfficientNet, ConvNet-style architectures)  
- **Cross-view fusion:** Cross-attention mechanism for aligning ground-level and satellite feature representations  
- **Localization head:** Small MLP predicting probabilistic displacement (distance and direction)  
- **Inference strategy:** Multi-hypothesis iterative refinement with shared visual features  
- **Training:** End-to-end supervised learning with regression-based objectives  
- **Benchmarks:** Evaluated on standard FG-CVG datasets including **KITTI** and **VIGOR**

The architecture is designed such that computationally expensive components are executed only once, while refinement operates entirely in a low-dimensional latent space.

---

## Results

The proposed framework achieves compelling localization accuracy on benchmarks such as **KITTI** and **VIGOR**, while maintaining strong runtime efficiency suitable for real-time applications (~30 FPS(Frame Per Second)).

---

<!-- Figure 1 -->
<div class="row justify-content-center">
  <div class="col-md-8">
    <div class="project-figure-medium">
      {% include figure.liquid
         path="/assets/img/cvg_qualitative.jpg"
         title="Iterative refinement of pose hypotheses"
      %}
    </div>
  </div>
</div>

<!-- Figure 2 -->
<div class="row justify-content-center mt-4">
  <div class="col-md-8">
    <div class="project-figure-medium">
      {% include figure.liquid
         path="/assets/img/cvg_heatmap.jpg"
         title="Refinement convergence behavior"
      %}
    </div>
  </div>
</div>
