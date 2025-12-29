---
layout: page
title: ML-Driven RF Test Compaction
description: Reducing semiconductor RF test time and cost using machine learning.
img: /assets/img/wafer_background.jpg
importance: 3
category: work
---

<div class="alert alert-info" role="alert">
  <strong>Role:</strong> Lead Researcher<br>
  <strong>Collaboration:</strong> Conducted in close collaboration with <strong>GlobalFoundries</strong>.
</div>

This project addresses a critical challenge in modern semiconductor manufacturing: the high cost and long turnaround time associated with post-fabrication testing of radio-frequency (RF) integrated circuits.

---

## Problem

In advanced semiconductor manufacturing, testing is a major cost driver and a key production bottleneck.  
Complex RF chips must undergo thousands of specialized tests using expensive automated test equipment. As device complexity increases, test programs grow longer, leading to increased manufacturing cost and reduced throughput.

At the same time, large volumes of historical RF test data collected from production wafers reveal strong statistical dependencies among many test measurements. These dependencies introduce substantial redundancy that is not explicitly exploited by conventional rule-based or specification-driven test flows.

---

## Key Idea

As the lead researcher on this project, I developed a **machine learning–based RF test compaction framework** that leverages data-driven models to reduce test time while preserving fault coverage and decision reliability.

The central idea is to learn predictive relationships among RF test parameters and use them to infer the outcomes of certain tests from a reduced subset of measurements. To achieve this, the framework:

- Uses supervised learning models to capture nonlinear correlations among thousands of RF test metrics.
- Evaluates multiple model families—including **gradient-boosted decision trees (XGBoost)**, **random forests**, and **support vector machines**—to balance prediction accuracy, robustness, and interpretability.
- Quantifies inference confidence to ensure that eliminated tests can be reliably predicted from retained measurements.
- Automatically constructs a compact test program that mirrors the pass/fail decisions of the full test suite.

The entire pipeline was implemented in **Python**, using **scikit-learn–based workflows** for data preprocessing, model training, validation, and test selection.

---

## Impact

The proposed ML-driven test compaction strategy demonstrated a substantial reduction in RF test time on real manufacturing data from a production environment.  
By executing fewer but more informative tests, the framework enables:

- **Lower testing cost** through improved utilization of expensive automated test equipment.
- **Higher manufacturing throughput**, allowing more devices to be tested per unit time.
- **Shorter time-to-market** for RF products.

Beyond this specific application, the project demonstrates how classical machine learning models, when embedded into an end-to-end decision framework, can meaningfully optimize capital-intensive semiconductor manufacturing processes. We are currently collaborating with engineers at GlobalFoundries to prepare a publication detailing the methodology and experimental results.
