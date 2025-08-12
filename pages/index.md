---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home
permalink: /
---


<style>

.flex-container {
    display: flex; 
    flex-direction: row;
    flex-wrap: wrap-reverse;
    gap: 14px; 

}
.left, .right {
    flex: 1 1 300px;
    flex-wrap: wrap;
}

#breadcrumbs {
    display: none; 
}
</style>

<div class="flex-container"> 
<div class="left"> 
<p> Hi, I'm Patrick! Computer Science graduate, event coordinator, hobbyist, gamer...  </p>

</div> 
<div class="right"> 
<img src="{{base.url}}/assets/R1-09-16.JPG" alt="cloudy, one of my family's cats" >
<em>Cloudy, one of my family's cats. Aug 2023</em>

</div>
</div>

