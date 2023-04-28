---
title: User guide for working with Andy
layout: layouts/post.njk
templateClass: userguide

---
<style>time{display:none}
article h2{font-size:2.5em; padding:.5em 0;}
.twocol{display:grid; grid-template-columns: 1fr 1fr; gap:2em}
@media (max-width: 40em) {.twocol{grid-template-columns: 1fr}
article, main{position:static;}
[href="#"],
[href="#pagenav"]{box-shadow:none;background-color: transparent; display:block; height:3em; width:3em; padding:.5em;z-index:91; position:fixed; bottom: 3rem; right:0; cursor:pointer;}
[href="#"]{bottom:0rem;  }
#pagenav{display:none;  opacity:0; pointer-events:none; }
#pagenav:target{display:grid; opacity:1; pointer-events: all;grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr; background-color: var(--bg-2); animation: showme 1s ease infinite}
@keyframe showme{ 0%{transform: scale(.7); opacity:0} 100%{opacity:1; transform:none;}}
#pagenav a{padding:0}
.pagenav{background-color: var(--bg-3)}
#pagenav:target{position:fixed; top:0; right:0; bottom:0; left:0; padding:0; overflow:none; z-index:90}
}
.pagenav{grid-template-columns:1fr;z-index:99;
grid-auto-flow: row;}
@media (min-width: 40em) {
    
    [href="#"],
[href="#pagenav"]{display:none}
footer{padding-left: 10em;}
article{padding-left: 20%;  }
.pagenav{width: 20%}
.pagenav{ position:fixed; max-height:calc(100vh -6rem); overflow-x:hidden; overflow-y:auto; top:6rem; left:0; }
.pagenav a{text-align:left; line-height:1em;}
.pagenav a:active{color: var(--fg)}
}
.time-management svg{fill:none; stroke:currentColor; stroke-width:.5;  max-width: 3em; display:block; color: var(--neutral);stroke-miterlimit:9;}
.time-management > div {margin-bottom:1rem;display:grid; grid-template-columns: 4em auto}
</style>

This guide may help shortcut concerns and clarify aspects of my approach that you’d otherwise need time to learn.   
If you like to RTFM, this is for you.
<div><a href="#" title="Top of page"><svg viewBox="0 0 6 6" fill="none" stroke="currentColor" stroke-linecap="round"><path d="M3 1V5M1 3 3 1 5 3" /></svg></a><a href="#pagenav" title="Shortcuts"><svg viewBox="0 0 6 6" fill="none" stroke="currentColor" stroke-linecap="round"><path d="M1 1H5M1 3H5M1 5H5" /></svg></a> 
<nav class="pagenav" id="pagenav"> 
<a href="#how-i-view-success">Success</a>
<a href="#how-i-communicate">Communication</a>
<a href="#what-may-annoy-you">Quirks</a>
<a href="#what-gains-and-loses-my-trust">Trust</a>
<a href="#my-strengths">Strengths</a>
<a href="#my-growth-areas">Weaknesses</a>
<a href="#what-i-expect-from-people-i-manage">Expectations</a>
<a href="#how-i-give-and-receive-feedback">Feedback</a>
</nav>
</div>

## How I view success

Success closely follows my **values** and my **mantra** which you can <a href="/">explore on my homepage</a>. 
Beyond that, success could be framed within wartime or peacetime contexts:

<div class="twocol">

<div>

### Peacetime
Success looks very <dfn data-title="Good Change: Continuously Improving">kaizen</dfn>, ideally it’s fast non-linear growth of the business I directly contribute to.  Optimizing for high margins, and fortifying advantages.  
Success is forward-looking, creatively inspired, where risk is self-healing. 
</div><div>

### Wartime 
Success looks like existentially-bound innovation, unconventional alliances, and clear minded reality checks. 
Success is grounded, constantly-measured, fighting with everything then winning.</div>
</div>
I’ve enjoyed both in equal measure and sometimes operate bimodally across facets of  work.  Colleagues have seen me thrive in wartime, but like most: I personally prefer peacetime.


## How I communicate

I’m direct and honest but also kind. 
I try very hard to call a spade a spade without getting punched in the mouth.  Meaning, I'll write with considered language yet be very candid interpersonally with those I trust. 

Logistically: 
<div class="time-management">

<div><svg viewbox="0 0 8 7"><path d="M5 5Q1 5 1 3t3-2 3 2c0 1-.2 1.6-1 2v1Z" /></svg><p>
I thrive via <b>instant message</b> chat when it's ad-hoc to make quick decisions.</p></div>

<div><svg viewbox="0 0 8 7"><path d="M1 5V1H7V5zM1 1 4 3 7 1" /></svg><p>
<b>Email</b> is where I prefer well-prepared communication, responding with focused and considered replies. </p></div>

<div><svg viewbox="0 0 8 8"><path d="M3 2a2.5 2.5 0 1 0 .001 0M5 1a2.5 2.5 0 1 0 .001 0"/></svg><p>I enjoy <b>scheduled  1:1’s</b> for the colleagues I feel more distant from as well as for a cadence with my team. I don’t waste these and 3 per quarter is plenty among all other contact.</p></div>

<div><svg viewbox="0 0 8 8"><path d="m4 .5a3.5 3.5 0 10.001 0M4 2V4H6" /></svg><p>I’ve found broadcasting <b>weekly office hours</b> works well - it lowers the barrier to interacting cross functionally. </p></div>

<div><svg viewbox="0 0 8 7"><path d="M1 1h6v5H1zm0 1h6M2 1v1m4-1v1M4 5V3l-.5.3"/></svg><p>I keep my calendar <b>as lean as possible</b> in order to welcome in-flight, unplanned work that aligns with priorities.</p></div>

<div><svg viewbox="0 0 8 8"><path d="M 1.5 1 V 7 H 6.5 V 1 H 4 V 3 L 3.5 2 L 3 3 V 1z"/></svg><p>I record <b>institutional memory</b> to rapidly enable colleagues. Usually this occurs in-context where the work is being done or via an LMS when large bodies of content need management. I also enjoy condensing this information into summaries for briefings and prefer real-time onboarding where possible.</p></div>
</div>
Realistically, I adapt to other modes of communication but the above are my preferred for their given purpose and this is probably a shared preference.

## What may annoy you

#### Infodumping
It’s something I do and a common neurodivergent trait.
There’s a difference between me telling you what you need to know, and excitedly sharing detail only very engaged enthusiasts would find critical. 

When I’m sharing information for a task, **I always frame it**:
 "*For this purpose let’s remember*…"
 "*I suggest you/we __ because*…"
 "*Keep in mind* …"
 "*I’ve learned and you should know* …"

If this context is absent, I am assuming you have the same level of excitement for detail that I do and am missing the mark.  
Cutting me off and saying “I don’t care” or “another time” is absolutely fine and even preferred.  I’ve never been offended by someone wanting to simplify communication. It doesn't hurt my feelings or change my perception of you. If anything I appreciate knowing when you don’t need more information and that the task at hand is obvious. 
By contrast, only geeking out and not resolving outstanding work can be a problem for us both.  If we’re working together, we don’t have an academic relationship. I trust those I work with to accept information given to them with the relevance they need to perform their role.


#### Attention isn’t praise, praise is praise 
Most relevant for anyone reporting to me.
I focus on problems and opportunities more than the areas I trust and know are well-run.  It becomes clear over time that I delight in recognizing and rewarding <acronym data-title="Business As Usual">BAU</acronym> just as much as I do milestones &mdash; shining a light on contributions in all areas.
 
In the short-term, avoid misjudging my focus for recognition or favouritism.
I could be spending more hours with your peers than you if they have more areas of improvement. I could also be spending more hours with a talent because I’m investing where there’s more existing skill for an immediate objective.  What I appear to be focussing on isn’t a metric of your impact and I make sure everyone knows that. 

#### Vocabulary

On occasion and always in odd moments, I'm prone to using overly specific words and terms.
Not because I want to sound smart but because I'm regularly misunderstood and it's my inability to read the room which leads me to be cautious with words. 
I mostly speak casually and prefer this, you'll notice when my guard is down because I'm naturally nonchalant (there I go being specific!). 
So on occasion, I'll talk in a way that some find off-putting at first. When you reflect on the words chosen it might be appreciated that more detail was said than less. I'm always working on the balance between thoughtful words and comforting language.  
The more I learn how you react to me, the more I adjust my conversation style.  So appologies for any early hiccups.


## What gains and loses my trust

#### Sharing our blindspots builds trust
I’m naturally a gap filler and a room-maker. If I can trust that you’re sharing your hardest problems with me, I’ll perform to my best to solve for them.   
If you clearly demonstrate a passion and talent for an area, I’ll be grateful for your contributions and make sure I’m amplifying or giving you autonomy.

#### A critical attitude can both create trust or erode trust
Being generous enough to be in open disagreement earns my trust and greatly influences what actions I take for the better. If you make the effort to communicate concerns, I make the effort to hear, understand, and address them when I can.  
Some encounters may end in a ‘disagree and commit’ scenario for either party. But by doing this my respect for you will grow and I'll trust you more after any rigorous debate. 
Being a surprise detractor for extended periods by contrast, can lure me into a combative stance where I chase wartime success. It’s on us both to be comfortable being openly critical. I strive to ensure safety and reward disagreement as a valuable contribution. Like anyone, I detest dissent manufactured in secret without having the opportunity to be consulted.

#### I find trusting the second time is easier
You may have learned the *crumpled bit of paper* visual metaphor for trust.  Easy to do, impossible to completely undo. 
That's not entirely how I think of it. Hard lessons drive predictability and I value teachable moments on the way to long term trust. Failure is good and I look at patterns more than isolated incidents. Mistakes don't feel good but can be learned from.

#### Failure early and often but never the same
We're part of an inherently optimistic species and that optimism helps us take risks and evolve. 
If you become aware commitments are no longer realistic, I need to know. 
If that's a common theme I need help getting to the cause.

## My strengths

1. Seeing potential
2. Communicating Ideas 
3. Executing heuristics and aesthetics together 

I’m good at identifying where technology can solve a given problem. 
That’s broad but so is technology, and so are problems.  My strength is letting value lead the way and connecting vast moving pieces, talented collaborators, and winning buy-in by directly contributing.  
This extends specifically to prototyping, proof of concepts, pitches, and decisions regarding investment.

I’m well versed in communicating complex ideas visually and through storytelling. These skills help me share a vision with a wider audience and win customers or contributors.

I'm very capable at marrying heuristic needs to aesthetic opportunities in real deliverables.  
To me this is <a href="/posts/my-mantra/" target="_blabk">doing justice to good work</a>. 
* Solving big problems with fantastic experiences.
* Creating outstanding engagement with measurable outcomes.


## My growth areas


#### Accepting constraints that I believe can be changed



I try to appreciate opportunities by identifying what is at the outer limits of best efforts. I take ownership and am grateful for fixed variables, yet I'm still learning to be satisfied when the status quo is in-fact enough. 
You can always work with what you’ve got; 
I’m working on being satisfied with that.

#### Communicating flexibility
My conversation-style is a passionate one designed to attract, energise, and provoke reciprocity. 
The negative side of this, is that it's hard for me to not come across as a zealot at times. 
In the words of <a href="https://daringfireball.net" target="_blank">John Gruber</a>: "Strong ideas loosely held is the path to success". 
Like anyone else, I don't know what I don't know and when the facts change, I change my mind.   I'm taking more moments to make sure people around me know we're never too far down a path for me to be wrong despite projecting some very committed vocabulary.

## What I expect from people I manage

1. Openness & Trust
2. Taking ownership
3. Bringing your best at your worst

The African proverb "go fast, go alone - go far, go together" rings true when thinking about taking ownership.
I'm very comfortable giving autonomy in exchange for ownership. Having said that, maintaining higher level goals keeps us both accountable and on track for long term success.

We all have days where we aren't feeling it,  I expect you to be open and ask for help at those times so that I can support you. When this happens, I can augment your temporary weakness, not replace your core strengths. Doing our combined best is always my goal. 



## How I give and receive feedback


I  prefer giving and receiving a mixture of formal and informal feedback at a regular and quarterly cadence.  Direct feedback helps in real time, formal feedback builds tribal memory and can be invaluable when bringing new leadership on board.

As a manager I try to build a moat around your talent and make otherwise invisible contributions tangible and measurable assets to an organization. 

As a resource I thrive on lateral contribution and the resulting direct feedback.  However; I prefer major contributions be recognised formally so that I continue to be motivated and invest in those areas. 

