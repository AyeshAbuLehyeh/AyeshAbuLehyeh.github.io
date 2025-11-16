---
layout: page
title: Reliable Indoor Localization with Adaptive Confidence
description: A GNN framework for indoor localization with rigorous uncertainty guarantees.
img: /assets/img/indoor_cp_architecture.jpg
importance: 2
category: work
related_publications: true
---

<div class="alert alert-info" role="alert">
  <strong>Note:</strong> This work has been submitted to a top-tier conference and is currently under review.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/indoor_cp_architecture.jpg" title="Model Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our model's architecture. Sensor data (e.g., WiFi/IMU) is processed by a Graph Neural Network (GNN) that understands the building's floorplan graph. Instead of a single "best guess," our method uses Conformal Prediction to output a <b>prediction set</b> (e.g., a set of rooms, highlighted in yellow) with a mathematically guaranteed confidence level.
</div>


This paper introduces **a novel framework for reliable indoor localization** that provides rigorous, user-defined confidence guarantees.

### The Problem

Standard indoor localization models are often "black boxes." They provide a single "best guess" for a user's location (e.g., "Room 101") but give no reliable way to know *how confident* they are. This is a critical failure for real-world applications. A model might be 99% certain or 10% certain, but the output looks the same, leading to a risk of "confident failure" in robotics or emergency services.

### Our Solution

Our model is designed to provide not just a location, but a **trustworthy prediction set**. We achieve this by combining two key technologies:

1.  **Graph Neural Networks (GNNs):** We model the indoor environment (rooms, corridors, etc.) as a graph. This allows our model to learn the complex spatial relationships of a building's layout, far better than models that treat each room in isolation.
2.  **Conformal Prediction (CP):** We apply a CP framework on top of our GNN's output. Conformal Prediction is a powerful statistical tool that can provide a *mathematically guaranteed* confidence level. Instead of a single point, our model outputs a *set* of possible locations and guarantees that the true location is within that set (e.g., 95% of the time).

A key feature of our method is that these prediction sets are **adaptive**. When the model is highly confident, the set is small (e.g., a single room). When the model is uncertain (due to noisy signals), the set automatically grows larger to maintain the 95% guarantee.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sacp_error_map.jpg" title="Localization Error Map" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our model's localization error map, demonstrating its ability to learn regional confidence. Regions like <b>R1</b> and <b>R4</b> show low localization error, indicating high model confidence. In contrast, other areas exhibit higher error due to more ambiguous sensor data. Our method learns this and adaptively expands the prediction set size in these low-confidence regions to maintain the user-defined confidence guarantee.
</div>

This approach provides a reliable and practical solution for safety-critical systems, as the downstream application can now understand and act on the model's uncertainty. A full analysis of our method and results has been submitted for publication.
