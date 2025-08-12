---
layout: page
title: FGC Scoreboard
category: Projects
permalink: /projects/fgcscoreboard.html
---
<style> 
.site-title {
    font-family: Bebas Neue; 
}

</style>
![scoreboard]({{base.url}}/assets/fgcscoreboard/scoreboardpanel.png)

# Intro
Github: [https://github.com/MrKredos/FGCScoreBoardOBS](https://github.com/MrKredos/FGCScoreBoardOBS) 

Makes it easier for you to edit OBS scenes without having to edit them directly, especially if you just want to edit some values such as names, scores, game, etc. 

NOTE: You do need some sort of HTML/CSS/JS experience.

## Setup 
Note: Tested with OBS 31.0.0-rc1, should theoretically work with most versions of OBS.

1. Add ```panel.html``` as a dock
    - Docks -> Customer Browser Docks.. -> Add dock name + ```http://absolute/C:/"ENTER THE FILE URL HERE"``` -> Apply
2. Add your ```yourOverlay.html``` as a Browser Source
3. Should be good to go from there. (add screenshots for steps)

## How it works 
Uses OBS' built in browser functionality to take advantage of localStorage to communicate. 
Two parts to this: 

- <ins>panel.html</ins> docked to OBS
    - Saves inputs to localStorage
    - Added via custom browser docks (ESSENTIAL)
- <ins>yourOverlay.html</ins> added to scene
    - Reads from localStorage. What it does with it, is something YOU need to create. 



### Things to keep in mind
This only works if you have some sort of HTML and CSS capabilities expertise. If you don't know how to use HTML or CSS, maybe nows a good time to learn? You do you, but I didn't know much before this and just played around with it until I did. I'm not competent but I am more confident in this sort of stuff. I'll write down some of my notes for further reference, or for your reference! 

<strong>Resolution for yourOverlay.html</strong><br>
I would recommend using 1920 width 1080 height, and just upscale or downscale within OBS Studio depending on your requirements. It's a nice round number I suppose. 

<strong>Put everything into divs</strong><br>
Divs are you best friend, especially when using unconventional formatting. Keeps everything clean.  

## Examples

UPDATE ME




