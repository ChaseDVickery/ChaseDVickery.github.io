---
title: "Offline Inverse Reinforcement Learning."
collection: projects
permalink: /projects/2024-offline-irl
excerpt: 'Investigated offline preference data selection methods to choose the most helpful preference pairs for model reward tuning with distribution entropy estimates obtained from Stein Variational Gradient Descent (SVGD).'
date: 2024-07-21
---

### Description
Investigated offline preference data selection methods to choose the most helpful preference pairs for model reward tuning with distribution entropy estimates obtained from Stein Variational Gradient Descent (SVGD).

<!-- In SVGD, particles' movements are also dependent upon the number and proximity of nearby particles -->
In the first part of the training loop, we used SVGD to train an initial sampler distribution to create a good spread of sampled points across our target distribution (a Bradley-Terry (BT) pairwise preference model) using the <a href="https://gregorygundersen.com/blog/2018/04/29/reparameterization/">reparameterization trick</a>.
In the second part of the training loop, we used the entropy value estimated from SVGD to calculate estimated optimal preference pairs, represented by a vector, delta. We queried our database of filtered offline preference pairs and selected M new preferences to incorporate into our BT model, thus quickly honing in on the subset of preferences that creates the most accurate and smallest potential space for our target model.
This can be helpful for quickly selecting the most informative pairs of LLM responses from a huge potential dataset, for example.

This was also the impetus for creating my <a href="https://chasedvickery.github.io/BradleyTerryVisualizer/">2D Bradley-Terry probability visualizer</a>.

<!-- Replace path up to /files with http://ChaseDVickery.github.io/ or http://localhost:4000/ -->
<img src="http://ChaseDVickery.github.io/files/irl/svgd1.gif">
<img src="http://ChaseDVickery.github.io/files/irl/svgd2.gif">
<img src="http://ChaseDVickery.github.io/files/irl/svgd3.gif">