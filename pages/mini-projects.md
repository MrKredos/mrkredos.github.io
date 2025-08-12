--- 

layout: default
title: Mini Projects
permalink: /projects/mini-projects/

---
All of my Mini-Projects, stuff that aren't as significant but I still put in a lot of effort. 

{% assign posts = site.posts %}

{%- if posts.size > 0 -%}

<div class="mini-projects-list">
    {%- assign date_format = site.minima.date_format | default: "%m/%d/%Y" -%}
    {%- for post in posts -%}
        {% if post.category == "Mini Projects" %}


        <a class="mini-projects-post-title" href="{{ post.url | relative_url }}">
        {{ post.date | date: date_format }} {{ post.title | escape }} 
        </a>
        <div class="misc-post-link"></div>

        {% endif %}
    {%- endfor -%}
    {%- endif -%}
</div>

