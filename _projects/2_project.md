---
layout: page
title: Reliable Indoor Localization with Adaptive Confidence
description: A GNN-based regression framework for indoor localization with rigorous uncertainty guarantees.
img: /assets/img/indoor_cp_architecture.jpg
importance: 2
category: work
related_publications: true
---

<div class="alert alert-info" role="alert">
  <strong>Status:</strong> This work has been submitted to a top-tier conference and is currently under review.  
  Code and full technical details will be released upon acceptance.
</div>

This project introduces a **reliable indoor localization framework** that performs **continuous position regression** while providing **formal, user-defined uncertainty guarantees**, enabling safer deployment in real-world systems.

---

## Problem

Most indoor localization models output a single point estimate of the user’s location \((x, y)\) without quantifying how reliable that estimate is.  
In practice, sensor noise, multipath effects, and environmental ambiguity can cause large localization errors that are indistinguishable from confident predictions.

This lack of calibrated uncertainty is a major limitation for safety-critical applications such as robotics, navigation, and human–machine interaction.

---

## Key Idea

We design an indoor localization system that performs **precise coordinate regression** while explicitly modeling uncertainty through **adaptive confidence regions**.

Our approach combines two core components:

1. **Graph Neural Networks (GNNs) for Indoor Modeling:**  
   The indoor environment is represented as a graph where nodes correspond to fixed infrastructure elements (e.g., WiFi access points) and the mobile user, while edges capture physical proximity, signal relationships, and network connectivity.  
   This allows the model to reason jointly over sensor measurements and the spatial structure of the indoor network.

2. **Conformal Prediction for Regression:**  
   We apply conformal prediction on top of the regression output to produce **confidence regions** around the predicted \((x, y)\) location.  
   These regions come with **formal statistical guarantees**, ensuring that the true location lies within the region with a user-specified confidence level (e.g., 95%).

Crucially, the confidence regions are **adaptive**: they remain tight in well-observed areas and expand automatically in regions with noisy or ambiguous signals to maintain the desired coverage guarantee.

---

{% include figure.liquid path="/assets/img/indoor_cp_architecture.jpg" title="GNN-based indoor localization with conformal regression" class="img-fluid rounded mx-auto d-block" style="max-width:900px;" %}

<div class="caption">
Sensor measurements (e.g., WiFi, IMU) are processed by a Graph Neural Network that models the indoor network structure, including access points and their relationships to the mobile user.  
Conformal Prediction converts point estimates into adaptive confidence regions with rigorous coverage guarantees.
</div>

---

## Results and Behavior

The model learns **spatially varying uncertainty** across the indoor environment.  
Regions with strong and consistent signal geometry yield compact confidence regions, while ambiguous areas produce larger regions that preserve the user-defined confidence level.

---

{% include figure.liquid path="/assets/img/sacp_error_map.jpg" title="Localization error and uncertainty behavior" class="img-fluid rounded mx-auto d-block" style="max-width:750px;" %}

<div class="caption">
Localization error map illustrating region-dependent uncertainty.  
Areas with lower error correspond to tighter confidence regions, while ambiguous regions exhibit larger uncertainty, which is explicitly captured by the conformal prediction mechanism.
</div>

---

This framework provides a principled and practical solution for **reliable indoor localization**, allowing downstream systems to reason explicitly about positional uncertainty.  
A full technical analysis and experimental evaluation have been submitted for publication.
