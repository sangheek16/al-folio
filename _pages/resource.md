---
layout: page
title: Resource
permalink: /resource/
description: A collection of useful resource.
nav: true
---

<div class="resource grid">

  {% assign sorted_resources = site.resource| sort: "importance" %}
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
          <h2 class="card-title text-lowercase">{{ resource.title }}</h2>
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
              </span>
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
