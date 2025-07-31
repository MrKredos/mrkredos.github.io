---
layout: post
title: movie screensaver :) 
date: 2024-08-26
category: Mini Projects
permalink: /projects/mini-projects/screensaver
---

<script type="application/processing"> 
int x = width/2; 
int y = height/2;
boolean xMovingRight = true; 
int speedMultiplier = 3;
int ellipseRadius = 50;
boolean yMovingDown = true; 

void setup() {
  size (700, 400); 
  
}

void draw() {
  background (0);
  fill (255);
 
  ellipse(x, y, ellipseRadius*2, ellipseRadius*2); 
  if (x < ellipseRadius) {
    xMovingRight = true; 
  } 
  if (x > width-ellipseRadius) {
    xMovingRight = false;
  }
  if (y < ellipseRadius) {
    yMovingDown = true; 
  }
  if (y > height-ellipseRadius) {
    yMovingDown = false; 
  }

  if (xMovingRight == true) {
    x = x+1*speedMultiplier; 
  } else {
    x = x-1*speedMultiplier; 
  }
  
  if (yMovingDown == true) {
    y = y+1*speedMultiplier;
  } else {
    y = y-1*speedMultiplier;
  }
  
} 
</script>
  <canvas id="sketch"></canvas>
  <p id="label">Movie Screensaver</p>

Created using processing.js
