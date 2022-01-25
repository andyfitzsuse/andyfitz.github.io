---
title: Get individual SVG's back from IconFonts
date: 2022-01-26
tags:
  - svg
  - minimal
  - tips
layout: layouts/post.njk
---
 
In this tutorial I'm going to show you how to decompile a big bloated icon font into a series of small, neat, and portable SVG files.  It's dead easy.

First install [Fontforge](https://fontforge.org/) on your system

Fedora Linux
```
sudo dnf install fontforge
```
MacOS
```
brew install fontforge
```

Just change the package manager for your distribution: 
eg Debian/Ubuntu with ```sudo apt install fontforge``` 
 

Now for the magic one liner, just copy and paste this in your terminal and replace ```youriconfont.woff``` with the path to your icon font file.

```
fontforge -lang=ff -c \\
'Open($1); SelectWorthOutputting(); \\
foreach Export("svg"); endloop;' \\
youriconfont.woff
```


You'll now have a standalone SVG file for every glyph in your icon font. If you don't care about naming feel free to head to the [bonus round](#bonus-round)

## But those filenames, they suck right?

Because the font file knows nothing about what each shape is called, the filenames take the unicode value for each character represented like so you'd think you're stuck with filenames like :  **``` uniE9AF_youriconfont.svg ```** 

Good news, your existing CSS should have something like this (but probably bigger):

```
.icon-pacman:before {
  content: "\e916";
} 
.icon-leaf:before {
  content: "\e9a4";
}
.icon-airplane:before {
  content: "\e9af";
}
```

> Yarr, thar be useful names' 

What I do is a bulk find and delete on the common CSS markup so that we're left with something like this:

```
icon-pacman,e916 
icon-leaf,e9a4 
icon-airplane,e9af 
```

As my SED and AWK skills are terrible, I just opened that output as a CSV in a spreadsheet, converted the unicode column to uppercase (if you need to), flipped the columns order, and was left with new CSV output like this:

```
E916,icon-pacman 
E9A4,icon-leaf 
E9AF,icon-airplane 
```


I dutifully do another 3 find and replace commands:

replace first line with ```mv uni```

replace all commas with ```_youriconfont.svg   ``` (trailing space)

replace linebreak with ```.svg``` followed by a line break


The output now looks like this: 
```
mv uniE916_youriconfont.svg pacman.svg 
mv uniE9A4F_youriconfont.svg leaf.svg
mv uniE9AF_youriconfont.svg airplane.svg
```

I run that and rejoice

This finally replaces all filenames with the sane names given to them by the CSS.

I'm sure I can script this reconciliation part but I do like doing it manually as all CSS is crafted slightly differently so it's good to be eyes-on in case there is some rogue CSS to clean up.

You probably only need to do this once. 
If you're doing this every day well... then you might be a competitor of my employer, so shoo shoo 👀


# Bonus round
### install SVGO on your system 
(I prefer to use NPM as it works on linux and mac hosts alike)  
```
npm install -g svgo
```


Now you can simply enter the directory and run 
```
svgo *.svg
```

That's it.

Your files will have ```fill="currentcolor"``` applied to them so when you inline the SVG inside markup they will adhere to your CSS ```color:``` value just like the good-ol days.

# A little history

I'll cover why you would you ever need or want to do this. Icon Fonts were once an answer to easy web design. 
They exploded on the scene once [```@fontface```](https://caniuse.com/fontface) was supported by major browsers.  
iconfonts gave us all the icons you could need within a single HTTP-request - which was great if you had a lightning fast CDN and agressive caching.  You used them usually with CSS pseudo elements and custom character ranges. That's where things get hairy for our a11y friends.

Remember image sprites? Iconfonts as a technique came after image sprites for single-payload single-color icon sets. Before frameworks like react or powerful site generators it made sense to align your icons and marks with your typographic layout - browsers werent always so nice so this kept things on 'some' guardrails. 
Plus services like [IcoMoon](https://icomoon.io) emerged which made creating custom icon sets easy. 

But of course like I mentioned the accessibility was terrible. 
Worse, some text layout engines mutilated iconsfonts.  Think of the carnage the CSS ```text-rendering: optimizeSpeed;```   would do to your illustrations.

### We now live in the future
With the advent of modern frameworks and the popularity of best practices like [ARIA atrributes](https://css-tricks.com/accessible-svg-icons/). Icon fonts just arent the most suitable technique anymore; not by a long shot.

But much of the internet is still littered with websites and apps that depend on iconfonts.  And for those poor buggers, it's not without effort to climb into modern times. 

We see this often at [outfit.io](http://outfit.io) whenever we have a new client with only a website to ingest their existing brand assets from.

Once we have the clean illustrations (that were often lost) back in a malleable and minimal format, our web developer counterparts can shed hundreds of kilobytes of frontend bottleneck from their sites and apps.

I hope this helps you
