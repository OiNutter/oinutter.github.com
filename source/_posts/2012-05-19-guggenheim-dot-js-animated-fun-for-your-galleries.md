---
layout: post
title: "Guggenheim.js - Animated fun for your galleries"
date: 2012-05-19 10:02
comments: true
tags:
- javascript
- css3
- animation
categories: 
- Javascript
---

I've been holding off on posting for a few months as I've had a couple of pretty cool projects that I wanted to get released so I could write about them. Unfortunately they're currently hitting a few snags so that's going to have to wait. I do however have something else that I cooked up based on an idea for something at work that I would like to share. So without further ado, may I introduce guggenheim.js.

Guggenheim.js is a framework agnostic plugin for your website that will create an animatable gallery. It currently supports animated filtering and reordering of the galler items, as well as the pre-requisite pagination.  It makes use of absolute positioning and hiding the overflow to position each item in the right row and column so that they remain in the correct order but still inside the same container. This enables me to animate the items to their new position when filtering or re-ordering, giving a really cool looking effect. 

The animation is using the same code I used on [tipBox](https://github.com/OiNutter/tipBox), but with improvements and fixes that I will eventually port back across. It will use CSS3 animations where available but fallback to Javascript when necessary. The javascript animation is using a modified embedded version of [emile](https://github.com/madrobby/emile) with [Kangax's fixes](https://github.com/kangax/emile/commit/bec75a4e684fd701efe1e91069900814a4b55062) to make it play nicely with opacity in IE8. This gives it a nice, lightweight engine for handling the animation.

I am intending to add functionality to auto generate pagination links, including numbered pagination, but for now you can easily add your own prev and next buttons and call the exposed methods of the guggenheim object.

Check out the Source Code and Examples over on GitHub for more information:

[Source Code](https://github.com/OiNutter/guggenheim.js) | [Examples](http://oinutter.github.com/guggenheim.js)
