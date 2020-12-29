---
layout: page
permalink: /resources/
title: Resources
description: Resources in a variety of areas I've dabbled in
nav: true
---
I've always believed that knowledge should be learned to be shared and this is my attempt at doing so. Below you will find a combination of resources that I've compiled on a variety of topics. If you spot any errors, don't hesitate to point them out.

<div class="resources grid">

  {% assign sorted_resources = site.resources | sort: "importance" %}
  {% for resource in sorted_resources %}
  <div class="grid-item"> 
    {% if resource.redirect %}
    <a href="{{ resource.redirect }}" target="_blank">
    {% else %}
    <a href="{{ resource.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if resource.img %}
        <img src="{{ resource.img | relative_url }}" alt="resource thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title">{{ resource.title }}</h2>
          <p class="card-text">{{ resource.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if resource.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ resource.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if resource.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ resource.github_stars }}-stars"></span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>
