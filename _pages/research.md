---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
header:
  og_image: "research/ecdf.png"
feature_row:
 - image_path: /images/android-chrome-192x192.png
   alt: "placeholder image 1"
   title: "Placeholder 1"
   excerpt: "This is some sample content that goes here with **Markdown** formatting."
 - image_path: /images/android-chrome-192x192.png
   alt: "placeholder image 2"
   title: "Placeholder 2"
   excerpt: "This is some sample content that goes here with **Markdown** formatting."
   url: "#test-link"
   btn_label: "Read More"
   btn_class: "btn--inverse"
---

My academic research falls into three main areas: machine learning applications in the atmospheric environment, impacts and adaptations of the human system to climate change, and processes and interactions between air pollution and the biosphere. One strand of research in this first area generates a global full-coverage ozone dataset that relies on a novel machine-learning method. My interests in environmental studies and atmospheric science also inform the projects on analyzing the anthropogenic influences on Earth as well as the feedback to humans.

My main research agenda uses advanced statistical models to establish the relationships between a wide range of outcomes (crop yields and SIF) with climate and air pollution. These researches are relying on publicly available data from remote sensing and numberic models. In a new avenue of research, I plan to use machine learning and big data to explore the interplays between human and nature.

<nbsp>

{% include base_path %}

{% assign ordered_pages = site.research | sort:"order_number" %}

{% for post in ordered_pages %}
  {% include archive-single.html type="grid" %}
{% endfor %}
 
{% include feature_row %} 
