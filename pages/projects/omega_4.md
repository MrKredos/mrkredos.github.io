---
layout: page
title: OMEGA 4
category: Projects
permalink: /projects/omega_4.html
---

<style> 


body {
    background: url("{{base.url}}/assets/omega_4/background.png");
    background-size: 100%; 
    color: #f0f0f0ff;
}

.page-content { 
    font-size: 22px;
}

.wrapper {
    background: #00000078;

}
#four-images {
    display: flex; 
    fustify-content: space-between;
    width: inherit; 
}
.image {
    flex: 1;
    min-width: 0; 
}

.site-title {
    letter-spacing: 0px;
    background: linear-gradient(var(--rotation), #e24cb0, #967eeb);
    background-clip: text; 
    font-family: "Rawhide Raw 2016"; 
    text-transform: none; 
    text-shadow: red 2px 5px;
    a {
        color: white; 
    }
}


</style> 

<img src="{{base.url}}/assets/omega_4/logoAdjusted.png">

### Intro
<ins>Theme:</ins> Heroes and Villians, ArtDeco Style, old timey comics. <br>
It was a little difficult because people were burnt out and I didn't have much to work with, so I tried my best. The theme that I tried to go for was more related to art deco with a focus on the classy side of it. Didn't really fit the heroes and villian theme thinking about it lol 

OMEGA is a fighting game tournament ran twice a year in Parramatta, NSW, organised by the Western Sydney Fighting Game Club for Western Sydney University, a student run club by a bunch of ex-students and non-students (and a few students).

# Showcase
<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_4/showcase.mp4" type="video/mp4">
</video>
Playlist was just classical music. I thought all classical music was copyright free because of how old they are, but apparently different recordings have copyright on them... so some of the vods had been caught because of that. But not a big deal since we don't make any money from this. 

# [FGC Scoreboard]({{site.url}}/projects/fgcscoreboard)
Reused from previous OMEGA, with some minor adjustments, namely 4 player capabilities and crew battles. I want to say more but it's all pretty self explanatory I think.

Crew battles creates HTML when adding players, and kills the HTML when removing. It actually works a lot better than my current implementation, so maybe one day I'll rebuild everything from scratch with my current knowledge (never gonna happen knowing me).

4 Player capabilities, I just added 2 extra players, and maybe my code a bit more scalable for when we need have more than 4 players. Not sure when that will be needed, but when the time comes I'll make it.

See link for how it works and how to use it. 

# Background
**First Attempt**
<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_4/firstattempt.mp4" type="video/mp4">
</video>
[oldbackground.html]({{base.url}}/misc/oldbackground.html)


**Final**
<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_4/background.mp4" type="video/mp4">
</video>

I spent too much time trying to make a really cool background.

For the longest time, I wanted to create a background that you can change the details for (like the player names showing up, or maybe the game name), and the perfect way for this is to do this via HTML/CSS/JS and reading values from localStorage. It was just a proof of concept, but it didn't work out so I didn't go too much further into it. 

The issue with my original.html implementation is that it is too heavy. Everytime you leave the scene, it will do some cpu saving measures which will affect the background when you re-enter the scene. It will jitter a bunch, and this happens on my pretty hefty computer. I did some research and websites only work with 1 cpu core (since you have so many tabs open) and this is just something you have to work around. If I were to attempt this again, maybe keep the performance tight on the background.html (currently rotates on the 3D plane which adds a lot of caclulations for anti-aliasing) and also maybe give myself like 0.5 seconds of leeway before transitioning into a new scene just for the background.html to get itself ready.

# Transition

<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_4/transition.mp4" type="video/mp4">
</video>
Learned about masks! OBS has Mask capabilities and so I just did something simple. I liked the idea of the 3rd Strike transition, (forgot what it's called, I think venetian blinds?) but I also didn't like how static it was and just did a gradient time mask that would focus on a specific spot. The circle actually ended at a logo for the event, but I ended up scrapping that but keeping the time mask. 

# Assets

Good friend [Leo](https://x.com/lonkdoodle){:target="_blank"} created all of the art assets. Amazing artist and one of the tournament organisers. I'm more of a curator who takes an idea and runs away with it. 

### Fonts used
[ArtDeco MN](https://fonts.adobe.com/fonts/artdeco-mn){:target="_blank"}. ArtDeco, nothing much to say. 

[CopperPlateGothic](https://learn.microsoft.com/en-us/typography/font-list/copperplate-gothic){:target="_blank"}. Pretty sure it comes with Windows? I can't remember where I found this to be honest. 

Trying to move away from Bebas Neue just because I use it too much. 

### Comments 

Get in touch if you have any questions! Happy to answer them. 

