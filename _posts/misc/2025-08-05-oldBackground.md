---
layout: thoughts-post
title: omega4_oldbackground
category: Misc
date:   2025-08-05 12:21:20 +1000
permalink: /misc/oldbackground.html
---

<style>
    :root {
        --length: 20s;
    }

    @keyframes move_background {
        0% {
            top: -500px;
            left: 0px;
        }

        100% {
            top: 0px;
            left: -500px;
        }
    }

    #background {
        position: absolute;
        top: 0px;
        left: 0px;
        right: 0px;
        bottom: 0px;
        background-image: url(../assets/omega_4/wordLogo.png);
        background-size: 500px;
        animation-name: move_background;
        animation-duration: var(--length);
        animation-iteration-count: infinite;
        animation-timing-function: linear;
        animation-delay: -30s;
        z-index: -2;
        opacity: 50%;
    }

    #background2 {
        position: absolute;
        top: 0px;
        left: 0px;
        right: 0px;
        bottom: 0px;
        background-image: url(../assets/omega_4/logo.png);
        background-size: 500px;
        animation-name: move_background;
        animation-duration: var(--length);
        animation-iteration-count: infinite;
        animation-timing-function: linear;
        z-index: -2;
        opacity: 50%;
    }

    #background3 {
        position: absolute;
        top: -109px;
        left: -167px;
        right: 0px;
        bottom: 0px;
        transform: rotate3d(1, 1, 0, 30deg);
        width: 2358px;
        height: 1440px;
        z-index: -1;
    }

    #box {
        background: #7fb5db;
        background: radial-gradient(circle, rgba(127, 181, 219, 1) 0%, rgba(35, 57, 75, 1) 100%);
        outline-style: auto;
        outline-color: black;
        position: absolute;
        width: 1920px;
        height: 1080px;
        left: 0px;
        top: 0px;
        z-index: -1;
    }
</style>

<div id="box"></div>
<div id="background3">
    <div id="background2"></div>
    <div id="background"></div>
</div>
<!-- <div id="background2"></div>
-->



