---
layout: layouts/homepage.njk
date: 2021-04-12

---

<section>G’day, you've found Andy Fitzsimon</section>

<p class="scroll fade">Booster fixer, handy andy is more than a nickname</p>
<p class="scroll fade">Recently, I resumed <a href="/posts">blogging</a> </p> 


 
<svg class="scroll pen" 
 style="max-width: 25vw; fill:var(--neutral); display:block; max-height: 10em;  margin:2em auto;" 
 viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <path d="M33.8 62l25-25.2C54.8 33 49.3 31 46 35.7L31 58.7l2.7 3.3zM11.4 81.5c0-3.7 4.8-10.8 9.6-10.8 2.6 0-.6 2.7-.6 4.5 0 2 13.8-3.4 9.5-11-1.7-2.8-4.8-3.4-8-2a20.7 20.7 0 00-11.5 19.3c0 1 1 1 1 0zm57.8-37.6l-.5-2.5c.3 0 5.8-1 8.8-6.1 3-5.4 1.3-11.2 1.3-11.2l-8.4 5.7-.6-1.6L92.1 5l1.6 1.5c-5.3 8.8-5.8 18.8-8.7 25-4.5 9.7-15.8 12.5-15.8 12.5zM52 26.9s2.7-11.4 12.4-16c6.1-3 16.2-3.6 25-9l1.5 1.5L67.5 26a4 4 0 00-1.5-.5l5.5-8.5s-5.8-1.6-11.1 1.5c-5.2 3-6 8.5-6 8.9zM2 94c8-14 3.9-36.4 26.1-36.4L44 32.8c3.9-6.2 11.9-5 18.1 1.2 6.3 6.2 7.7 13.8 2 17.5L38 67.7C38 90.1 16.5 85.8 2 94.1z"/>
</svg>




<style>
.scroll.map{margin:2em auto;}

.scrolled.pen{
  animation: brush 3s ease infinite;}

.scroll.map path {
  stroke-dasharray:  344 344; 
  stroke-dashoffset:-344;
  stroke-width: 3; 
  stroke-opacity:0}


.scroll.map circle{
  stroke-width: 5; 
  transition: all 1.5s ease  .2s;}

.scroll.map.scrolled circle{
  stroke-width:10; 
  fill:var(--tone-2)}
.scroll.map.scrolled path{
  stroke-width: 5;
  stroke-dasharray:  344 344; 
  stroke-opacity:1;
  stroke-dashoffset:0;
  transition: 
    stroke-dashoffset 1.5s ease,
    stroke-width 1.5s ease;}


p.scroll{
  min-height:10vh;
}
.scroll.fade{
  opacity:0; 
  transform: translate(0,2em)}
.scrolled.fade{
  opacity:1; transform:none;
  transition: 
    transform 1s ease, 
    opacity 1s ease}
</style>

