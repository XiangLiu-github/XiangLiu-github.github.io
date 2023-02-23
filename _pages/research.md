---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
header:
  og_image: "research/ecdf.png"
---

My academic research falls into three main areas: 

### Machine Learning Applications in the Atmospheric Environment

In this area, my research involves generating a global full-coverage ozone dataset using novel machine-learning methods. I also analyze anthropogenic influences on Earth and the resulting feedback to humans. 

### Impacts and Adaptations of the Human System to Climate Change

My main research agenda involves using advanced statistical models to establish relationships between a wide range of outcomes, such as crop yields and SIF, with climate and air pollution. These studies rely on publicly available data from remote sensing and numerical models. 

### Processes and Interactions Between Air Pollution and the Biosphere

I am interested in studying the complex interactions between air pollution and the biosphere. I use various techniques such as statistical learning, geospatial analysis, and big data to investigate the impacts of air pollution on ecosystems and the biosphere's feedback to air pollution. 

In a new avenue of research, I plan to use machine learning and big data to explore the interplay between human and nature. 


<nbsp>

{% include base_path %}

{% assign ordered_pages = site.research | sort:"order_number" %}

{% for post in ordered_pages %}
  {% include archive-single.html %}
{% endfor %}
 
