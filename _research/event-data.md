---
title: "Conflict event data"
layout: single-portfolio
excerpt: "<img src='/images/research/ozone_map.jpg' alt=''>"
collection: research
order_number: 20
header: 
  og_image: "research/ozone_map.jpg"
---

In this project, We used numerous datasets from remote sensing, reanalysis, socioeconomic, and etc. sources, which integrate with the surface ozone measurements from Tropospheric Ozone Assessment Report and China National Environmental Monitoring Center. We then develop a state-of-the-art machine learning algorithm based on the combined tabular dataset to predict the ozone levels where data are not available. This model is based on ensemble learning that uses a geographically weighted generalized additive model to stack predictions of six algorithms. Furthermore, we used a cluster-enhanced procedure to enhance the model performance, because it can partially account for the spatial heterogeneity.

The key findings of this paper are that 1) the best-fit algorithm we developed, 2) the produced ozone maps can be useful to evaluate the global health impacts of ozone, and 3) the striking increasing trends in China are covered from this dataset. The ozone data is freely accessible in [Zenodo](../../software).

## Article

"Cluster-Enhanced Ensemble Learning for Mapping Global Monthly Surface Ozone From 2003 to 2019", *Geophysical Research Letters*.

> Surface ozone is damaging to human health and crop yields. When evaluating global air pollution risk, gridded datasets with high accuracy are desired to reflect the local variations in air pollution concentrations. Here, a cluster-enhanced ensemble machine learning method was used to develop a new 0.5-degree monthly surface ozone data set during 2003–2019 by combining numerous informative variables. The overall accuracy of our data set is 91.5% (90.8% for space and 92.3% for time). Historically, populations in South Asia, North Africa and Middle-East, and High-income North America are exposed to the highest ozone concentrations. Globally, the population weighted ozone concentration in the peak season is 47.07 ppbv. Our results highlight that ozone pollution is intensifying in some regions, and implicate air quality management is crucial to secure human health from air pollution.
