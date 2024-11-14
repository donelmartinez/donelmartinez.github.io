---
layout: page
title: Blog
permalink: /blog/
---

My blogs are focused on <a href="/categories/#macros" style="font-weight:normal;"> Macros</a>, <a href="/categories/#diferentialprivacy" style="font-weight:normal;"> Differential Privacy</a>, <a href="/categories/#federatedlearning" style="font-weight:normal;"> Federated Learning</a>, <a href="/categories/#ai" style="font-weight:normal;"> Artificial Intelligence</a>, <a href="/categories/#machinelearning" style="font-weight:normal;"> Machine Learning</a>, and general <a href="/categories/#Compliance" style="font-weight:normal;"> Privacy and Information Security Compliance</a>.

<ul class="listing">
{% for category in site.categories %}
  <li class="listing-separator">{{ tag[0] }}</li>
    {% for post in tag[1] %}
      <li class="listing-item">
        <a href="{{ post.url }}" title="{{ post.title}}">{{ post.title }}</a>
      </li>
    {% endfor %}
{% endfor %}

{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator">{{ y }}</li>
  {% endif %}
  <li class="listing-item">
    <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
