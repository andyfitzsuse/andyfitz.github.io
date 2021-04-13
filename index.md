---
layout: layouts/home.njk
date: 2021-04-12

---

G'day traveller, I'm Andy Fitzsimon<br> from Noosa, Australia.  

<i style="color:var(--neutral)">153.104 -26.408
 (he/himself)</i>

<p class="scroll fade"></p>


<svg class="scroll map" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" style="max-width:40vw">
  <path fill="none" stroke-linejoin="round"  stroke="var(--neutral)" d="M77 85l1 7 2 2h2l2-3 1-4v-2l-5 1zM71 4l4 8 3 2 2 9 8 5 1 4 2 1v3l6 5v4l1 3-2 9-7 13v5h-4l-3 4-5-2-3 2-8-3-1-4-2-3h-2l1-4-2 1 1-5-6 5-5-7-10-2-4 3h-6l-3 4H17l-5 4-6-4 2-6-3-3-1-4-3-8 2-3v-6l8-6 9-2 4-7 9-8 3 4 4-1 2-6 5-3 10 3v3h-3v3l12 7 2-7V7z"/>
<circle cx="96" cy="42" r="3" stroke="var(--brand)" fill="var(--bg)" />
</svg><br>

<p class="scroll fade">I work with talented friends &mdash; together we make stuff. <br>Thanks to over 20 years at places like <a href="https://www.suse.com/" target="_blank">SUSE</a>, <a href="https://www.redhat.com/" target="_blank">Red Hat</a>,  and now <a href="https://www.outfit.io/" target="_blank"> Outfit</a> </p>

<svg class="scroll o-logo" style="margin-bottom:4em" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 19 8.5" stroke="#e40046" fill="none">
  <circle cx="2.36" cy="6.12" r="1.68"/>
  <path d="M 5.35 4V 6.5A 1.02 1 0 008 6.5V 4.5 H 18.68"/>
  <path d="M 10.2 8.2v -6"/>
  <path d="M 12.5 8.2V 2A 1.3 1.2 10 0114.5 1"/>
  <path d="M 14.8 8.2V 4.5"/>
  <path d="M 17.1,8.2v -6"/>
  <path d="M 14.8 2.7v.001" stroke-linecap="round"/>
</svg>


<p class="scroll fade">I enjoy strategy, design, and code.</p>
<p class="scroll fade"> Recently, I resumed <a href="/posts">blogging</a> </p> 

 
<svg class="scroll pen" style="max-width: 30vw; fill:var(--neutral); display:block; margin:2em auto;" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <path d="M33.8 62l25-25.2C54.8 33 49.3 31 46 35.7L31 58.7l2.7 3.3zM11.4 81.5c0-3.7 4.8-10.8 9.6-10.8 2.6 0-.6 2.7-.6 4.5 0 2 13.8-3.4 9.5-11-1.7-2.8-4.8-3.4-8-2a20.7 20.7 0 00-11.5 19.3c0 1 1 1 1 0zm57.8-37.6l-.5-2.5c.3 0 5.8-1 8.8-6.1 3-5.4 1.3-11.2 1.3-11.2l-8.4 5.7-.6-1.6L92.1 5l1.6 1.5c-5.3 8.8-5.8 18.8-8.7 25-4.5 9.7-15.8 12.5-15.8 12.5zM52 26.9s2.7-11.4 12.4-16c6.1-3 16.2-3.6 25-9l1.5 1.5L67.5 26a4 4 0 00-1.5-.5l5.5-8.5s-5.8-1.6-11.1 1.5c-5.2 3-6 8.5-6 8.9zM2 94c8-14 3.9-36.4 26.1-36.4L44 32.8c3.9-6.2 11.9-5 18.1 1.2 6.3 6.2 7.7 13.8 2 17.5L38 67.7C38 90.1 16.5 85.8 2 94.1z"/>
</svg>

<br>
<p class="scroll fade">If you'd like to know more about me, here's my story.<br><br></p>
<p class="scroll fade"> <a class="button" href="/story">my story</a></p>


<style>
.o-logo{margin: 2em auto; display:block;max-width: 70vw}
.scroll.map{margin:2em auto;stroke-dasharray:  344 344; stroke-dashoffset:-344;stroke-width: 9; opacity:0}

.scroll.map.scrolled{stroke-width: 1;stroke-dasharray:  344 344; opacity:1;stroke-dashoffset:0;transition: stroke-dashoffset 1.5s ease, stroke-width 1.5s ease;}
.o-logo>*{opacity:0}.scrolled.o-logo>*{animation:in-out 1s ease reverse;opacity:0;animation-fill-mode:forwards}.scrolled.o-logo>:nth-child(2){animation-delay:.1s}.scrolled.o-logo>:nth-child(3){animation-delay:.2s}.scrolled.o-logo>:nth-child(4){animation-delay:.3s}.scrolled.o-logo>:nth-child(5){animation-delay:.4s}.scrolled.o-logo>:nth-child(6){animation-delay:.5s}.scrolled.o-logo>:nth-child(7){animation-delay:.7s;animation-duration:.5s;animation-name:dotup;animation-duration:.6s;animation-direction:reverse;animation-delay:0;transform-origin:0;animation-timing-function:cubic-bezier(.6,-.3,.2,0)}@keyframes in-out{0%{stroke-dasharray:19.5 0;opacity:1}100%{stroke-dasharray:0 19.5;opacity:1}}@keyframes dotup{0%{stroke-width:1;opacity:1;transform:translate(0)}100%{stroke-width:.5;transform:translate(0,2px);opacity:0}}

p.scroll{min-height:10vh;}
.scroll.fade{opacity:0; transform: translate(0,2em)}
.scrolled.fade{opacity:1; transform:none;transition: all 1s ease}
</style>

<script>
  // vanilla JS on scroll detection
const scrollElements=document.querySelectorAll(".scroll"),elementInView=(e,l=1)=>{return e.getBoundingClientRect().top<=(window.innerHeight||document.documentElement.clientHeight)/l},elementOutofView=e=>{return e.getBoundingClientRect().top>(window.innerHeight||document.documentElement.clientHeight)},displayScrollElement=e=>{e.classList.add("scrolled")},hideScrollElement=e=>{e.classList.remove("scrolled")},handleScrollAnimation=()=>{scrollElements.forEach(e=>{elementInView(e,1.25)?displayScrollElement(e):elementOutofView(e)&&hideScrollElement(e)})};window.addEventListener("scroll",()=>{scrollElements.forEach(e=>{elementInView(e,1.25)?displayScrollElement(e):elementOutofView(e)&&hideScrollElement(e)})});
</script>