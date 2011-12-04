--- 
layout: post
title: Zebedee - v0.2 - A whole lot of frameworks
tags: 
- accordion
- animation
- emile
- framework
- javascript
- scriptaculous
- scripty2
- zebedee
- zepto
status: publish
type: post
published: true
---
Ok, there's only 3 more but still, it sounds more exciting. Yes, zebedee has made it to version 0.2, my first actual version increment on any of my projects, I 
feel quite proud! So what's new in version 0.2? Well the main additions are the versions for [Scriptaculous](http://script.aculo.us), 
[Scripty2](http://scripty2.com) and [emile.js](https://github.com/madrobby/emile) Check out the readme for details on what files are needed and how to use them.  
In addition there are also a few bug tweaks, minor reworking of the zepto version to cope with a major restructuring of zepto and the addition of a default panel 
option.

For the large part I've kept the code the same on the new versions, the main changes being updating the open and close methods to use each individual library.  
I've also removed functions that were duplications of methods available now available to me in Prototype for the Scriptaculous and Scripty 2 versions.  I did 
however keep my own object merge function as it merges more recursively than Prototypes version.  Emile however was much more of a challenge as it is solely an 
animation framework and therefore contains no helper methods whatsoever.  Cue a trip deep into zepto's code and the 
[Mozilla Javascript Docs](https://developer.mozilla.org/en-US/docs) to find out how the frameworks do things. I ended up adding a few helper methods to deal with 
manipulating the classnames, just to make life easier.

I've also added in the facility for the Scripty 2 version to use Scripty 2's ability to use css transitions where available. This is only available on linear and 
sinusoidal transitions at the moment but the library will fallback to javascript for the unavailable transitions. In the case of emile the transition calculation 
functions have to be provided as an option so I've added a zebedeeTransition object with a selection of functions.  The default object just includes the linear 
and sinusoidal transitions but by including the zeb-transitions.js file you can get access to all the transition types of Scripty 2.  The calculations are taken 
from Scripty 2's included calculations that are based on Robert Penner's original AS2 [easing equations](http://www.robertpenner.com/easing/).

Coming up in version 0.3 will be a jQuery version, callbacks for when the panel opens and closes, at both the start and finish of the animation, and the option to 
keep one panel open at all times.

[Zebedee](https://github.com/OiNutter/zebedee)