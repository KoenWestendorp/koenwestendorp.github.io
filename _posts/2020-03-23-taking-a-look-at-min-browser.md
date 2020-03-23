---
layout: post
title:  "Taking a look at the Min browser again"
date:   2020-03-23 10:03:42
published: true
---

Dear me, and anyone interested in reading about this,\
Over the past week (Corona week 0) I have had the chance to start fresh with my new MacBook Pro. Well, new... It is the early 2015 Retina 13 inch model, and I was able to get it for a really good price using money I made over the summer. (For anyone interested: 2.9GHz Dual-Core i5 with 16GB memory). Unfortunately, the context of this replacement is my 2011 Air finally breaking down into a hardly usable state after 7 years of featherlight and honourable service. 

Still, I've been having a fantastic time starting with a clean slate. (Actually thoroughly enjoying macOS Catalina, which I did not think would be the case.) Setting up [iTerm](https://iterm2.com/) as my terminal, installing some of my daily driver terminal applications using [HomeBrew](https://brew.sh/). Also, I am starting to get to know [_zshell_](https://en.wikipedia.org/wiki/Z_shell), which I plan sticking with for a while in favour of [_fish shell_](https://fishshell.com), but that is an article for another time.

{% include img.html url='/assets/img/setup-march-2020.jpeg.png' caption='My current setup.' %}

Interestingly I have noticed that Safari has gotten quite a bit faster on Catalina compared to High Sierra on my Air, also when compensating for processor speed (of course). This is the case for very light static pages, but also for web apps and sites like the ever performance-hungry Reddit. I have found that it eats away quite a bit less RAM compared to the High Sierra build, and the performance is improved by the truly wonderful 16GB of RAM on this new Mac, too.

This experience of featherlight and lightning fast browsing on Safari, made me think of a very obscure little browser I came across years ago: [Min](https://minbrowser.github.io/). To the best of my recollection, I came across this project on [HackerNews](https://news.ycombinator.com/), and I had used it of and on over 2017/2018. 

## The Min browser
Min takes a different approach to web browsing. It has been designed with power users as its central audience, leaving out and abstracting away almost all GUI buttons and allowing its users to rely solely on keyboard shortcuts for navigating the minimal UI it has. The focus is on the site, exactly where it belongs if you ask me. 

{% include img.html url='/assets/img/Min-floating.png' caption='Isn't it just really pretty‽' %}

Now, this makes it the case that there is a little bit of a learning curve to Min, but for me it was not bad at all, since I use Safari by keyboard shortcut control almost entirely, and the shortcuts are quite similar.

Next: the all important pixel measurements. (Notice how I used 'measurements' correctly here, as opposed to the Idun board in their recent newsletter.)  Safari's top bar comes in at 64pt with tabs and a respectable 38pt with only one tab. 
Compare that to the Min title bar, which comes in at a 36pt height, _with tabs_! Can you believe that!?!? This makes Safari look practically unusable, since this means at least a 53.4% decrease in productivity based on top bar height alone!!

(It must be noted that I use the screen scaling setting between the default and smallest, where most people tend to use it on Retina/UHD devices.)

{% include img.html url='/assets/img/top-bar-height-comparison.png' caption='Because screen space efficiency and productivity are basically the same ;)' %}

Well, that is not that important, but one of the things I liked most about Min-and still do love-is its minimal approach to UI. When you spend a large part of your day browsing, researching and reading on the interwebs, small things become important. This is all not to detract from my love for Safari's UI, which is excellent in my opinion, and which I also love to the bone. 

But that is in my experience-years prior and in the past days-the time to shine for Min. _Browsing_. I feel like it starts to become a clogged up Electron app when using it to do heavier tasks. And incidentally, Min _is_ and Electron app.

## Electron apps
[Electron](https://www.electronjs.org) is an open-source framework for app development. It allows for the use of web technologies like CSS, HTML and JavaScript in the creation of "native" apps. Native in quotes there, because they are able to run natively on a range of platforms, yet they still are borderless (also known as chromeless) browser windows. 
But it is the ability to build one app for a range of different platforms, that appeals to companies and developers. You can build one app, and publish them on Windows, Linux, macOS (if Apple doesn't reject them due to privacy concerns) and Android. This saves an incredible amount of time and money, because instead of a few different teams that work on all of the different platforms, you only need one for all of them. And in reality, this means that the app only would appear on one platform, not almost all of them.

Yet it is the cross-platform nature of Electron apps that make them suck, I would say. Because you are making one app to serve all platforms, you don't optimise for any of them! Also, you are stuck with whatever the people behind the framework want to do with it. If one error is made in the framework, suddenly all of your apps could have a gaping security hole. 

Electron apps are at their core browsers. They run on web technologies. Web technologies are not known to create particularly efficient and performant products. Basically, the moment JavaScript gets involved, things turn into a RAM and CPU dumpster fire. The result is a slow app, that just doesn't _feel_ native. Or rather, it used to be like that...

Over the past few years, the people behind Electron (it is maintained by GitHub, so that actually is quite reassuring) have been working on greatly improving performance and efficiency of their framework, which instantly trickles down into the products that are built on it, as a consequence. And of course I should mention that Electron apps are not the only cross-platform, web powered solutions. React Native is a very popular option as well. 

Also, many Electron apps already exist as web apps, and honestly, feel much more at home in their browser home, than as an actual app. So, for your sanity and mine, please just use your browser to use Slack, WhatsApp, Discord, Gmail _et cetera_...

{% include img.html url='/assets/img/slack-bad-native-good.jpeg' caption='sLaCk bAd nAtIvE GoOd' %}

For me an app being based on Electron or a similar framework actually is reason not to try something at all. To me, this is where Min as a browser would break down, normally. But, I do not think it is fair for me, to exclusively see Min in this light. This is because Min is a browser. Min is a browser, and so are all Electron apps. Normally this is the problem I have with them, but since Min is in its function a browser, this might not be such a bad think at all. 

My concerns for battery life, memory usage, general performance and proneness to bugs still stand, though, but I am giving Min a chance. By which I mean that I will be stress testing it over the coming weeks. I am going to try to devise a protocol to consistently test performance across a few browsers, and on a few different platforms (might do a little Raspberry Pi test, too.) 

{% include img.html url='/assets/img/Safari-floating.png' caption='Trusty Safari.' %}

## Conclusion?
I like Min, the idea of Min. Its power-user centric philosophy of design, the fact it uses a count-from-zero approach which warms my heart, and also how it looks, [to be Frank](&&&). But the reason I have not continued using this cute browser from the point I discovered it, is because of my consciousness of the potential performance downsides it might bring. At the time I never thoroughly researched that feeling. Also, I feel like its performance might have improved quite a bit since 2018, the project is [actively maintained on GitHub](https://github.com/minbrowser/min). So let's do it now.

Hopefully I am able to get some consistent tests of its performance, now in 2020. If that is the case, I will publish them here of course :.)

Well, goodbye and please cough into your elbow. \
Sent from my ~~iPhone~~ Min browser.





