---
layout: page
title: Afhalen/Leveren
permalink: /categories/
---
{% assign cats =  site.shop | map: 'category' | join: ','  | split: ',' | uniq %}
{% for cat in cats %}
  <h3><a name="{{cat}}">{{ cat }}</a></h3>
  <ul>
  {% for note in site.shop %}
    {% if note.category contains cat %}
    <li><a href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}
