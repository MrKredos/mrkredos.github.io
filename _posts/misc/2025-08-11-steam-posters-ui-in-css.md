---
layout: post
title: Steam Posters UI in CSS
date: 2025-08-11 
category: Misc
permalink: /misc/movies.html
---

<div class="three-row">
    <div class="container">
        <div class="image">
            <div class="shine"></div>
            <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="normal" />
            <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="blur" />
        </div>
    </div>
    <div class="container">
        <div class="image">
            <div class="shine"></div>
            <img src="https://image.tmdb.org/t/p/original/uDO8zWDhfWwoFdKS4fzkUJt0Rf0.jpg" class="normal" />
            <img src="https://image.tmdb.org/t/p/original/uDO8zWDhfWwoFdKS4fzkUJt0Rf0.jpg" class="blur" />
        </div>
    </div>
    <div class="container">
        <div class="image">
            <div class="shine"></div>
            <img src="https://image.tmdb.org/t/p/original/u68AjlvlutfEIcpmbYpKcdi09ut.jpg" class="normal" />
            <img src="https://image.tmdb.org/t/p/original/u68AjlvlutfEIcpmbYpKcdi09ut.jpg" class="blur" />
        </div>
    </div>
</div>

<div class="button-container">
    <button id="shine-toggle" onClick="toggleShine()">Toggle Shine</button>
    <button id="drop-shadow-toggle" onClick="toggleDropShadow()">Toggle Drop Shadow</button>
    <button id="blur-shadow-toggle" onClick="toggleBackgroundBlur()">Toggle Background Blur</button>
    <button id="hover-toggle" onClick="toggleHover()">Toggle Hover</button>
</div>


### Intro
I wanted to have a page showing off my favourite movies with their posters. I decided I wanted to recreate the Steam Library Posters UI, because it looks great and wanted to try my hand at a little challenge. It took me maybe a day of hard work but I'm proud that I'm finally done with this.

WIP Adding how it works later. 
### How it was made
## Shine

This is two states, and you interpolate between the two. 



```css
/* Idle */ 
.image-demo {
    background: linear-gradient( 
        30deg,
        rgba(255, 255, 255, 0) 0%,
        rgba(255, 255, 255, 0) 74%,
        rgba(255, 255, 255, 0) 77%,
        rgba(255, 255, 255, 0.01) 100%
    ); 
}
/* Hover */
.image-demo:hover { 
    background: linear-gradient( 
        30deg,
        rgba(255, 255, 255, 0) 0%,
        rgba(255, 255, 255, 0.02) 53%, /* there is actually tiny bit of shine on the whole image on */
        rgba(255, 255, 255, 0.02) 55%, /* hover which is why opacity has been adjust ever so slightly */ 
        rgba(255, 255, 255, 0.2) 100%
    ); 
}
```

<div class="container">
    <div class="container">
        <strong>Shine</strong> <br> 
        Hover/Tap me!
    </div> 
    <div class="image-demo" style="justify-content:center; flex: none;">
        <div class="shine-demo" style="text-align: center;"></div>
        <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg"/>
    </div>
</div>
<div class="three-row" >
    <div class="container" style="justify-content:center; flex: none;">
    Idle
        <img src="{{base.url}}/assets/images/idle.png" class="img-demo"> 
    </div>
    <div class="container" style="justify-content:center; flex: none;">
    Hover
        <img src="{{base.url}}/assets/images/hover.png" class="img-demo">
    </div>
</div>
On both of the images, marked <span style="color:red">red</span> the two positions on hover and on idle. 

I used gradients for this, using this helpful website [https://cssgradient.io/](https://cssgradient.io/){:target="_blank"} for getting the right numbers. 

There are different ways to do this and this is definitely not the easiest way, you could have a CSS shape that has transitions and just hide the overflow. And by doing this, you effectively would make this build CSS only. 

However hindsight is 20/20, this first thing that came to mind so I stuck with it. If I were to recreate it, I'll just do it with CSS shapes. 

**transition:** <br>
Unfortunately for me, you are unable to interpolate linear-gradients with vanilla CSS, so I had to get a little hands on with finding a way to animate the eases, the solution I came up with was using GSAP [https://gsap.com/](https://gsap.com/){:target="_blank"} where they have a function for interpolation. I did want to do the interpolation myself, but honestly that's just a rabbit hole and there are already so many implementations for it. 



## Hover 

Three parts put together:

```css
.image-demo {
    transform: 
        /*1.*/ perspective(1500px) 
        /*2.*/ scale(1.03) 
        /*3.*/ rotate3d(1, 0, 0, 10deg);

    /* these two are explained below! */ 
    transform-origin: 50% -10px; 
    transition: transform 0.6s cubic-bezier(0, 1, 0.4, 1);
}
``` 

<div class="three-row" >
    <div class="container" style="justify-content:center; flex: none;">
    <strong>Perspective</strong> transform: perspective(1500px);
        <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="image-demo" id="perspective-demo"> 
        Only works with rotate3d
    </div>
    <div class="container" style="justify-content:center; flex: none;">
    <strong>Scale</strong> transform: scale(1.03);
        <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="image-demo" id="scale-demo">
    </div>
    <div class="container" style="justify-content:center; flex: none;">
    <strong>Rotate3D</strong> transform:  rotate3d(1, 0, 0, 10deg);
        <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="image-demo" id="rotate3d-demo">
    </div>
    <div class="container" style="justify-content:center; flex: none;">
    <strong>All together</strong> 
        <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="image-demo" id="hover-demo">
    </div>
</div> 

Notice how <ins>rotate3D</ins> just flattens the image? Very odd but I suppose it makes sense, assuming you're in a 2d universe that is exactly how it would appear. There is a function that makes it look like it is rotating in 3D and that's by using the <ins>perspective</ins> function within transform.

**transform-origin:** <br>
<ins>transform-origin</ins> is used to change the rotate origin point towards the top of the image. Transforming with the origin in the middle doesn't look right. You can disable <ins>transform-origin</ins> in inspect mode if you want to see how it changes things. 

>TIP: **CRTL + SHIFT + C** lets you select elements on a webpage, super helpful for web development! 

**transition:** <br>
I think finding the right <ins>transition</ins> was difficult, and I don't think I could actually find something that replicates Steam, but that's a job for another day (or another person!). 


## Blur/Background 
```css 
#blur-demo {
    border-radius: 150px;
    transform: scale(1.10);
    top: 50px;
    left: -5px; 
    filter: blur(1.5rem);

    opacity: 0;
    transition: opacity 0.4s ease-out;
    z-index: -1;
}

#image-container:hover #blur-demo { /* when the image is hovered, make the blur visible*/
    opacity: 0.5; 
}
```

```html 
<div class="container" style="justify-content:center; flex:">
    <strong>Blur Background</strong>
    Hover/Tap me!
    <div class="image" id="blur-demo-image">
        <!-- Top is poster, bottom is the blur -->
        <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" style="opacity: 0.25;" />
        <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="image-demo" id="blur-demo"> 
    </div>  
</div>

```
<div class="three-row" >
    <div class="container" style="justify-content:center; flex:">
        <strong>Blur Background</strong>
        Hover/Tap me!
        <div class="image-demo" id="blur-demo-image">
            
            <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" style="opacity: 0.25;" />
            <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" class="image-demo" id="blur-demo"> 
        </div>  
    </div>
</div> 

We duplicate the image for the blur and apply some CSS to the blur to achieve the affect. I'll explain what is going on here for clarification. 

```
border-radius: 150px;
transform: scale(1.10);
top: 50px;
left: -5px; 
filter: blur(1.5rem);
```
Pretty straight forward here, border-radius to round the corners, scale up so the blur bleeds out to the edges, move it a bit downward and center it a bit and add the blur filter. 

``` 
opacity: 0;
transition: opacity 0.4s ease-out;
z-index: -1;
```
Opacity is 0 on idle and changes to 0.5 on hover. z-index is to always keep it behind. 

## Drop Shadow
```css 
#shadow-demo {
    filter: drop-shadow(0px 5px 5px rgba(0, 0, 0, 0.5));
}

#shadow-demo:hover  {
    filter: drop-shadow(0px 15px 5px rgba(0, 0, 0, 0.2));
}

```
Colour changed for better visibility. 

Pretty straight forward, values can be adjusted for better accuracy. 

>NOTE: Drop shadow is attached to the image THUS is affected by transform. Please keep this in mind when adjusting values. 

<div class="three-row" >
    <div class="container" style="justify-content:center; flex:">
        <strong>Drop Shadow</strong>
        Hover/Tap me!
        <div class="image-demo" id="shadow-demo-image">
            
            <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" />
        </div>  
    </div>
    <div class="container" style="justify-content:center; flex:">
        <strong>Drop Shadow (with transform)</strong>
        Hover/Tap me!
        <div class="image" id="shadow-demo-image">
            
            <img src="https://image.tmdb.org/t/p/original/aoV4UeZGy8nM6F59l7KRXPrsK4B.jpg" />
        </div>  
    </div>
</div> 

Well, that's that. 

Feel free to use!! 

<style>

    #h2 {
        position: sticky; 
    }
    #blur-demo {
        position: absolute; 
        border-radius: 150px;

        transform: scale(1.10);
        top: 50px;
        left: -5px; 
        filter: blur(1.5rem);


        
        opacity: 0;
        transition: opacity 0.4s ease-out;
        z-index: -1;
    }

    #blur-demo-image:hover #blur-demo {
        opacity: 0.5; 
    }

    #hover-demo:hover {
        transform: perspective(1500px) scale(1.03) rotate3d(1, 0, 0, 10deg);
    }

    #perspective-demo:hover {
        transform: perspective(1500px);
    }

    #scale-demo:hover {
        transform: scale(1.03);
    }

    #rotate3d-demo:hover {
        transform: rotate3d(1, 0, 0, 15deg);
    }

    #shadow-demo-image {
        filter: drop-shadow(0px 5px 5px rgba(255, 255, 255, 0.5));
        opacity: 1; 
        transition: all 0.6s cubic-bezier(0, 1, 0.4, 1);
    }

    #shadow-demo-image:hover  {
        filter: drop-shadow(0px 15px 5px rgba(255, 255, 255, 0.2));
        transition: all 0.6s cubic-bezier(0, 1, 0.4, 1);
    }
    
    .img-demo {
        max-height: 300px; 
    }

    .center {
        text-align: center; 
    }

    .image-demo {
        position: relative; 
    
        max-width: 250px;
        margin-bottom: 12px;

        transform-origin: 50% -10px;
        transition: transform 0.6s cubic-bezier(0, 1, 0.4, 1);
        
    }

    .shine-demo {
        position: absolute;
        width: 100%; 
        height: 100%;

        max-width: 250px;
        margin: auto;
        object-fit: contain;
        
        --stop1: 74%;
        --stop2: 77%;
        --opacity1: 0; 
        --opacity2: 0; 
        --opacity3: 0.05;

        background: linear-gradient(
            30deg,
            rgba(255, 255, 255, var(--opacity1)) 0%,
            rgba(255, 255, 255, var(--opacity2)) var(--stop1),
            rgba(255, 255, 255, var(--opacity3)) var(--stop2),
            rgba(255, 255, 255, 0.01) 100%
        );
        -webkit-mask-repeat: no-repeat;
        -webkit-mask-size: cover;
        z-index: 1; 
    }

    .normal-demo {
        max-width: 250px; 
        width: 100%; 
        height: auto;
        filter: drop-shadow(0px 5px 5px rgba(0, 0, 0, 0.5));
        transition: all 0.4s ease-out;
            /*
            --stop1: 74%;
            --stop2: 77%;
            --opacity3: 0.9;
            --opacity1: 1;
            --opacity2: 1;

            -webkit-mask: linear-gradient(
                30deg,
                rgba(0, 0, 0, var(--opacity1)) 0%,
                rgba(0, 0, 0, var(--opacity2)) var(--stop1),
                rgba(158, 158, 158, var(--opacity3)) var(--stop2),
                rgba(84, 84, 84, 1) 100%
            );
            -webkit-mask-repeat: no-repeat;
            -webkit-mask-size: cover;*/
    }


    .button-container {
        
        padding-top: 70px;
        
        display: flex; 
        flex-wrap: wrap;
        gap: 24px;
        align-items: flex-start;
        justify-content: center;
    }

    button {
        appearance: none;
        background-color: #FAFBFC;
        border: 1px solid rgba(27, 31, 35, 0.15);
        border-radius: 6px;
        box-sizing: border-box;
        color: #24292E;
        cursor: pointer;
        display: inline-block;
        font-weight: 500;
        line-height: 20px;
        list-style: none;
        padding: 6px 16px;
        transition: background-color 0.1s cubic-bezier(0.3, 0, 0.5, 1);
        user-select: none;
        -webkit-user-select: none;
        touch-action: manipulation;
        vertical-align: middle;
    }

    button:hover {
        background-color: #e2e2e2ff; 
    }

    .three-row {
        display: flex;
        flex-wrap: wrap;
        gap: 24px;
        align-items: flex-start;
        justify-content: center;
        padding-bottom: 30px; 
    }
    .container {
        display: flex;
        flex: 1 1 20%;
        flex-direction: column;
        align-items: center;
        min-width: 200px;
    }

    body {
        background-color: #242d3a;
    }

    .image {
        position: relative; 
    
        max-width: 250px;
        margin-bottom: 12px;

        transform-origin: 50% -10px;
        transition: transform 0.6s cubic-bezier(0, 1, 0.4, 1);
        
    }

    .blur, 
    .shine {
        position: absolute;
        width: 100%; 
        height: 100%;

        max-width: 250px;
        margin: auto;
        object-fit: contain;
        
    }
    .normal {
        max-width: 250px; 
        width: 100%; 
        height: auto;
        filter: drop-shadow(0px 5px 5px rgba(0, 0, 0, 0.5));
        transition: all 0.4s ease-out;
    }

    .normal.off {
        max-width: 250px; 
        width: 100%; 
        height: auto;
        filter: none;
        transition: all 0.4s ease-out;
    }

    .blur {
        
        border-radius: 150px;

        transform: scale(1.10);
        top: 50px;
        left: -5px; 
        filter: blur(1.5rem);

        
        opacity: 0;
        transition: opacity 0.4s ease-out;
        z-index: -1;
    }

    .shine {
        --stop1: 74%;
        --stop2: 77%;
        --opacity1: 0; 
        --opacity2: 0; 
        --opacity3: 0.05;

        background: linear-gradient(
            30deg,
            rgba(255, 255, 255, var(--opacity1)) 0%,
            rgba(255, 255, 255, var(--opacity2)) var(--stop1),
            rgba(255, 255, 255, var(--opacity3)) var(--stop2),
            rgba(255, 255, 255, 0.01) 100%
        );
        -webkit-mask-repeat: no-repeat;
        -webkit-mask-size: cover;
        z-index: 1; 
    }

    .image:hover  {
        transform: perspective(1500px) scale(1.03) rotate3d(1, 0, 0, 10deg);
    }
    
    .image.no-hover:hover {
        transform: none;
    }

    .image:hover .normal {
        filter: drop-shadow(0px 15px 5px rgba(0, 0, 0, 0.2));
    }

    .image:hover .normal.off {
        filter: none;
    }

    .image:hover .blur {
        opacity: 0.5;
    }


    

</style>

<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script>
let isShineToggled = false; 
let isDropShadowToggled = false; 
let isBackgroundBlurToggled = false; 
let isHoverToggled = false; 
function toggleShine() {
    isShineToggled = !isShineToggled;
    //console.log(isShineToggled);
    if (isShineToggled) {
        document.getElementById("shine-toggle").style.backgroundColor = "#ffff00";
        document.querySelectorAll(".image").forEach(image => {
            const shine = image.closest('.image').querySelector('.shine');
            gsap.to(shine, {
                    "--stop1": "98%",
                    "--stop2": "99%",
                    "--opacity1": 0,
                    "--opacity2": 0,
                    "--opacity3": 0,
                    duration: 1,
                    ease: "expo.out"
                });
            });
    } else {
        document.getElementById("shine-toggle").style.background = null;
        document.querySelectorAll(".image").forEach(image => {
            const shine = image.closest('.image').querySelector('.shine');
            gsap.to(shine, {
                "--stop1": "74%",
                "--stop2": "77%",
                "--opacity1": 0,
                "--opacity2": 0,
                "--opacity3": 0.05,
                duration: 1,
                ease: "expo.out"
            });
        });
    }
    return;
}
function toggleDropShadow() {
    isDropShadowToggled = !isDropShadowToggled;
    const normalElements = document.querySelectorAll('.normal');
    //console.log(isDropShadowToggled);
    normalElements.forEach(img => {
        img.classList.toggle('off', isDropShadowToggled);
    });
    if (isDropShadowToggled) {
        document.getElementById("drop-shadow-toggle").style.backgroundColor = "#ffff00";
    } else {
        document.getElementById("drop-shadow-toggle").style.background = null;
    }
    return;
}
function toggleBackgroundBlur() {
    isBackgroundBlurToggled = !isBackgroundBlurToggled;
    const backgroundBlur = document.querySelectorAll('.blur');
    //console.log(isBackgroundBlurToggled);
    if (isBackgroundBlurToggled) {
        backgroundBlur.forEach(el => {
            el.style.display = 'none'; 
        });
        document.getElementById("blur-shadow-toggle").style.backgroundColor = "#ffff00";
    } else {
        backgroundBlur.forEach(el => {
            el.style.display = 'block'; 
        });
        document.getElementById("blur-shadow-toggle").style.background = null;
    }
    return;
}
function toggleHover() {
    const images = document.querySelectorAll('.image');
    isHoverToggled = !isHoverToggled;
    images.forEach(img => {
        img.classList.toggle('no-hover', isHoverToggled);
    });
    //console.log(isHoverToggled);
    if (isHoverToggled) {
        document.getElementById("hover-toggle").style.backgroundColor = "#ffff00";
    } else {
        document.getElementById("hover-toggle").style.background = null;
    }
    return;
}
document.querySelectorAll(".image").forEach(image => {
    const shine = image.closest('.image').querySelector('.shine');
    image.addEventListener("mouseenter", function () {
        if (!isShineToggled) 
        {
            gsap.to(shine, {
                "--stop1": "53%",
                "--stop2": "55%",
                "--opacity1": 0.02,
                "--opacity2": 0.02,
                "--opacity3": 0.2,
                duration: 1,
                ease: "expo.out"
            });
        }
    });
    image.addEventListener("mouseleave", function () {
        if (!isShineToggled) 
        {
            gsap.to(shine, {
                "--stop1": "74%",
                "--stop2": "77%",
                "--opacity1": 0,
                "--opacity2": 0,
                "--opacity3": 0.05,
                duration: 1,
                ease: "expo.out"
            });
        }
    });
});
document.querySelectorAll(".image-demo").forEach(image => {
    const shine2 = image.closest('.image-demo').querySelector('.shine-demo');
    image.addEventListener("mouseenter", function () {
        gsap.to(shine2, {
            "--stop1": "53%",
            "--stop2": "55%",
            "--opacity1": 0.02,
            "--opacity2": 0.02,
            "--opacity3": 0.2,
            duration: 1,
            ease: "expo.out"
        }); 
    });
    image.addEventListener("mouseleave", function () {
        gsap.to(shine2, {
            "--stop1": "74%",
            "--stop2": "77%",
            "--opacity1": 0,
            "--opacity2": 0,
            "--opacity3": 0.05,
            duration: 1,
            ease: "expo.out"
        });
    });
});
</script>
