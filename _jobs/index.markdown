---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: splash
permalink: /jobs/index.html
title: Job List
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /images/labgroup_2017.png
  caption: "Photo: A 2017 Lab Party"
excerpt: "Join our Team!"
---
<h2> Currently Open Positions: </h2>
{% for job in site.jobs %}
  {% if job.Status == "Open" %}
<ul>
    <h2><a href="{{ job.url }}">{{job.Type}}: {{ job.title }}</a></h2>
</ul>
  {% endif %}
{% endfor %}

<h2> Previous Positions Available: </h2>
{% for job in site.jobs %}
  {% if job.Status == "Filled" %}
<ul>
    <h2><a href="{{ job.url }}">{{job.Type}}: {{ job.title }}</a></h2>
</ul>
  {% endif %}
{% endfor %}
