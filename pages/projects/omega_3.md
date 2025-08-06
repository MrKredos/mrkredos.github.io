---
layout: page
title: OM3GAMANIA
category: Projects
permalink: /projects/omega_3.html
---

<style> 


body {
    background: url("{{base.url}}/assets/omega_3/background.png");
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

<img src="{{base.url}}/assets/omega_3/logo.png">

### Intro
<ins>Theme:</ins> Wrestling. 

OMEGA is a fighting game tournament ran twice a year in Parramatta, NSW, organised by the Western Sydney Fighting Game Club for Western Sydney University, a student run club by a bunch of ex-students and non-students (and a few students).

# Showcase
<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_3/showcase.mp4" type="video/mp4">
</video>
It's hard to see due to the compression and the low bitrate, but there is a playlist of songs during "Starting Soon" and "BRB" scenes, and there is a little thing that reacts to the music. 

Playlist is just music from WWE, unfortunately some of the music was copyrighted so we had to mute parts of the vod. I think in future we will only be using copyright free music, or better yet, music will only show on the livestream but not the VOD. 

# [FGC Scoreboard]({{site.url}}/projects/fgcscoreboard)
Replaced StreamControl, as it was too cumbersome to use. 

See link for how it works and how to use it. 

# Background

<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_3/background.mp4" type="video/mp4">
</video>
Made in AfterEffects. Basic wave stuff, very simple. 

# Transition
<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_3/transition.mp4" type="video/mp4">
</video>
This went through many, many renditions. Changing colours, changing speed values, changing spotlight colours and directions, changing images... A lot went into this specific thing.

It's pretty simple when you break it down:
- A sliding background transition with bayer dithering
- Logo swooping in with keyframes, easing and motion blur.
    - The logo is actually a 3D object that rotates on the a 3D plane. 
- Crowd.png coming from bottom of the screen with keyframing up and down to simulate movement. 
    - Fun fact, this is from Club Penguin lol
- Spot light effect brightening the background (only the background) 
- Then everything swoops out of frame. 

### [Transition Tables](https://obsproject.com/forum/resources/transition-table.1174/){:target="_black"}
Someone made a plugin where transitions only activate depending on what scene you are coming from or what scene you are going to. 

I just put transitions to the gameplay scenes and from starting soon scene. 

# Assets

Good friend [Leo](https://x.com/lonkdoodle){:target="_blank"} created all of the art assets. Amazing artist and one of the tournament organisers. I'm more of a curator who takes an idea and runs away with it. 

### Fonts used
[Coolvetica](https://www.dafont.com/coolvetica.font){:target="_blank"}. Nice looking font I suppose, easy to use. Free for personal use. 

[Rawhide Raw 2016](https://www.dafont.com/rawhide-raw-2016.font){:target="_blank"}. Similar vibes to the WWE RAW font, and its free for personal use. 

Trying to move away from Bebas Neue just because I use it too much. 

### Comments 

Get in touch if you have any questions! Happy to answer them. 

<figure id="four-images">
<img src="{{base.url}}/assets/omega_3/pot.png" class="image">
<img src="{{base.url}}/assets/omega_3/zangief.png" class="image">
<img src="{{base.url}}/assets/omega_3/incin.png" class="image">
<img src="{{base.url}}/assets/omega_3/king.png" class="image">
</figure>
<figcaption>The Boys - <a href="https://x.com/lonkdoodle" target="_blank">Leo</a></figcaption>
