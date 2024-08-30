---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Home

---


<style>
/*
body{
    background-image: url("/assets/background.gif");
    background-size: cover; 
    height: 100vh;
    padding:0;
    margin:0;
}


.post.h-entry {
    background-color: white; 
}
*/

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
</style>

<div class="flex-container"> 
<div class="left"> 
<p> Hi, I'm Patrick! I like sunsets, long walks on sandy beaches, not allowed to be within 50 metres from a school. </p>
<h2>Links</h2> 
{% assign pages = site.pages | sort: 'title' %}
<ul class="page-list">
    {% for page in pages %}
        {% unless page.title == "Home" %}      
            <li>
            <a class="page-link" href="{{ page.url | relative_url }}">
            {{ page.title | escape }}
            </a>
            </li>
            
        {% endunless %}
    {% endfor %}
</ul>
</div> 
<div class="right"> 
<img src="{{base.url}}/assets/R1-09-16.JPG" alt="cloudy, one of my family's cats" >
<em>Cloudy, one of my family's cats. Aug 2023</em>

</div>
</div>

