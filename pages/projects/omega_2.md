---
layout: page
title: OMEGA 2
category: Projects
permalink: /projects/omega_2.html
---

<style> 


body {
    background: url("{{base.url}}/assets/omega_2/background.gif");
    background-size: 100%; 
    color: #f0f0f0ff;
}

.page-content {
    font-family: "Bebas Neue"; 
    font-size: 22px;
}

.wrapper {
    background: #00000078;

}

.site-title {
    
    background: linear-gradient(var(--rotation), #e24cb0, #967eeb);
    background-clip: text; 
    font-family: "JetlabMedium"; 
    text-transform: none; 
}

</style> 

<img src="{{base.url}}/assets/omega_2/logo.png">

### Intro
<ins>Theme: </ins> 
OMEGA is a fighting game tournament ran twice a year in Parramatta, NSW, organised by the Western Sydney Fighting Game Club for Western Sydney University, a student run club by a bunch of ex-students and non-students (and a few students).

# Showcase
<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_2/showcase.mp4" type="video/mp4">
</video>
It's hard to see due to the compression and the low bitrate, but there is a playlist of songs during "Starting Soon" and "BRB" scenes, and there is a little thing that reacts to the music. 

# [StreamControl](https://farpnut.net/streamcontrol/){:target="_blank"}
Still using StreamControl for this one. It's a software used for updating scores and stuff. It is pretty old technology. FYI, I did not make this, props to farpnut for the awesome implementation. 

How it works: 
1. Software takes input, saves to file.
2. Add text in OBS that reads from file.
3. Voila!

# Background

<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_2/background.mp4" type="video/mp4">
</video>
Made in AfterEffects. I actually don't remember how I made this. There was a lot of trial and error going on here, and a lot of using waves and trying to mix and match colours that we were using. The purple is a bit random, I forgot how I ended up with that. Obviously inspired by psychedellics visuals. 

Unfortunately this background was terrible for the quality of the streams. The video encoder had no idea how to handle it and as a result, it would bitcrush any scene with the background visible. I was a bit disappointed, but I guess I learned that I can't just do whatever I want and have to be concious of the viewing experience. 

# Transition
<video width="100%" height="100%" controls>
<source src="{{base.url}}/assets/omega_2/transition.mp4" type="video/mp4">
</video>
Something to note, transitions were huge on disk. In order to have transparent pixels, you had to have .avi format, and that severely boosted the video file from originally like 10mbs to 300mbs. 

No green screen capabilities on Stingers as well. 

There is however Track Mattes, but I only have so much time so I just skip it for this time.

# Assets

Good friend [Leo](https://x.com/lonkdoodle){:target="_blank"} created all of the art assets. Amazing artist and one of the tournament organisers. I'm more of a curator who takes an idea and runs away with it. 

### Fonts used
[Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue){:target="_blank"}, the holy grail of fonts. Versatile, clean, free and most importantly monospaced, meaning it's easy to code with and figure out width for elements on the page. Unfortunately, it is overused and I tend to try to avoid it for that reason. I still love using it <br>

Sparse on the fonts this time.

### Comments 

Get in touch if you have any questions! Happy to answer them. 

<figure> 
<img src="{{base.url}}/assets/omega_2/theboys.png" alt="the boys">
<figcaption>The Boys - <a href="https://x.com/lonkdoodle" target="_blank">Leo</a></figcaption>
</figure>