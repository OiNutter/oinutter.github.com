--- 
layout: post
title: Zebedee - A Multi Framework Accordion Widget
categories:
- Javascript
tags: 
- accordion
- css3
- javascript
- mobile
- webkit
- widget
- zepto
status: publish
type: post
published: true
---

Zebedee is an accordion widget for multiple frameworks. At the moment it is only at V0.1, which only supports [zepto.js](http://zeptojs.com), but I will be adding 
support for various different animation frameworks as I have time. I wanted to play around with Zepto, [Thomas Fuchs](http://mir.aculo.us)\' new mobile javascript 
framework and decided it would be fun to do an accordion widget to see if I could use the CSS3 transitions to animate the opening and closing of the accordion 
sections.

It was good fun having to go back to basics on it as I was used to having Prototype and Class.Create() to work with when creating new objects. Thankfully zepto 
provided a few good utility functions to keep my code neat and simple. The jQuery like chaining also came in handy in that regard.

I've purposefully kept the functionality simple, as I don't really think it needs to be all singing, all dancing! At the moment it supports vertical and 
horizontal accordions and I will probably be adding the ability to set the the actual trigger event for the accordion to be bound to a child of the header object. 
Also the duration, transition type and trigger event are all configurable, as well as the class names assigned to the various components.

I should hopefully be adding support for Scriptaculous in the next month or so, and Scripty 2 should follow soon after that, so watch this space. In the meantime 
checkout the project page at the link below for more information and links to the GitHub source. I'll also be popping up some demo pages when I get the chance.

[Zebedee](https://github.com/OiNutter/zebedee) | [Demos](http://oinutter.github.com/zebedee)
