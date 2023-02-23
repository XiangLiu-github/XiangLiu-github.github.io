---
title: "Global ozone data"
layout: single-portfolio
excerpt: "<img src='/images/research/ozone_map.jpg' alt=''>"
collection: research
order_number: 20
header: 
  og_image: "research/ozone_map.jpg"
---

For this project, we utilized various datasets from sources such as remote sensing, reanalysis, and socioeconomic data, along with surface ozone measurements from the Tropospheric Ozone Assessment Report and China National Environmental Monitoring Center. We then developed a cutting-edge machine learning algorithm by combining these datasets to predict ozone levels in areas where data is not available. The algorithm relies on ensemble learning and uses a geographically weighted generalized additive model to stack the predictions of six algorithms. Additionally, we utilized a cluster-enhanced procedure to improve model performance, accounting for spatial heterogeneity.

The key takeaways from our research are: 1) the successful development of the best-fit algorithm, 2) the production of useful ozone maps to evaluate global health impacts, and 3) the coverage of striking increasing trends in China through the dataset. Access to the ozone data is available for free on [Zenodo](../../software).

## Article

"Cluster-Enhanced Ensemble Learning for Mapping Global Monthly Surface Ozone From 2003 to 2019", *Geophysical Research Letters*.

> Surface ozone is damaging to human health and crop yields. When evaluating global air pollution risk, gridded datasets with high accuracy are desired to reflect the local variations in air pollution concentrations. Here, a cluster-enhanced ensemble machine learning method was used to develop a new 0.5-degree monthly surface ozone data set during 2003–2019 by combining numerous informative variables. The overall accuracy of our data set is 91.5% (90.8% for space and 92.3% for time). Historically, populations in South Asia, North Africa and Middle-East, and High-income North America are exposed to the highest ozone concentrations. Globally, the population weighted ozone concentration in the peak season is 47.07 ppbv. Our results highlight that ozone pollution is intensifying in some regions, and implicate air quality management is crucial to secure human health from air pollution.
