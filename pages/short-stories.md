--- 
layout: page
title: Short Stories
permalink: /short-stories/

---
### Intro
<u>Some stories may contain thoughts may contain sensitive or explicit topics, not suitable for all ages. View at your own discretion!</u>

I've never been one for writing even since I was younger, I didn't read much either, but sometimes ideas and stories just come to my head and I just have to write them down and has been more apparent in recent years. I have a journal where I write my thoughts down everyday that doubles up as a dreams diary and short story writing excersises. I think whatever I write here is not necessarily a "short story" but more like an extended thought that could act as a story idea. Please enjoy! 

## Stories, sorted by oldest 

I'll update this page sooner with better viewing experience, just wanted to get stuff down first. 

{% for short-stories in site.data.short-stories %}
<h3> {{short-stories.title }} </h3>
<p> {{ short-stories.content }} </p>
{% endfor %}    
