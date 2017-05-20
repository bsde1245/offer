---
layout: page
title: Categories
permalink: /categories/
---
<div>
    {% assign categories = site.categories | sort %}
    
   

    {% for category in categories %}
    <a name="{{ category[0] }}"></a><h4>{{ category[0] | replace:'-', ' ' }} ({{ category | last | size }}) </h4>
    {% assign sorted_posts = site.posts | sort: 'title' %}
    {% for post in sorted_posts %}
    {%if post.categories contains category[0]%}

      <span style="font-size: 18px;"><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span>&bull;<span  class="post-meta">{{ post.date | date: date_format }}</span>
       <hr>

    {%endif%}
    {% endfor %}

    {% endfor %}
    </div>
