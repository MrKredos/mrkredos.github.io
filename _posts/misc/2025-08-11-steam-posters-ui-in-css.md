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
I want to have a page showing of my fav movies and needed like a lil bit of flourish for the posters. I decided I wanted to re-create the Steam Library Posters UI, because it looks like and it would be a fun little challenge to replicate. It took me maybe a day of hard work but I'm proud that I'm finally done with this.

WIP Adding how it works later. 
### Parts 

## Shine

## Hover 

## Blur/Background 

## Drop Shadow







<style>
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

    .blur {
        
        --opacityblur: 0;
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
        transform: none !important;
    }

    .image:hover .normal {
        filter: drop-shadow(0px 15px 5px rgba(0, 0, 0, 0.2));
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
    const images = document.querySelectorAll('.image');
    const normalElements = document.querySelectorAll('.normal');
    images.forEach(img => {
        img.classList.toggle('no-shadow', isDropShadowToggled);
    });
    //console.log(isDropShadowToggled);
    if (isDropShadowToggled) {
        normalElements.forEach(el => {
            el.style.filter = 'none';
        });
        document.getElementById("drop-shadow-toggle").style.backgroundColor = "#ffff00";
    } else {
        normalElements.forEach(el => {
            el.style.filter = "drop-shadow(0px 15px 5px rgba(0, 0, 0, 0.2))";
        });
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
</script>
