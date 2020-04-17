---
layout: post
title:  "Arkyve, a new thing I have been working on"
date:   2020-04-17 22:33:19+0100
published: true
---

{% include img.html url='/assets/img/arkyve-hero.png' caption='' %}

Over the past two weeks, I have been working on a project I have named 'Arkyve', for the time being. I am quite aware that this name is one '-ly' suffix away from being a 2016 startup, but I guess it's fine and I can always change it later, let's just agree it's a working title. 
As somebody who grew up with YouTube videos as one of the central comedic and cultural wells, I often find myself just talking about and referencing videos with friends. Whole afternoons, bus rides and lectures can be spent just recalling videos from the likes of KUD or just creating an IRL 'Vines that butter my bloody egg roll and have repeatedly saved me from the brink of getting work done' compilation, right there on the street. And if you happen do be able to connect to this newfangled thing called 'the inter webs' you might even be able to actually look up the videos, to see to what extent you were misquoting it, to have it reflect your internal comedic taste. 

Considering these videos are often not more than 5 years old, and YouTube is still a stable ~~monopoly-adjacent~~ platform, they are all still there. The biggest trouble you might run into (for the more popular ones at least), is misremembering the video's title, and having to search by a description of what happens in it. If a video is popular, you can be 99% certain it will be on YouTube for the rest of its days, due to re-uploads, but that is exactly what concerns me. 

{% include img.html url='/assets/img/arkyve-figma-1.png' caption='A look into the Figma file.' %}

I do not know what the future will hold for us, nor do I claim that I do. But I think it can be argued that it is not certain whether all of these comedic snippets will still be there, when I want to tell my kids what comedy was all about bAcK iN mY dAy. At the risk of sounding like an anarchist: YouTube is not your friend, they are a company, and they are here to make money. So when Google at one point decides to pull the plug on this *currently* beloved product, where will all of its ... years of footage go? 

For that matter, where will all the wonderful places on the internet be in 10 or 20 years. Seriously, you should ask yourself that question. 

Honestly, I realise that I sound like a fucking hoarder. (A [data hoarder](https://reddit.com/r/datahoarders), one might even say. This is a phenomenal subreddit!) But this question really bothers me, and luckily I am not the only one. The most well-known project trying to conserve and archive the internet is [archive.org](https://archive.org), the people behind the [WayBack Machine](https://archive.org/web/) among many other truly inspiring archival projects.  And this is what my Arkyve project is about: a site my friends can submit cool videos to, so I can archive them for the future.

## The for the whom-whomst
For the time being, I want this to be a small-scale project. This is a service I want for myself, and for my friends, and I have no ambitions beside that. The most likely pathway of submission will be using an invite system.

## The how to submit
In the end, I think I will end up with a flow that goes something like this: 
- the user pastes a YouTube URL or video ID into the big text field at the top of the homescreen.

Yeah, that's it. I believe the experience should be as frictionless as possible. Though this system will be terribly, terribly susceptible to malicious minds, I think it will be fine, because this site will, most likely, only be a word-of-mouth thing. 

I am also working on implementing a way to submit a list of videos or a YouTube playlist. 

## Request a video file
All of this would be pretty useless if there was not a robust system in place for requesting a video that has been deleted from YouTube. So I decided on a high-tech 'hit me up with an email and I will send it to you asap' system. Suck on that, postal pigeons!!!

## The processing of a submission
Once a video has been submitted, the input will first be validated, to ensure it is actually a YouTube URL or video ID. Once the validity is ensured, the further parameters will be inferred from the video ID, by calling YouTube's API. This will give the title, channel, duration, upload date and other properties. All of this information will make up the video's object, which will be stored inside of a database, where it will await the downloading. 

Every few weeks, I will take a look at the newly submitted entries, and will decide whether it is safe to download them all and, if necessary, filter them for malicious entries. This will probably be a manual process, because this ensures that no mishaps can occur with a hundred 10 hour long videos being downloaded onto a harddrive, because that is not what Arkyve is intended for. 

The filtered list of URLs will then be downloaded at a manageable resolution like 720p, onto a drive for safe-keeping. Pretty low, tech and old skool right? Well that is ~~because I am not bothering to create a more robust system and not in the possession of endless amounts off dolla dolla bills~~ because I like it better that way.

## The design
{% include img.html url='/assets/img/arkyve-screen-1.png' caption='Home page progress.' %}

In its current iteration the site is based around a yellow primary color, typeset in Helvetica Neue (or its fallbacks). The different functional sections like 'Submit a video' and 'Recently submitted' are divided by big, bold headings and the submission interface consists of large, radiant elements which are implemented to be nice and `tab`-able, for the pro users (me). This is achieved using robust and visible `:focus` pseudo-class styling, which I like more than necessary.

{% include img.html url='/assets/img/arkyve-figma-2.png' caption='' %}

Also, I subconsciously designed it to look early like [Vox.com](https://vox.com/), which I only realised after I settled on the design. But this does not bother be at all, because Vox is one of my favourite websites on so many levels, 'bro'.

## The tech
{% include img.html url='/assets/img/arkyve-code-2.png' caption='Writing a server application in Xcode?!' %}

I am using the *Vapor* server-side *Swift* framework, so that's really cool I think. Vapor compiles into an extremely fast, light-weight, and reliable binary that can run on a *Debian*-based server. 
For the styling I am using *Sass*, which I parse into the assets folder using a cli converter. 
The database I plan on using is *SQLite* for no particular reason, I honestly don't know that much about databases and their merits and my demands are really quite minute, so it probably doesn't matter a lot.

{% include img.html url='/assets/img/arkyve-code-1.png' caption='Honestly, I really like writing CSS! (When it is SCSS at least.)' %}

Currently, it is not on my GitHub page, because I am still trying to make a bare-bones, working prototype. After I have achieved that, I will rewrite it with the power of hindsight and create the actual production implementation.

## In summary
Okay, cool thing I am working on etc. 

If this thing peaks your interest, please, please [email](/contact) me, so we can work on this together :) 

Met vriendelijke 'de moeder', 
Koen