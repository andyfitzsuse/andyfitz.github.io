---
title: The smallest SVG possible
description: This is a post on My Blog about agile frameworks.
date: 2021-04-11
tags:
  - svg
  - minimal
  - tips
layout: layouts/post.njk
---
A while back, I created this interactive demo of the Outfit logo to teach some of the fundamentals of plotting and styling SVG path coordinates.  

<p class="codepen" data-height="450" data-theme-id="1777" data-default-tab="result" data-user="andyfitz" data-slug-hash="gOwzMwV" style="height:455px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; margin: 1em 0; padding: 1em;" data-pen-title="Outfit Logo Inspector">
  <span>See the Pen <a href="https://codepen.io/andyfitz/pen/gOwzMwV">
  Outfit Logo Inspector</a> by Andy Fitzsimon (<a href="https://codepen.io/andyfitz">@andyfitz</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
It got even smaller as a one-liner: 

``` xml
<svg viewBox="0 0 19 8.5" stroke="#e40046" fill="none"><circle cx="2.36" cy="6.12" r="1.68"/><path d="M5.35 4v2.5A1.02 1 0 008 6.5v-2h10.68M10.2 8.2v-6m2.3 6V2a1.3 1.2 10 012-1m.3 7.2V4.5m2.3 3.7v-6"/><path d="M14.8 2.8v0" stroke-linecap="round"/></svg>
```



<a target="_blank" href="https://rowanhogan.com/">Rowan Hogan</a> originally designed the logo without trying to contort the shapes specifically for SVG format optimisation – try not to let the medium become the message as they say. 

The design evolved with minor updates and when it came time to make this demo it had things stacked against it:
  * optical overshoot 
  * non-perfect curves 
  * non 1:1 grid rhythm (1:1.3 spacing of stems) 


# Rules to SVG by 

This list is by no means comperehensive but it does serve as a rough guide
### viewBox under 10 or 100 - from zero
``` xml
<svg viewBox="0 0 10 10" ... >   
<!-- 
 or
 -->   
<svg viewBox="0 0 100 100" ... >   

```
Depending on the complexity of your image.
the point here is we dont want every coordinate to be in the thousands, we also want to avoid unnessecary decimals, 
 

## Stroke if you can

Every shape you can pull off as a stroke that would otherwise be a filled path saves you 2-3x bloat in coordinate 


## know when to capital or lowercase coordinates

Don't know the difference?
Uppercase Letters like M C L A H V Q T etc all start an operation relative to the viewBox
Lowercase letters (same as above) m c l a h v q t etc start from the last coordinate you did

Relative or absolute positioned coordinates make a huge difference



## chose your operator wisely

Using a horizontal (H) or vertical (V) operator is great because you only need one coodinate it saves you tryping both X and Y,  you only need one coordinate so that halves what would otherwise be redundant axis data with the line-to (L) operator.

Arc paths, quadratics and cubic splines all have their own benefits and problems 

