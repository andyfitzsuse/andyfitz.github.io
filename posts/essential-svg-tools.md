---
title: Essential SVG tools
description: We all could use a little help making SVG the leanest and meanest 
date: 2021-04-13
tags:
  - svg
  - minimal
  - tools
layout: layouts/post.njk
---


This article contains all the SVG-related resources I reach for depending on need. 
As the rifleman's creed goes: *“there are many like it but this one is mine”*.  
When your need involves SVG something here will help.


I have write up below but if you're in a hurry: 
[SVGOMG](https://jakearchibald.github.io/svgomg/) / [SVGO](https://github.com/svg/svgo)
[SVG Path Editor](https://yqnn.github.io/svg-path-editor/)
[SVG Crop](https://svgcrop.com/)
[SVG URL Encoder](https://yoksel.github.io/url-encoder/)
[SVG Fitler Builder](https://svgfilters.com/)
[SVG Gradient Map Builder](https://yoksel.github.io/svg-gradient-map/#/)
[CSS Relative Clip-path convertor](https://yoksel.github.io/relative-clip-path/)
[Imagetracer JS](https://github.com/jankovicsandras/imagetracerjs)
[Inkscape](https://inkscape.org/)  
[Penpot](https://penpot.app/) 
[RawGraphs ](https://app.rawgraphs.io/)
[2geom](https://gitlab.com/inkscape/lib2geom)  
[LibRsvg](https://gitlab.gnome.org/GNOME/librsvg)
toys: [Blobs](https://www.blobmaker.app/) [Noise](https://codepen.io/georgedoescode/full/dyNVNjG) [Waves](https://yoksel.github.io/wave-maker/)

#### Preamble

My love affair with SVG started before Macromedia was aquired. 
Adobe was <a href="https://www.w3.org/TR/1998/NOTE-PGML" target="_blank">into PGML</a> - competing against giants like <a href="https://www.w3.org/Graphics/SVG/WG/wiki/Secret_Origin_of_SVG">Microsoft and Autodesk</a>.


When W3C released the SVG draft: I figured it would win the web within months and started to chase it (it took years). 
Fortunately SVG was more useful than just internet use. 
In 2003, I toyed with SVG a for much of university. 
By 2005, I finally used SVG commercially thanks to Red Hat and UTF-8. 

My personal heroes who moved SVG forward directly or indirectly: [Cam Mcormack](https://mcc.id.au/), [Raph Levien](https://raphlinus.github.io/), [Chris Lilley](https://svgees.us/), Carl Worth, Liam Quinn, Doug Schepers, Nathan Hurst, Peter Moulder, Tavmjong Bah, Bryce Harrington, Aaron Spike, Jon Cruz, Bulia Byak, Dom Lachowicz, Dodji Seketeli, [Owen Taylor](https://blog.fishsoup.net/) and so many more. 

What's promising is that many of the tools listed here are not by the authors above. A new generation is pushing SVG ever forward.


Some are online tools, some are scripts, some are desktop apps, some are libraries. All incredibly powerful in the right situation.  So here goes, get your bookmark tool of choice fired up:

## [SVGOMG](https://jakearchibald.github.io/svgomg/)

The webinterface is amazing, I also use this directly in apps and on the commandline 

```
npm install -g svgo
```

If you use [webpack](https://webpack.js.org/), [snowpack](https://www.snowpack.dev/), [vite-svg-plugin](https://www.npmjs.com/package/vite-plugin-svg) etc you likely use it too.
The plugins are fascinating and have bailed me out many times.

## [SVG Path Editor](https://yqnn.github.io/svg-path-editor/)

I use this now more than even [Inkscape](http://www.inkscape.org/) for simple illustrations, and I really wish the preview would let me add my CSS. But still, this thing is pure GOLD!
When finishing an illustration I often return to this tool and go path by path to reduce unnessecary coordinates and operators. Stealing a few decimals here and there, replacing cubic bezier path operators with more optimal ones like quadratics or arcs.   SVG path editor will dramatically improve your understanding of the SVG path system


## [SVG Crop](https://svgcrop.com/)

Remove the extra margin from around your SVG content so the file is easy to work wit.
SVGcrop.com resizes the SVG artboard by changing the ```viewBox="..``` attribute
It's not bulletproof (any shapes used as clippaths will affect the viewBox) but handy all the same.

## [SVG URL Encoder](https://yoksel.github.io/url-encoder/)

Inline SVG into CSS - hey it's a gnarly technique but I still find myself throwing SVG into pseudo elements all the time. Think of the saved HTTP request! 

This tool from Yoksel makes it super easy!

## [Relative Clip-path ](https://yoksel.github.io/relative-clip-path/)

For turning SVG paths into CSS-friendly `clip-path` coordinates. Super handy.


## [SVG Fitler Builder](https://svgfilters.com/)

Creating complex SVG Filters is incredibly hard, Thankfully we have this brilliant tool

There's an alternative [SVG Filter Constructor](https://yoksel.github.io/svg-filters/#/) by [Yoksel](https://yoksel.github.io) with a less intimidating interface that's worth a look.



## [SVG Gradient Map Builder](https://yoksel.github.io/svg-gradient-map/#/)

Who doesn't love Duotone effects?  SVG Gradient Map filters make them achievable native on the web. 
There's just one annoying catch.  when you are coding these you need to convert your R G and B into separate channels and divide by 255 then place them your R G and B numbers for different colours next to eachother - it feels kind of unnatural.
This tool makes creating a custom filter easy.

If you want to automate this, I also [wrote a CodePen](https://codepen.io/andyfitz/pen/KKagbqe) that converts any array into swatches and a duotone effect.


## [Inkscape](https://inkscape.org/)

Isn't the evolution of open source desktop applications awesome? 
Gill > Sodipodi > Inkscape 
I've loved this journey and especially love where it is now.
Run it on your linux machine, your mac .. its brilliant for creative exploration, and especially illustration.
I've used Inkscape since it's inception. I could go on and on but let me just say it's the best tool for illustration of complext paths and leave the rest up to your imagination.

## [Penpot](https://penpot.app/)
Early days to call this a Figma killer - But I do find it does most of what I want out for Figma (for free and freedom)

## [RawGraphs ](https://app.rawgraphs.io/)

Brilliant way to produce graphs without having to render client side, create the layout in rawgraphs then style with your own CSS

## [librSVG](https://gitlab.gnome.org/GNOME/librsvg)
(used in ImageMagick and heaps more)
This is a blazingly fast library to work with SVG files

If you are a performance-driven developer, [RSVG convert](https://gitlab.gnome.org/GNOME/librsvg/-/blob/master/src/bin/rsvg-convert.rs) in particular will blow your mind

Also you should follow [Federico Mena-Quintero](https://people.gnome.org/~federico/blog/tag/librsvg.html) Who is dragging RSVG into the future.


## [Imagetracer JS](https://github.com/jankovicsandras/imagetracerjs)

There are many bitmap to vector tracers like [potrace](http://potrace.sourceforge.net/), autotrace etc. Imagetracer is the most promising for web developers and has a few tricks up it's sleeve.

Handy to have on the CLI too:
```
imagetracerjs/nodecli>node nodecli ../in.png outfilename out.svg scale 10
```

## [2geom](https://gitlab.com/inkscape/lib2geom)

Fun fact, Inkscape uses 2geom under the hood.

If you're building something that needs to perform 2d computational geometry - you'll end up grateful for Nathan Hurst and all other contribnutors


## Single-purpose SVG generator tools 

[blob maker](https://www.blobmaker.app/)
   does one thing, makes blobs
  
[noise maker](https://codepen.io/georgedoescode/full/dyNVNjG)
  nice patterns of directional lines or dots

[Wave Maker](https://yoksel.github.io/wave-maker/)

## [Create.Rip](https://create.rip)

Easily convert design files to web ready formats then extract individul elements. 
Accepts most traditional formats (PDF AI PSD TIFF etc) .

I'd be remiss for not including this one.

https://create.rip is a web service we built at Outfit for ourselves with the help of [embersea](http://www.embersea.io/) and [devaway](https://devaway.io/)

We decided to host and share it with the world -

Dedicated in memory to Ihor Novikov author of the Uniconvertor and Sk1 who passed March 15th, 2021 hospitalised by a stroke and subsequently COVID-19