---

layout: page
title: Misc
permalink: /misc/

---

for stuff that doesn't really fit into any of my categories

# Gaming related
[My Gaming Journey]({{base.url}}/misc/gaming)

{% assign posts = site.posts %}

{%- if posts.size > 0 -%}

<div class="misc-list">
    {%- assign date_format = site.minima.date_format | default: "%m/%d/%Y" -%}
    {%- for post in posts -%}
        {% if post.category == "Misc" %}


        <a class="misc-post-title" href="{{ post.url | relative_url }}">
        {{ post.date | date: date_format }} {{ post.title | escape }} 
        </a>
        <div class="misc-post-link"></div>

        {% endif %}
    {%- endfor -%}
    {%- endif -%}

</div>