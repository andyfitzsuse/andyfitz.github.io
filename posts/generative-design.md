---
title: Generative art with vanilla JS
description: Random computational artwork doesn't have to be hard or heavy
date: 2021-04-19
tags:
  - brand automation
  - generative design
  - creative coding
  - svg
  - minimal
  - javascript
layout: layouts/post.njk
---
Why design a single piece when you can design a visual system with countless unique permutations?

In this tutorial I'm going to show you how to make dynamic artwork using very simple vanilla javascript and SVG.
<style>

#nstage{cursor:pointer;}
#nstage circle {stroke: DeepPink;fill: none;stroke-width:2;}
#nstage circle:nth-child(2n) {stroke:#6ac; animation-delay:-1s; }
#nstage circle:nth-child(3n){stroke:#789;  opacity:.5;animation-delay:-2s;}
#nstage circle:nth-child(4n){stroke:#567;  opacity:.5;animation-delay:-3s;}
#nstage circle:nth-child(5n){stroke:#9ab; animation-delay:-.5s;}
#nstage circle{animation: showhide 4s ease infinite}
@keyframes showhide{50%{opacity:0}}
</style>
<svg id="nstage"  width="100%"  height="27em" viewBox="0 0 100 100" preserveAspectRatio="xMidYMid slice" style="opacity:.8;position:absolute; top:-2em; left:0; right:0; z-index:-1;">
<circle cx="10" cy="10" r="5" />
<circle cx="20" cy="90" r="4" />
<circle cx="30" cy="40" r="3" />
<circle cx="40" cy="30" r="2" />
<circle cx="50" cy="70" r="1" />
<circle cx="60" cy="60" r="6" />
<circle cx="70" cy="30" r="7" />
<circle cx="80" cy="80" r="8" />
<circle cx="90" cy="10" r="9" />
</svg>
<script>
function eremoveAll() {
document.getElementById("nstage").innerHTML = "";
}
eremoveAll();
let esvg = document.getElementById("nstage");
function edrawCircles() {
for (i = 0; i < 15; i++) {
circle = document.createElementNS("http://www.w3.org/2000/svg", "circle");
circle.setAttribute("pathLength", "1");
circle.setAttribute("stroke-width", "1");
circle.setAttribute("r", Math.floor(Math.random() * 7) * 2 + 2);
circle.setAttribute("cx", Math.floor(Math.random() * 4) * 20 + 20);
circle.setAttribute("cy", Math.floor(Math.random() * 4) * 20 + 20);
esvg.appendChild(circle);
}
}
document.addEventListener("click", function () {
eremoveAll();
edrawCircles();
});
edrawCircles();
var deGenTimer = window.setInterval(function () {
eremoveAll();
edrawCircles();
}, 1000);
</script>

For generative art there are some great frameworks like [P5.js](https://p5js.org/),[Three.js](https://threejs.org/), all the way up to the mind bending [Generative Adversarial Networks](https://en.wikipedia.org/wiki/Generative_adversarial_network) like [styleGAN](https://github.com/NVlabs/stylegan) and so many more.  This space is exploding with digital artists and art directors chasing never seen before aesthetics that blur the lines between human and machine made creations.

This isn't new either. For decades many brands with expansive portfolios have gone down the dynamic brand route with their visual architecture. We're lucky to have a few of them as customers at Outfit.io . Traditionally however, permutations were created by central tooling. Often created on the desktop of an art director in a brand team. A render produced once per-need - manually looked over, then distributed as static assets. Nowadays, we can keep the systems alive by leveraging our web native technology and respond to new input 

One of the many benefits in using web formats for design, is that it's very easy to produce artwork that is unique every time. An awesome perk for end users of your visual system.
Plus, unlike choosing a specific tool, you have all the aesthetic potential of the web. 

This can make for a far more engaging and dynamic aesthetic on large builds like events or media.

## Setting the stage 

First, we're going to create something without any javascript at all. 
This helps us to creatively set the stage by mocking up at least some of the look and feel you'd like to create.  

The benefits of this approach means you discover your answers to the most beautiful of questions:

>  What must **stay the same** so that<br>everything else can change?"

The answer is what frees us up to explore new horizons:

>  Observe what is constant,<br>discover what can **constantly change**

If we get a sense of what we like, we'll also get a sense of what variables we can bend or break.

In this case we're going to use `SVG`,  but you could just as easily use plain ol HTML and `div`'s.
I'm not going to use `canvas` or even Filters because at the end I want a nice vector PDF poster and not a heavy rasterized asset.

``` xml
<body>
 <svg
  id="stage" 
  viewBox="0 0 100 100" 
  preserveAspectRatio="xMidYMid slice">
<!-- cool stuff will go here -->
 </svg>
</body>
```
That `preserveAspectRatio="xMidYMid slice"` will center-crop our artwork if we display it at non square. Think of it as `background-size: cover; background-position: 50% 50%;` but for SVG contents within a `viewBox`

We should probably add some CSS to make sure we're full page too. 

``` css
body{margin:0; overflow:hidden;}
body > svg{width:100vw;height:100vh}
```

Now, lets think about what we could create.

A few random-ishly placed circles might do the trick.

<svg viewBox="0 0 100 100" fill="currentcolor"  width="100%" height="15em">
<circle cx="20" cy="80" r="4" />
<circle cx="80" cy="40" r="4" />
<circle cx="40" cy="40" r="2" />
<circle cx="40" cy="80" r="2" />
<circle cx="60" cy="60" r="6" />
<circle cx="60" cy="20" r="6" />
<circle cx="20" cy="60" r="8" />
<circle cx="80" cy="20" r="8" />
</svg>

Not really that random... I just placed the X and Y axis in increments of 20 and the radius in sizes between 2-8.

``` xml
<circle cx="20" cy="80" r="4" />
<circle cx="80" cy="40" r="4" />
<circle cx="40" cy="40" r="2" />
<circle cx="40" cy="80" r="2" />
<circle cx="60" cy="60" r="6" />
<circle cx="60" cy="20" r="6" />
<circle cx="20" cy="60" r="8" />
<circle cx="80" cy="20" r="8" />
```

## What must stay the same ?

We're going to apply some CSS and attributes to lock in the look we want.  In this case, pink circles with double thick lines and no fill.

``` css
circle {
  stroke: DeepPink;
  fill: none;   
  stroke-width:2;
}
```

<svg viewBox="0 0 100 100" fill="currentcolor" width="100%"  height="15em"> <g style="stroke: DeepPink;fill: none;stroke-width:2;"><circle cx="20" cy="80" r="4" /><circle cx="80" cy="40" r="4" /><circle cx="40" cy="40" r="2" /><circle cx="40" cy="80" r="2" /><circle cx="60" cy="60" r="6" /><circle cx="60" cy="20" r="6" /><circle cx="20" cy="60" r="8" /><circle cx="80" cy="20" r="8" /></g></svg>


Okay that was fun, but we need more of these, and I'd go mad placing circles manually. Time to let the computers take over.

# Enter Vanilla Javascript

For this demo, we be messing with the three attributes of each SVG `circle` element.
* the circle X position
* the circle Y position
* the radius of the circle
 
I also want the option of changing how many circles we play with. 

So to accommodate this, we're going to say bye-bye to the manually crafted circles and hello to Javascript generated ones.

I'm going to leave them in the DOM just incase someone is using `noscript`. But there's no need to do this if we were generating this server-side. 
I also want a `removeAll` function for easily testing new variations.


``` js
// clearing the stage
function removeAll() {document.getElementById("stage").innerHTML = "";}
removeAll();
```

Now we're going to create entirely new circles on the stage with a function called `drawCircles`

``` js
// calling my state svg
let svg = document.getElementById("stage");

function drawCircles() {
  // how many circles to draw 
  // I started with 8 but now I think 15 is the magic number
  for (i = 0; i < 15; i++) {
    
    // because circle isnt a html element I need to specify the SVG namespace 
    circle = document.createElementNS("http://www.w3.org/2000/svg", "circle");
   
    // maximum 14, minimum 2 and in increments of 2 
    circle.setAttribute("r", Math.floor(Math.random() * 7) * 2 + 2) ;
    
    // minimum 20 maximum 80, incremements of 20 
    // (so either 20 , 40, 60, 80 )
    circle.setAttribute("cx", Math.floor(Math.random() * 4) * 20 + 20);
    circle.setAttribute("cy", Math.floor(Math.random() * 4) * 20 + 20);
    
    // add these elements to my stage
    svg.appendChild(circle);
  }
}
drawCircles();
```

Mess with the values, it's super fun to see your design going off-plan.  Watching your rules bend and break can give you new ideas. 

## Testing and regenerating

We're going to make testing easy with a timer that changes permutation every 4 seconds.

``` js
var reGenTimer = window.setInterval(function () {
  removeAll();
  drawCircles();
}, 4000);
```

Actually, I'm super impatient so we're also going to add a click event listener so that I can just click for a new generation. 
``` js
document.addEventListener("click", function () {
  removeAll();
  drawCircles();
});
```

## CSS for some more flair
What's awesome about generating random elements is that you already have them in a random sequence.  So you can add very sequential CSS rules using the `:nth` selectors and still get away with looking random - no need to put this stuff in your JS.

Below, I just make every 2nd, 3rd, 4th and 5th circle a different stroke color.

``` css
circle:nth-child(2n){stroke:#6ac}
circle:nth-child(3n){stroke:#678}
circle:nth-child(4n){stroke:#345}
circle:nth-child(5n){stroke:#9ab}
```

Click below to refresh faster

<style>
#stage{cursor:pointer;}
#stage circle {stroke: DeepPink;fill: none;stroke-width:2;}
#stage circle:nth-child(2n) {stroke:#6ac}
#stage circle:nth-child(3n){stroke:#678}
#stage circle:nth-child(4n){stroke:#345}
#stage circle:nth-child(5n){stroke:#9ab}
</style>
<svg id="stage"  width="100%"  height="20em" viewBox="0 0 100 100" >
<circle cx="10" cy="10" r="5" />
<circle cx="20" cy="90" r="4" />
<circle cx="30" cy="40" r="3" />
<circle cx="40" cy="30" r="2" />
<circle cx="50" cy="70" r="1" />
<circle cx="60" cy="60" r="6" />
<circle cx="70" cy="30" r="7" />
<circle cx="80" cy="80" r="8" />
<circle cx="90" cy="10" r="9" />
</svg>
<script>
function removeAll() {
document.getElementById("stage").innerHTML = "";
}
removeAll();
let svg = document.getElementById("stage");
function drawCircles() {
for (i = 0; i < 15; i++) {
circle = document.createElementNS("http://www.w3.org/2000/svg", "circle");
circle.setAttribute("pathLength", "1");
circle.setAttribute("stroke-width", "1");
circle.setAttribute("r", Math.floor(Math.random() * 7) * 2 + 2);
circle.setAttribute("cx", Math.floor(Math.random() * 4) * 20 + 20);
circle.setAttribute("cy", Math.floor(Math.random() * 4) * 20 + 20);
svg.appendChild(circle);
}
}
document.addEventListener("click", function () {
removeAll();
drawCircles();
});
drawCircles();
var reGenTimer = window.setInterval(function () {
removeAll();
drawCircles();
}, 3000);
</script>

<a href="https://codepen.io/andyfitz/pen/KKaxgvw" rel="noreferer" target="_blank">Play with it on Codepen</a>

And there you have it,  we've made generative artwork. 
Random but within constraints. Every iteration looks different but also like they belong together. The rules you set – and how wild you go, is entirely up to your vision. 

The whole dance of this technique is to ensure every permutation is a *hit*  and looks like something you'd be happy with. That's easier said than done when you can't push pixels, but trust me it's super rewarding knowing you have created a living system rather than a static piece.

## What about that poster?
Remember I said we were going to make this a nice vector PDF poster?   
Thanks to Make.cm we can, and [every single download](https://api.make.cm/make/t/ad146027-af14-4644-92e8-b13f1209bfda/k/17915c24-7159-4b2a-9552-a50f296fa3d6.c0e9241f95e4c5bbbf17b447538274b7/sync?size=A4&format=pdf&data[empty]=nodata) will be generated uniquely.

Checkout the GET request below for an A3 version
<a style="padding:1em; margin: 1em 0;display:block; width: 100%;overflow:auto; " class="button" target="_new" href="https://api.make.cm/make/t/ad146027-af14-4644-92e8-b13f1209bfda/k/17915c24-7159-4b2a-9552-a50f296fa3d6.c0e9241f95e4c5bbbf17b447538274b7/sync?size=A3&format=pdf&data[blank]=nodata"> https://api.make.cm/make/t/ad146027-af14-4644-92e8-b13f1209bfda/k/17915c24-7159-4b2a-9552-a50f296fa3d6.c0e9241f95e4c5bbbf17b447538274b7/sync?size=A3&format=pdf&data[blank]=nodata </a>
