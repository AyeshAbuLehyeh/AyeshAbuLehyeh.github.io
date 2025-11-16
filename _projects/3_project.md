---
layout: page
title: ML-Driven RF Test Compaction
description: Reducing semiconductor test time and cost at GlobalFoundries using machine learning.
img: /assets/img/wafer_background.jpg
importance: 3
category: work
---

<div class="alert alert-info" role="alert">
  <strong>Role:</strong> Lead Researcher<br>
  <strong>Collaboration:</strong> This project was conducted in close collaboration with <strong>GlobalFoundries</strong>.
</div>

This project addresses one of the most significant challenges in modern semiconductor manufacturing: the high cost and time associated with post-fabrication testing of Radio Frequency (RF) chips.

### The Problem

In semiconductor manufacturing, testing is a primary cost driver and a major production bottleneck. Every complex RF chip must undergo thousands of rigorous tests on extremely expensive, specialized equipment. As chip complexity increases, the number of tests explodes, consuming valuable time and resources, which directly impacts the final product cost and time-to-market.

### Our Solution

As the lead researcher on this project, I developed a machine learning framework to tackle this problem through **RF test compaction**. The core objective was to intelligently reduce the number of tests required, without any loss in quality assurance or fault detection.

Our solution works by:
* Analyzing vast historical datasets of test results from the GlobalFoundries manufacturing line.
* Training a machine learning model to understand the complex correlations and dependencies between thousands of different RF test parameters.
* Intelligently identifying and pruning redundant tests that provide low informational value (i.e., their results could be predicted by other tests).
* Generating a final, highly "compacted" test program that provides the same rigorous quality guarantee in a fraction of the time.

### The Impact

This ML-driven approach demonstrated a significant reduction in test time for RF semiconductor products. By running fewer, smarter tests, the framework directly enables:
* **Dramatic Cost Savings:** Frees up expensive testing equipment, reducing capital expenditure.
* **Increased Manufacturing Throughput:** Allows more chips to be processed per day.
* **Faster Time-to-Market:** Speeds up the entire production and validation pipeline.

This work serves as a powerful case study for how modern machine learning techniques can be applied to optimize capital-intensive industrial processes. We are currently collaborating with engineers at GlobalFoundries to author a paper detailing the results of this applied research.
