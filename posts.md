---
layout: page
title: Posts
permalink: /posts/
---

This page presents a collection of articles, project updates, and technical notes.

{% assign posts_by_category = site.posts | group_by: "category" %}

{% for category in posts_by_category %}
  <h2>{{ category.name }}</h2>
  <div class="posts">
    {% for post in category.items %}
      <article class="post">
        <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>
        <div class="entry">
          {{ post.excerpt }}
        </div>
        {% if post.illustration %}
          <div class="centered-image">
            <img src="{{ site.baseurl }}{{ post.illustration }}" alt="{{ post.title }}">
          </div>
        {% endif %}
        <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
      </article>
    {% endfor %}
  </div>
  <div class="masthead" style="margin-top: -25px;margin-bottom: -15;"> </div>
{% endfor %}