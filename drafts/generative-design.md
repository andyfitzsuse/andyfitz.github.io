---
title: Easy generative design with vanilla JS
description: Random computational artwork doesn't have to be hard or heavy
date: 2021-04-12
tags:
  - brand-automation
  - generative design
layout: layouts/post.njk


----

Why design a single piece when you can design a visual system with countless unique permutations?

In this tutorial I'm going to show you how to make artwork using very simple vanilla javascript and SVG.

For generative art there are great frameworks like P5.js, Three.js, all the way up to the mind bending styleGAN and so many more.  
But I felt they were all a bit much when it comes to the basiscs. Hopefully this article sets you up for a long and happy relationship with this mode of creative production.


## preamble


Plenty of brands have gone the dynamic brand route and we're lucky to have a few of them as customers of Outfit.io leveraging our web native templates. 

One of the many benefits in using web technology based templates, is that it's very easy to produce artwork that is unique every time. An awesome perk for end users of your visual system.
This can make for a far more engaging and dynamic aesthetic on large builds like events or media.


# Setting the stage - getting started

First we're going to create something without any javascript at all. 
This helps us to set the stage by mocking up the look and feel you'd like to create.  

The benefits of this approach means you discover your answers to the most beautiful questions:

>  What must stay the same so that everythign else can change"

and also frees us up to explore new horizons

>  What can change now that we know what can stay the same


In this case we're going to use SVG,  but you could just as easily use HTML

``` 
<body>
  <svg id="stage" viewBox="0 0 100 100">

  </svg>
</body?
```

