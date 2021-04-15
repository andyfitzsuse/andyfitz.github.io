---
title: Essential SVG tools
description: We all could use a little help making SVG the leanest and meanest 
date: 2021-04-15
tags:
  - svg
  - minimal
  - tools
layout: layouts/post.njk
---
<svg viewBox="-7 0 24 10" style="height:15em; width:100%;background-color:#f87; fill:#fca"> <path fill="#fff" d="M-3 3H1V7H-3M8 7H13L10.5 3M5 3A2 2 0 105.001 3" /></svg>

This article contains SVG tools I reach for depending on need. 
As the rifleman's creed goes: *“there are many like it but this one is mine”*.  
I like this list. 

 

## Preamble

My affair with SVG began back when Adobe offered <a href="https://www.w3.org/TR/1998/NOTE-PGML" target="_blank"  rel="noreferrer">PGML</a>. I loved flash, but figured open standards would win the browser wars . You can read about<a href="https://www.w3.org/Graphics/SVG/WG/wiki/Secret_Origin_of_SVG"> SVG's origins</a> here.


Once W3C released the SVG draft: I figured it would own the web and be supported by all major browsers within months (it took years). Nevertheless, my courtship began.

Fortunately SVG was more useful than just internet use. 
By 2003, I had toyed with SVG in my studies. 
By 2005, I had finally used SVG commercially thanks to [Red Hat](https://redhat.com) (and UTF-8). 

SVG assists me in many tasks – from websites, to presentations, to apps, to toolchains.  
Here's what I use today:  Some are online tools, some are scripts, some are desktop apps, some are libraries. All incredibly powerful (and/or fun) for the right situation. 
So here goes, get your bookmark tool of choice fired up:

## [SVGOMG](https://jakearchibald.github.io/svgomg/)
<a href="https://jakearchibald.github.io/svgomg/" target="_blank" rel="noreferrer"><svg viewBox="0 0 600 600" style="height:15em; width:100%;background-color:#0097A7;"><path fill="#00BCD4" d="M-2000 0H3000V395.68H-2000Z"/><path d="M269.224 530.33L519 395.485H269.224V530.33zM214.35 91.847H519v303.638H214.35V91.847z" opacity=".22"/><path fill="#FFF" d="M80 341.735h189.224V530.33H80z"/></svg></a>

The webinterface to SVGO is so handy, I also use SVGO directly in apps and on the commandline.  Everybody should have local access to it.

```
npm install -g svgo
```

If you use [webpack](https://webpack.js.org/), [snowpack](https://wwwz.snowpack.dev/), [vite-svg-plugin](https://www.npmjs.com/package/vite-plugin-svg) etc you likely use it too.
The plugins are fascinating and have bailed me out many times.

There's also [SVG Cleaner](https://github.com/RazrFalcon/svgcleaner) which has some compelling benefits over SVGO.


## [SVG Path Editor](https://yqnn.github.io/svg-path-editor/)
<a href="https://yqnn.github.io/svg-path-editor/" target="_blank" rel="noreferrer"><svg viewBox=" -1-1 15 15" style="height:15em; width:100%;background-color:#678; fill:#eee">  <path d="M 4 8 L 10 1 L 13 0 L 12 3 L 5 9 C 6 10 6 11 7 10 C 7 11 8 12 7 12 A 1.42 1.42 0 0 1 6 13 A 5 5 0 0 0 4 10 Q 3.5 9.9 3.5 10.5 T 2 11.8 T 1.2 11 T 2.5 9.5 T 3 9 A 5 5 90 0 0 0 7 A 1.42 1.42 0 0 1 1 6 C 1 5 2 6 3 6 C 2 7 3 7 4 8 M 10 1 L 10 3 L 12 3 L 10.2 2.8 L 10 1" /> </svg></a>
I use this now more than even [Inkscape](http://www.inkscape.org/) for simple illustrations, and I really wish the preview would let me add my CSS. But still, this thing is pure GOLD!
When finishing an illustration I often return to this tool and go path by path to reduce unnessecary coordinates and operators. Stealing a few decimals here and there, replacing cubic bezier path operators with more optimal ones like quadratics or arcs.   

SVG path editor will dramatically improve your understanding of the SVG path system.
Also try out this [SVG path visualizer](https://svg-path-visualizer.netlify.app/#M5%208.5l3-4c2-3-3-4-3-1%200-3-5-2-3%201z)  I put the heart from this article in it's URL param - very handy when teaching SVG.


## [SVG Crop](https://svgcrop.com/)
<a href="https://svgcrop.com/" target="_blank" rel="noreferrer"><svg viewBox="0 -1 10 12" style="height:15em; width:100%;background-color:#123; stroke-width:.5; stroke:#e3e6e9; stroke-miterlimit:9"><path fill="#7298a0" d="M 5 1 a 4 4 0 1 0 0.001 0 " /><path d="M 1 1 h 4 l -2 8z" stroke="#123" stroke-width="1"/><path fill="#a43365" d="M 1 1 h 4 l -2 8z" /></svg></a>

Remove the extra margin from around your SVG content so the file is easy to work with.
SVGcrop.com resizes the SVG artboard by changing the ```viewBox="..``` attribute
It's not 100% bulletproof (invisible shapes like clippaths will affect the viewBox) but handy all the same.

## [SVG URL Encoder](https://yoksel.github.io/url-encoder/)

Inline SVG into CSS - hey it's a gnarly technique but I still find myself throwing SVG into pseudo elements all the time. Think of the saved HTTP request! 
This tool from Yoksel makes it super easy!

## [Relative clip-path ](https://yoksel.github.io/relative-clip-path/)

For turning SVG paths into CSS-friendly `clip-path` coordinates. Super handy.

## [SVG Fitler Builder](https://svgfilters.com/)
<a href="https://svgfilters.com/" target="_blank" rel="noreferrer"><svg xmlns="http://www.w3.org/2000/svg" style="height:15em; width:100%;background-color:#4b5ca3;" viewBox="0 -10 119.9 164.8" ><path fill="#6795e9" d="M75.2 79.3a22.9 22.9 0 0043.5 0zm-3.7 23.8a23.1 23.1 0 00-26.9 3.2c-7.2 7-8.1 18-3.6 26.8z"/><path fill="#41bfd0" d="m97.5 50c-4.9 0-10 1.6-13 4.3a1.6 1.6 0 00-.2 0a23.8 23.8 0 00-2 1.6c-5.7 4.3-23.6 13.7-46-1l-1.8-1.3a22.4 22.4 0 10.5 37.3a22.3 22.3 0 002.5-1.9c12.2-9.5 23-9 23-9h40.6c5.8 0 11.7 3 11.7 8.7a22.4 22.4 0 00-15.3-38.7zm-22.1 30c-.7 10.5-9.6 20.7-9.6 20.7l-13.5 20.2c-3.4 4.8-9 8-13.8 4.7c3 20 28.9 26 40.5 9.5c2.8-4 4.4-9.2 3.8-13.2l.1-.2-.1-2.5c-.3-6.8 1.2-19.3 18.2-24.5a22.9 22.9 0 01-25.5-14.7zm37.4 8.6zzzm-52.8-88.6a23 23 0 10.001 0"/></svg></a>
Creating complex SVG Filters is incredibly hard, Thankfully we have this brilliant tool.
There's an alternative [SVG Filter Constructor](https://yoksel.github.io/svg-filters/#/) by [Yoksel](https://yoksel.github.io) with a less intimidating interface that's worth a look.
Actually [Boxy SVG editor](https://boxy-svg.com/app) has a great compositing editor which is easy to use too.


## [SVG Gradient Map Builder](https://yoksel.github.io/svg-gradient-map/#/)

Who doesn't love Duotone effects?  SVG Gradient Map filters make them achievable native on the web. 
There's just one annoying catch.  when you are coding these you need to convert your R G and B into separate channels and divide by 255 then place them your R G and B numbers for different colours next to eachother - it feels kind of unnatural.
This tool makes creating a custom filter easy.

If you want to automate this, I also [wrote a CodePen](https://codepen.io/andyfitz/pen/KKagbqe) that converts any array into swatches and a duotone effect.


## [Inkscape](https://inkscape.org/)
<a href="https://inkscape.org" target="_blank" rel="noreferrer"><svg viewBox=" 0 0 100 100" style="height:15em; width:100%;background-color:#e2e6e9; fill:var(--dark)"><path d="M 40.8 7 L 7.2 41.3 C -5 55.2 14.9 53.7 23.1 57.8 C 27.3 59.8 12 63 15 66 C 18 69 32 71 35.6 75 C 39 78 29.5 81 32.4 83.9 C 35.4 86.9 42.1 84.1 43.4 91 C 44.3 96 55.6 93.2 61.1 89.1 C 64.1 86.1 55.5 86.4 58.5 83.4 C 65.8 75.9 72.5 80.7 75 73.2 C 76.3 69.5 63 67 67 64.5 C 75.7 59.5 105 56.6 91 42.5 L 56.2 7 Q 48.5 -1 40.8 7 Z M 79.4 73 C 78.8 75 91.9 76 91.9 72.8 C 90.1 67.6 81 68 79.4 73 Z M 32 78 Q 26 75 23 78 T 24 83 T 32 78 M 77.8 76.7 C 74 80.1 78 83.8 82 81.4 C 83 80.6 82 77.6 77.8 76.7 Z M 32.8 59.7 Q 41 62 50.5 63.4 C 52 63.6 51 65.2 49.3 65.6 C 45.7 66.6 28.3 59.6 32.8 59.7 Z M 54.1 9.4 L 67.3 22.9 Q 69.6 25.3 68 27.4 L 61.4 22 L 60 30 L 54.5 27 L 45.6 32.6 L 42.6 21 L 38 29 H 30.7 Q 23.9 29 30.1 22.6 L 43.1 9.4 Q 48.4 3.5 54.1 9.4 Z" /></svg></a>

Isn't the evolution of open source desktop applications awesome? 
[Gill > Sodipodi > Inkscape](https://wiki.inkscape.org/wiki/index.php/InkscapeHistory)
I've loved this journey and especially love where it is now.
Run it on your linux machine, your mac .. its brilliant for creative exploration, and especially illustration.
I've used Inkscape since it's inception. Demoed it around the planet and pleaded for top designers to consider it. I could go on and on but let me just say it's **the very best tool for illustration of complex paths**. and leave the rest up to your imagination.

## [Penpot](https://penpot.app/)
<a href="https://penpot.app/" target="_blank" rel="noreferrer"><svg viewBox="0 -1 10 12" style="height:15em; width:100%;background-color:#83f5d4; fill:none; stroke-width:.4; stroke:var(--dark)"><path d="M2.3 3.4V1.6L3.2.3l.9 1.3V2L5 .7 5.9 2v-.4L6.8.3l.9 1.3v1.8M5 4.8v5M2.3 2.5l-.9.5v5L5 9.8 8.6 8V3l-.9-.5M1.4 3L5 4.8 8.6 3M4.1 2v2.3M5.9 2v2.3M2.9.8h.6m1.2.4h.6M6.5.8h.6"/><path stroke-width=".3" d="M2.3 1.8h1.8m0 .4h1.8m0-.4h1.8m-4.5 0v2M5 2.2v2.6m1.8-3v2.1"/></svg></a>
Early days to call this a Figma killer - But I do find it does most of what I want out of Figma (for free and freedom). Super impressed and excited to see where this project goes.

## [RawGraphs ](https://app.rawgraphs.io/)
<a href="https://app.rawgraphs.io" target="_blank" rel="noreferrer"><svg viewBox="0 0 14 5" style="height:15em;width:100%;background-color:#f2f6fa; font-family:Work Sans, sans-serif; font-weight:300;" fill="#0dc4a3" ><text font-size="2" x="7" y="3" text-anchor="middle" dominant-baseline="middle"><tspan fill="#3e3e41" font-weight="900">RAW</tspan>Graphs</text></svg></a>
Brilliant way to pre-render beautiful data graphics, create the layout in rawgraphs then style with your own CSS. 

## [Boxy Editor](https://boxy-svg.com/app)
<a href="https://boxy-svg.com/app" target="_blank" rel="noreferrer"><svg viewBox="0 0 1024 1024" style="height:15em;width:100%;background-color:hsla(211, 86%, 57%, 1.00);"><path fill="#de6547" d="M132.4 732V291.5l202.9 117.9v205L132.4 732z"/><path fill="#fdbc4d" d="M513 952.7V722.4L335.2 614.5 132.4 732 513 952.7z"/><path fill="#69b356" d="M891.6 732V291.5L688.7 409.4v205L891.6 732z"/><path fill="#d1e993" d="M513 952.7V722.4l175.7-107.9L891.6 732 513 952.7z"/><path fill="#80b7fa" d="M513 71.3v230.3L335.2 409.5 132.4 292 513 71.3z"/><path fill="#4581e1" d="M513 71.3v230.3l175.7 107.9L891.6 292 513 71.3z"/><g><path fill="#fff" stroke="#2f2f2f" stroke-width="66.880944" d="M585 542.3h90.2a43.6 43.6 0 100-60.5H585l63.8-63.8h.8a43.6 43.6 0 10-43.6-43.6v.8L542.3 439v-90.2a43.5 43.5 0 10-60.5 0V439L418 375.2v-.8a43.6 43.6 0 10-43.6 43.6h.8l63.8 63.8h-90.2a43.6 43.6 0 100 60.5H439L375.2 606h-.8a43.6 43.6 0 1043.6 43.6v-.8l63.7-63.8v90.2a43.5 43.5 0 0030.3 75 43.6 43.6 0 0030.3-75V585l63.7 63.8v.8a43.6 43.6 0 1043.6-43.6h-.8z" paint-order="stroke"/></g></svg></a>
At first sight, boxy looks like yet another svg-edit clone. But open up the panels and start editing (start using the i and o keys) and you'll see why it's fantastic for small projects.

## [librSVG](https://gitlab.gnome.org/GNOME/librsvg)
<a href="https://gitlab.gnome.org/GNOME/librsvg" target="_blank" rel="noreferrer"><svg viewBox="0 0 10 10" style="stroke-linecap:round;height:15em;width:100%;background-color:#555" fill="none" stroke="#eee" stroke-width=".4"><path d="M2 4A1 1 0 102.001 4M7 1A1 1 0 107.001 1M2 5 7 7V2M5.5 6.9 7 8.4 8.5 6.9 7 5.4Z"/></svg></a>

This is a blazingly fast library to work with SVG files (used in ImageMagick and heaps more). If you are a performance-driven developer, [RSVG convert](https://gitlab.gnome.org/GNOME/librsvg/-/blob/master/src/bin/rsvg-convert.rs) in particular will blow your mind. Also you should follow [Federico Mena-Quintero](https://people.gnome.org/~federico/blog/tag/librsvg.html) Who is dragging RSVG into the future with Rust.

Worthy mention goes to [reSVG](https://github.com/RazrFalcon/resvg) which is a super performant and powerful alternative to rSVG.

## [Imagetracer JS](https://github.com/jankovicsandras/imagetracerjs)

There are many bitmap to vector tracers like [potrace](http://potrace.sourceforge.net/), autotrace etc. Imagetracer is the most promising for web developers and has a few tricks up it's sleeve.
Handy to have on the CLI too:
```
imagetracerjs/nodecli>node nodecli ../in.png outfilename out.svg scale 10
```

## [2geom](https://gitlab.com/inkscape/lib2geom)
<a href="https://gitlab.com/inkscape/lib2geom" target="_blank"  rel="noreferrer"><svg viewBox="0 0 10 10" style="height:15em;width:100%;background-color:#eee" fill="none" stroke="#222" stroke-linejoin="round" stroke-linecap="round"><path stroke="#4e9a06" d="M 0.8 3 C 1.8 2 3.8 2 3.8 4 C 3.8 6 0.8 5.4 0.8 7 H 3.8"/><path d="M 5.4 9 C 10.1 9 5.6 2.8 9 2 M 6.25 7 a 1.4 1.4 0 1 1 0.01 0 z" /></svg></a>
If you're building an app that needs to perform fast and accurate 2d computational geometry (boolean operations and way way more) you'll end up grateful for [Nathan Hurst](http://njhurst.com/) and all other contributors who made lib2geom possible.
Fun fact, Inkscape uses 2geom under the hood and also powers the amazing live path effects etc.


## Single-purpose SVG generator tools 
<svg  viewBox="0 0 72 72" style="height:15em;width:100%;background-color:#e2e6e9; font-family:Work Sans, system-ui, sans-serif; font-weight:300;" ><path fill="#f93" d="M14 50C7 36 25 6 42 5s32 27 22 42c-9 15-43 17-50 3z"/><path fill="#f06" d="M40 36c6 6 15 11 16 16-2 15-25 17-35 11C9 55 1 37 8 25c4-6 13-10 19-7 5 3 8 11 13 18"/> <text font-size="55" x="36" y="40" text-anchor="middle" dominant-baseline="middle" fill="#fff" font-weight="900">B</text></svg>
[Blob Maker](https://www.blobmaker.app/) and [Wave Maker](https://getwaves.io/) - both part of the super cool [haikei app](https://app.haikei.app/)
[Noise maker](https://codepen.io/georgedoescode/full/dyNVNjG) nice patterns of directional lines or dots
[Arc Wave Maker](https://yoksel.github.io/wave-maker/) nifty example of repeating arc paths
[Snowflakes](https://www.misha.studio/snowflaker/) Random snowflakes 
[Snowflake Painter](https://yoksel.github.io/snowflake/) Design a snowflake with lines

<!-- 
## [Create.Rip](https://create.rip)

Easily convert design files to web ready formats then extract individul elements. 
Accepts most traditional formats (PDF AI PSD TIFF etc) .

I'd be remiss for not including this one.

https://create.rip is a web service we built at Outfit for ourselves with the help of [embersea](http://www.embersea.io/) and [devaway](https://devaway.io/)

We decided to host and share it with the world -

Dedicated in memory to Ihor Novikov author of the Uniconvertor and Sk1 who passed March 15th, 2021 hospitalised by a stroke and subsequently COVID-19 -->


## What else?

Well there's lots of nifty things I havent personally climbed into. 

[Canvas2SVG ](https://github.com/gliffy/canvas2svg ) - I have a feeling I'll get to know this library well someday.
[Apache Batik](https://xmlgraphics.apache.org/batik/)  - I used it quite a bit in the early days but it never took root in my toolchain.  
[SVGJS](https://svgjs.com/docs/3.0/) It offers compelling shortcuts, I'm just a fan of vanilla JS. This also goes for [SNAP SVG](http://snapsvg.io/)


# Thank you SVG

<svg viewBox="0 0 10 10" style="height:15em; width:100%;background-color:#f87; fill:#fff" stroke="#fca" paint-order="stroke" stroke-width="2" stroke-linejoin="round"><path d="M5 8.5l3-4c2-3-3-4-3-1 0-3-5-2-3 1z" /> </svg>

So there you have it, the best tools to help you with SVG.
By the way, all the images in this article were super-tiny inlined SVG - open web inspector and see for yourself.

On a personal note:
There are heroes I'd like to recognise; friends who moved SVG forward directly or indirectly - at least in my universe: 
[Cam Mcormack](https://mcc.id.au/), [Raph Levien](https://raphlinus.github.io/), [Chris Lilley](https://svgees.us/), [Carl Worth](https://cworth.org/), [Liam Quinn](https://www.w3.org/People/Quin/), [Nathan Hurst](http://njhurst.com/), Peter Moulder, [Tavmjong Bah](http://tavmjong.free.fr/), [Bryce Harrington](https://twitter.com/bryceharrington), [Aaron Spike](https://www.ekips.org/), Jon Cruz, Bulia Byak, [Ted Gould](https://gould.cx/ted/), [Doug Schepers](http://schepers.cc/), [Dom Lachowicz](https://twitter.com/domlachowicz), [Dodji Seketeli](https://twitter.com/dodjiseketeli), [Owen Taylor](https://blog.fishsoup.net/) and so many more. 

<style>article svg{border-radius: 1em;}article a:hover svg {box-shadow: 0 0 0 .3em var(--brand); transition: box-shadow .2s ease} article a svg > *{transition: transform .25s ease; transform-origin:50% 50%; transform:scale(.9)}article a:hover svg > *{transition: transform .35s cubic-bezier(.4,.2,.1,1.5); transform-origin:50% 50%;transform:Scale(1)}</style>