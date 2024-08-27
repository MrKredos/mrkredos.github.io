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
    display: flex;
    flex: 1 1 300px;
    flex-wrap: wrap;
}
</style>

<div class="flex-container"> 
<div class="left"> 
Living life! I enjoy creating cool experiences and I love learning.

Links
</div> 
<div class="right"> 
<img src="{{base.url}}/assets/R1-09-16.JPG" alt="cloudy, one of my family's cats" >
<em>Cloudy, one of my family's cats. Aug 2023</em>

</div>
</div>