---
title: Must have SVG tools 
description: We all could use a little help making SVG the leanest and meanest 
date: 2021-04-12
tags:
  - svg
  - minimal
  - tools
layout: layouts/post.njk
---


This article contains a list of current SVG tools I reach for today depending on need. 
As the rifleman's creed goes: *“there are many like it but this one is mine”*.  I hope my list is useful to you. 




It's worth noting that my love affair with SVG started relatively early. Before Adobe aquired Macromedia, it had weight with Sun Microsystems into PGML - competing against giants like Microsoft and Autodesk. [This document covers the state of play](https://www.w3.org/Graphics/SVG/WG/wiki/Secret_Origin_of_SVG) 

As a creative, I really loved Flash, but when W3C released their draft recomendation for SVG 1: I figured it would win the web within months (it took years). 

Fortunately for the interim, SVG was more useful than just for the web. 
In 2003, I toyed with SVG a for university. 
In 2005, I finally used SVG commercially thanks to Red Hat and UTF8. 

My personal heroes who moved SVG forward directly or indirectly: [Cam Mcormack](https://mcc.id.au/), [Raph Levien](https://raphlinus.github.io/), [Chris Lilley](https://svgees.us/), Carl worth, Liam Quinn, Doug Schepers, Nathan Hurst, Peter Moulder, Tavmjong Bah, Bryce Harrington, Aaron Spike, Jon Cruz, Bulia Byak, Dom Lachowicz, Dodji Seketeli, [Owen Taylor](https://blog.fishsoup.net/) and so many more. 

What's promising is that many of the tools listed here are not by the authors above. A new generation is pushing SVG ever forward.


Some are online tools, some are scripts, some are desktop apps, some are libraries. All incredibly powerful in the right situation.  So here goes, get your bookmark tool of choice fired up:

## [SVGOMG](https://jakearchibald.github.io/svgomg/)

The webinterface is amazing, I also use this directly in apps and on the commandline 

```
npm install -g svgo
```

If you use [webpack](https://webpack.js.org/), [snowpack](https://www.snowpack.dev/), [vite-svg-plugin](https://www.npmjs.com/package/vite-plugin-svg) etc you likely use it too.
The plugins are fascinating.

## [SVG Path Editor](https://yqnn.github.io/svg-path-editor/)

I use this now more than inkscape for simple illustrations, and I really wish the preview would let me add CSS. But still, this thing is pure GOLD!

When finishing an illustration I often return to this tool and go path by path to reduce unnessecary coordinates and operators


## [SVG Crop](https://svgcrop.com/)

Not as handy as the method we use in create.rip (any clippaths will affect the viewBox) but handy all the same.

## [SVG URL Encoder](https://yoksel.github.io/url-encoder/)

inline svg into css - hey it's nasty but I still find myself throwing SVG into pseudo elements all the time.

This tool from Yoksel makes it super easy!


## [SVG Fitler Builder](https://svgfilters.com/)

Creating complex SVG Filters is incredibly hard, Thankfully we have this brilliant tool

There's an alternative [SVG Filter Constructor](https://yoksel.github.io/svg-filters/#/) by [Yoksel](https://yoksel.github.io) with a less intimidating interface that's worth a look.




## [SVG Gradient Map Filter Builder](https://yoksel.github.io/svg-gradient-map/#/)

## [Relative Clip-path ](https://yoksel.github.io/relative-clip-path/)

For turning SVG paths into CSS-friendly `clip-path` coordinates.

## [Wave Maker](https://yoksel.github.io/wave-maker/)
ok this i just fun

## [Inkscape](https://inkscape.org/)

Gill > spodipodi > inkscae I've loved this journey and especially love where it is now.
Run it on your linux machine, your mac .. its brilliant for creative exploration, and especially illustration

## [Penpot](https://penpot.app/)
Early days to call this a Figma killer - But I do find it does most of what I want out for Figma (for free and freedom)

## [RawGraphs ](https://app.rawgraphs.io/)

Brilliant way to produce graphs without having to render client side, create the layout in rawgraphs then style with your own CSS

## [librSVG](https://gitlab.gnome.org/GNOME/librsvg)
(used in ImageMagick and heaps more)
This is a blazingly fast library to work with SVG files

If you are a performance-driven developer, [RSVG convert](https://gitlab.gnome.org/GNOME/librsvg/-/blob/master/src/bin/rsvg-convert.rs) in particular will blow your mind

Also you should follow [Federico Mena-Quintero](https://people.gnome.org/~federico/blog/tag/librsvg.html) Who is dragging RSVG into the future


## [Imagetracer JS](https://github.com/jankovicsandras/imagetracerjs)

There are many bitmap to vector tracers like potrace, autotrace etc but imaegtracer is the most promising for web developers.

Handy to have on the CLI too:
```
imagetracerjs/nodecli>node nodecli ../in.png outfilename out.svg scale 10
```

## [2geom](https://gitlab.com/inkscape/lib2geom)

Fun fact, Inkscape uses 2geom under the hood.

If you're building something that needs to perform 2d computational geometry - you'll end up grateful for Nathan Hurst and all other contribnutors

## [SVG JS](https://svgjs.com/)

I've not used this but it does offer some compelling shortcuts 


## [Create.Rip](https://create.rip)

Easily extract essential assets from any design format (PDF PSD TIFF etc) to the right web ready formats.

I'd be remiss for not including this one.

create.rip is a web service we built at Outfit for ourselves with the help of embersea.

We decided to host and share it with the world -

Dedicated in memory to Ihor Novikov author of the Uniconvertor and Sk1 who passed March 15th, 2021 hospitalised by a stroke and subsequently COVID-19