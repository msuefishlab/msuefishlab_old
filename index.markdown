---
author: Jason Gallant
comments: false
date: 2018-06-21
title: Welcome to the MSU Electric Fish Lab!
author_profile: true
layout: landing
header:
  overlay_color: "#000"
  overlay_filter: "0.2"
  overlay_image: /images/kingsleyae_electricorganwhole.png
  caption: "Photo: The Electric Organ of _Paramormyrops kingsleyae_ "
excerpt: " \"The electric organs of fishes offer another case of special difficulty; it is impossible to conceive by what steps these wondrous organs have been produced...\" - Charles Darwin _The Origin of Species_ "
---


## About Our Research
The Gallant laboratory is broadly interested in the origin and diversification of novel phenotypic and behavioral traits involved in animal communication signals.  Diverse communication signals are often associated with species radiations, implying an important link between signal diversity and the speciation process.
{% include video id="qWjus4t8RXc" provider="youtube" %}{: .right_set_video_container}
We explore these broad questions in mormyrid electric fish from Africa, which are ideally suited to highly integrative experimental approaches.  In the laboratory, we perform our analyses across many levels of biological organization, from the genome to populations.  

<!-- <h3>Open Positions: </h3>
<ul>
{% for job in site.jobs %}
  {% if job.Status == "Open" %}
<ul>&raquo;  <a href="{{ job.url }}">{{job.Type}}: {{ job.title }}</a></ul>
  {% endif %}
{% endfor %}
</ul> -->

<h3>Recent News: </h3>
<ul>
{% for post in site.tags.news offset: 0 limit: 5  %}
  <ul>&raquo; <a href="{{ post.url }}">{{ post.title }}</a></ul>
{% endfor %}
</ul>
