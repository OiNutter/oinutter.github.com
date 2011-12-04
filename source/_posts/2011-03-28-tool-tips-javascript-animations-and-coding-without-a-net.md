--- 
layout: post
title: Tool tips, javascript animations and coding without a net
tags: 
- animation
- Coding
- css3
- encapsulation
- Javascript
- javascript
- tool tips
status: publish
type: post
published: true
---
I've been working on overhauling the UI experience in the back end systems we use at work and decided that I wanted some tool tips to help tell users what things 
do without them having to ask us. The only decent tool tip library I've ever found was [Prototip](http://www.nickstakenburg.com/projects/prototip/) by Nick 
Stakenburg but I knew I wouldn't be able to get away with buying a license for it so I needed to create my own. After my experiences doing the emile.js version of 
zebedee I decided to give myself a bit of a challenge and go completely frameworkless to create a standalone widget.

First up was finding out how to do encapsulation in javascript so that I was only giving access to the methods that needed to be accessible from outside the class.
The way this is done is to return an object with the public methods defined in it, rather than doing return this. For purposes of scope I defined the methods 
before the return statement, then returned references to them. Like so:

{% gist 1173224 %}

Once I had that that figured out it was down to creating the various methods and setting up the event listeners. The main requirement was handling the 
positioning of the tool tip in relation to it's trigger element. As the position could either be fixed to a point on the trigger or follow the mouse, I ended up 
creating an object with either the element properties or the mouse coordinates and using that as the starting reference to perform the calculations from, then 
scanned the position option for one of the y position possibilities and set the top and did the same for the x position options. I later expanded this to have an 
optional element passed through which would be positioned instead of the tooltip, for use with the animations.

I spent a lot of time going through [prototype](http://prototypejs.org) and [zepto](http://zeptojs.com) to find out how to do the various things I needed to do 
without the frameworks and ended up stealing various little bits of code, like the user agent regular expressions from zepto so I could determine whether the 
browser was running webkit, I also tweaked this to check for gecko 2 as well. This was so I could use css animations where available for the transitions. When it 
came to dealing with the animation, [emile.js](http://github.com/madrobby/emile) ended up being my main source of reference, to the point that when I needed to 
expand my original animation function to be more flexible I ended up taking emile's animation code and a few of it's helpers and tweaking them for my own purposes.

The biggest challenge with doing the animation was the scale transition and positioning it, particularly the css animations. With the javascript animation it was 
easy to make the box appear to grow and shrink from it's trigger element, as I just needed to call the position method each time I adjusted the size. But with the 
css couldn't call anything on each iteration so I had to create a test element that was a clone of the tool tip, alter that, reposition it and get the end values, 
to then pass through to the animation function. In the end it worked out but I'd like to play around with it to see if I can get something less long winded. I also 
want to have a play to see if it's possible to make the text grow and shrink with the box, by using ems. Another interesting thing I discovered while working on the 
CSS transitions is that both Gecko 2 and Webkit have their own version of the transition end event, in Gecko 2 you can use transitionend but in webkit you need to 
call webkitTransitionEnd. Also this event will get called for each property you are animation, so in the case of the scale transition,where I was animating width,
height,left and top, the event was being called four times. Remember to check for this when writing your handlers.

I ended up namespacing the tool tip function inside a tipBox object, so I could add the scan method and keep them together. This means that while the calls are a 
bit longer, the functions are kept neat and secure, and shouldn't conflict with anything.

The scan method enables you to have a load of elements on a page (preferably a tags for semantic reasons) with a given class name that you can turn into tipBox 
triggers with one function call. All you need to do is pass the class name and the options you want to use to the method and it will scan the page and set up the 
tipBox for each one, using the title attribute to supply the text.

I found getting the initial stages of the widget working were a lot easier than I expected, which I take to be a good sign that my understanding and knowledge are
improving (either that or it's easier than I thought and I'm just being a numpty). The animations presented my biggest challenge and took as much time to work 
round as everything else did to create but were without a doubt the most rewarding part of it to complete. The whole coding without a net approach forced me to 
explore and learn more, and work out my own solutions to how to do things, which was great fun, and will hopefully result in an improvement in my javascript work 
from now on.

Code and demos are available on GitHub:

[tipBox](https://github.com/OiNutter/tipBox) | [Demos](http://oinutter.github.com/tipBox/)

