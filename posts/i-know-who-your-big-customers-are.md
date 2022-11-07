---
title: How I know when you win a big customer
description: Simple insights that can help your growth hacking. 
date: 2022-11-06
tags:
  - business intelligence
  - marketing
  - sales
layout: layouts/post.njk

---


Competitive intelligence is a big deal, it can turn a speculative gamble into a sure-thing.  With the right insight: we fish where the fish are, can plan to win, and campaign to eat the market from the top down.  
If you're new in the game without a killer funnel or flywheel (ugh buzzword fatigue)  it can be easier to churn a dissatisfied customer already spending with your competitor than it is to find and teach a new prospect what you are all about.

### So what can SaaS do when facing a glut of competitors?

Firstly, celebrate, market validation is the greatest gift.
Secondly, get a lay of the land - know where you stand.

There are commercial platforms that offer these kinds of tools - I'm not going to link them because I've never tried them.  But if you're happy to roll up your sleeves and run a few command line scripts, this is for you.

In  this article, I'll cover three techniques 

1. Search trigger
2. Name enumeration
3. Door knocking 

This is so that you can 
- Identify large accounts at other vendors.
- Track when they sign up and churn
- Learn how fast competitors are growing

You can do plenty of this on your own workstation ad-hoc, or set up a VPS to run constant reports over time.


So firstly let me disclose the important points:
- This is not meant to encourage any illegal or unethical activity
- You are responsible for how you leverage the learnings of this article. 
- I am not a lawyer or from the infosec industry; this does not constitute professional advice. 
- You will use your own competitor and prospect names

## What you will need

1. A list of your competitor domains\
    (any/all domains they use to host their customers if they use multiple for different storefronts or products)

2. A list of target accounts\
    (say the top 10 thousand global companies by market cap or something as simple as the Forbes 500, or even just the ~ 100 businesses you are targeting right now) - Gather this yourself, there are commercial services offering solutions built on these lists but this is a DIY article.  Easy enough to get a hold of.

Okay with that out of the way, we can start with the obvious.

# Search

SaaS companies love and need SEO, many encourage partial/full public usage of their platforms wherever possible.  Think github, codepen, even my employer Brandfolder.

Their user activity might be mostly private, but it's in the vendors best interest to have as many ```vendorname.com/yourcompany``` instances as possible.

So scripting a recurring search with tools like googler (<https://github.com/jarun/googler>) like ```site:competitordomain.com prospectName``` is the easiest way of learning if an organisation has begun using a competitor.\
Seems simple but this is frequently overlooked and you can skip the awkward "who are you working with" question in discovery calls.

# Domain Enumeration

This one is similar but different to search in that even fully closed platforms often offer up whitelabelling subdomains as a feature to their accounts. ```Companyname.competitordomain```

For this we can use services like <a href="https://github.com/OWASP/Amass/">Amass</a> and <a href="https://github.com/aboul3la/Sublist3r">sublist3r</a> .

These tools will use a variety of techniques and do their best to surface all the custom subdomains  - giving you an idea of who is a customer and who is not.

While not giving you target company lists, I'm not a monster. Here's a handy ignore list to clean up the results you get. <https://gist.github.com/andyfitz/227921862fb81a7843a05479255711a9>

# SSO Door knocking

I saved the best till last.  Lots of private-productivity SaaS environments neither subdomain nor subpath their customers.\
But like death and taxes, one other thing is certain:  Enterprise accounts demand SSO/IDP integration. So if they are a small team logging in with username/password - you may never know, but if they are a big customer, you'll be able to confirm relatively easily.

I'm not even sure if this technique actually called something else - but I've called it door knocking because you're simply

1\. Visiting a website's login form

2\. Knocking it with a targeted domain's email.

2\. Checking the response sizes to confirm / disprove the account

Over time, this helps you track acquisition and churn by large enterprise accounts.

I'm not going to share how this is automated technically other than to say it involves rotating VPS proxies,  puppeteer, and form submission which is dead simple.\
Here's a handy tutorial from Scrapingbeee that doesn't require use of their service <https://www.scrapingbee.com/blog/submit-form-puppeteer/>.\
After reading that, you'll get the idea. automating requires you to set up a method for each competitor you want to track.

Say you try knocking their loginform with ```giuseppe@companyname.com```.

If you get the same size response as ```giuseppe@domaindoesnotexist.com``` (or no response), then you can validate that companyname is either a small-time customer on a team plan or not a customer at all because they haven't implemented SSO.

Again, you can do this manually by simply visiting your competitor website.\
Selecting the email option, typing in ```anyname@yourprospectdomain.com``` and seeing if you hit an SSO gate. Handy right ?

So that's it for now. 

I hope this was insightful.

P.S I don't run any analytics on my blog so if you liked this article - tell me @andyfitz via most major social media platforms.