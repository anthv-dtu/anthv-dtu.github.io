---
layout: page
title: Ship-Shore Communication
description: Intelligent control of ship-shore communication systems for remote situational awareness (PhD project, DTU Electro, 2024 – 2027)
img: assets/img/research/maritime-autonomy.webp
importance: 1
related_publications: true
---

<img class="project-hero-img" src="{{ '/assets/img/research/maritime-autonomy.webp' | relative_url }}" alt="Maritime remote and autonomous systems">

**PhD project, DTU Electro (December 2024 – present)**<br>
Supervisor: [Assoc. Prof. Dimitrios Papageorgiou](https://dimpapageorgiou.github.io/), Control, Robotics & Embodied AI (CREA).

## Motivation

As vessels become more autonomous, operators ashore need a reliable, real-time picture of what is happening on board and around the ship.
Ship–shore communication links are time-varying, uncertain and multi-channel. Link quality can change quickly with distance, sea state,
the vessel's motion and the surroundings.

## Approach

The project develops control and estimation methods that keep remote situational awareness reliable under these conditions:

- **Maritime channel modelling.** A time-varying multi-cluster fluctuating two-ray fading model that captures large-scale fading,
  Doppler shifts and time-varying phase and delay in the maritime environment {% cite vie2025fading %}.
- **Robust adaptive control.** Multi-layer barrier function-based adaptation of the super-twisting sliding-mode controller. The
  controller tunes itself to unknown perturbation bounds without being overly conservative {% cite vie2025barrier %}. It has been
  extended to discrete time, where it handles the controller's inter-sample blindness {% cite vie2026discrete %}.
