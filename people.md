---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: single
permalink: /people/
title: People
---
<h2> Current Lab Members: </h2>

{% for person in site.people %}
  {% if person.Status == "Active" %}
<ul class="people_list">  
    <img src="{{ person.Picture }}" align="left" height="150" width="150"  hspace="50">
    <h2><a href="{{ person.url }}">{{ person.Name }}</a></h2>
    {{ person.Title }}<br>
    <a href="mailto:{{ person.Email }}">{{ person.Email }}</a>
</ul>
  {% endif %}
{% endfor %}

<h2> Former Lab Members: </h2>

{% for person in site.people %}
  {% if person.Status == "Inactive" %}
<ul class="people_list">  
    <img src="{{ person.Picture }}" align="left" height="150" width="150"  hspace="50">
    <h2><a href="{{ person.url }}">{{ person.Name }}</a></h2>
    {{ person.Title }}<br>
    Formerly: {{ person.Formerly}} <br>
</ul>
  {% endif %}
{% endfor %}
