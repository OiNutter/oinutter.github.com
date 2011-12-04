--- 
layout: post
title: Obscura - Canvas, CoffeeScript and Micro Frameworks
tags: 
- Canvas
- Coding
- coffee-script
- coffeescript
- image manipulation
- Javascript
- javascript
- micro frameworks
status: publish
type: post
published: true
---
It's been a busy few months so I'm a bit behind on my posting so hopefully I can get back on schedule now. Once again I've been working on another javascript 
library, this time a canvas based image manipulation library called Obscura.

t all started with the arrival on the scene of [microjs.com](http://microjs.com) by [Thomas Fuchs](http://mir.aculo.us) and [Dustin Diaz](http://dustindiaz.com/). 
For those of you who haven't heard of it, [microjs.com](http://microjs.com) is an index of micro frameworks curated by Thomas and Dustin. The requirements for 
inclusion on the site are as follows:

* Must be written in javascript
* Must be less than 5k minified and gzipped
* Must be focused on one thing, rather than being a library of all trades
* Must have no dependencies

I liked the idea of this and was keen to get a listing on there as a step towards my goal of becoming more known in the community. Unfortunately none of my 
previous projects met the requirements, so if I wanted in I needed to come up with something else. I'd seen a tutorial in .Net magazine on image editing using 
javascript and canvas and decided I could port my existing PHP ImageHandler class to javascript using canvas as a base.

I also decided to use this as an oppurtunity to try out [CoffeeScript](http://jashkenas.github.com/coffee-script/) which I've been hearing a lot about. Once 
again, for those out of the loop, CoffeeScript is a lot like [Sass](http://sass-lang.com), which I've mentioned previously, but for Javascript. It's a language 
that compiles to javascript, so you can write your code in CoffeeScript's clearer, more verbose syntax, then compile it to normal working syntax.

I'm not normally a fan of stuff like this as I've never really seen the point, if you want to write javascript just learn javascript. However both Sass and 
CoffeeScript have convinced me that there are benefits to these things. In the case of CoffeeScript the automatic handling of things like scope and variable 
declaration make developing a lot easier and safer. The automatic wrapping in a function did cause me some confusion at first, which I'll discuss later, but does 
prevent any unnecessary pollution of the global scope and can be turned off with a compile option. I am however still adjusting to the braceless syntax which I'm 
not too keen on. I appreciate that it makes the code cleaner and smaller but as a php developer predominantly I've grown used to curly braces or at the very least 
some kind of ruby-esque closing statement.

I decided to stick with a small selection of basic image manipulation functions to start with. As I was using my existing PHP library as a starting point I had a 
ready supplied list of functions to use, with the basic logic all worked out. All I needed to do was work out how to write the functions in CoffeeScript and 
understand how to apply them with canvas. The latter proved to be the more challenging task for the most part. Particularly due to the inconsistencies in how the 
W3C's canvas spec is implemented in Gecko and Webkit. The main issue I came across was when working on the rotate function. I had been using the 
globalCompositeMethod copy to overwrite the existing canvas data which worked fine in Firefox but in Safari and Chrome "copy" actually overlays the new data onto 
the old, so the original, unrotated image was still visible. I ended up having to create an internal canvas object as a kind of staging area so all manipulations 
were performed on that before the finished article was sent to the target canvas.

By far my favourite CoffeeScript feature when writing this was the way it handles scope and the ability to reference the parent object easily when writing the 
code made life considerably easier, particularly as all the functions perform operations on internal objects. For any of you who haven't played with CoffeeScript 
yet or aren't familiar with the scope handling, it works like this:

{% gist 1084753 example.coffee %}

Which will compile to this

{% gist 1084753 compiled.js %}

Notice that CoffeeScript adds the __bind function which is then used to make sure the function executes in the object scope. Granted you can write this yourself 
but the syntax of the CoffeeScript is a lot simpler and clearer as to what is going on.

After a few weeks of playing around I got Obscura into a state I was happy with for a first version release. It passed all the tests for inclusion on 
[microjs.com](http://microjs.com), coming in at 1.5K compressed and gzipped, so I submitted it for inclusion and got it accepted. Obviously I was pretty pleased 
about this as it was one of the main reasons for writing the library in the first place and it was great that my work was considered good enough to be accepted 
onto the site but it didn't stop there. Later in the same week I got an email from [Softpedia](http://softpedia.com/) informing me that one of my projects had 
been added to their Scripts section. At first I had no idea what they were talking about as I hadn't submitted anything to Softpedia.Upon further investigation it 
would appear that they've been scanning other websites and finding libraries and widgets to add to their new Scripts download section. The project they'd added 
was Obscura so what I'm guessing has happened is they've been scanning through microjs.com and adding projects from there. It also appears they've been using 
those projects as starting points to find other projects as throughout the day I got more emails telling me they'd added other projects that are on my blog and 
github account. By the end of it 7 of my projects had been added; [Obscura](http://github.com/OiNutter/Obscura/), [Uncharted](http://github.com/OiNutter/uncharted/), 
[Zebedee](http://github.com/OiNutter/zebedee), [ermintrude](http://github.com/OiNutter/ermintrude), [Easel](http://github.com/OiNutter/Easel), 
[tipBox](http://github.com/OiNutter/tipBox) and [Delorean](http://github.com/OiNutter/delorean). For me this was a huge breakthrough in terms of what I've been 
trying to achieve this year as it's providing more avenues for people to find out about my work and hopefully use it and help improve it. It's also resulted in 
people starting to watch my GitHub repositories so hopefully I can build on this and keep raising my profile as the year goes on.

For now feel free to check out Obscura on GitHub for the code and demos

[Obscura](http://github.com/OiNutter/Obscura) | [Demos](http://oinutter.github.com/Obscura)
