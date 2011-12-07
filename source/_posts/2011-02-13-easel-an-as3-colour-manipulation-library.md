--- 
layout: post
title: Easel - An AS3 colour manipulation library
categories:
- Actionscript
tags: 
- Actionscript
- AS3
- color
- colour
- HSL
- RGB
- Sass
status: publish
type: post
published: true
---

Well my post for this month was going to be a tutorial on customising Flash UI components, but unfortunately doing it properly is going to take more time than I 
have available to me at the moment so I'm just going to keep working on that in the background and will post it when it's ready.  In the meantime I'm going to 
put up more information about some of my Open Source projects and hopefully get them better known, which in turns should, I hope, accomplish one of the aims of 
this blog.  Getting people to help improve my stuff and, by proxy, improving my skills and knowledge.

So first up, purely by virtue of being my most recent, is Easel, a colour (I'm english, so yes it is spelt right!) manipulation library for Actionscript 3.  Easel 
came about from a need to take a randomly generated colour and get colours that would work well with it for dynamically generated objects in a recent project at 
work.  At first I just managed to find the [Tint library by RevokeLabs](http://lab.revoke.ca/2009/04/as3-color-functions/) which provided me with a darken 
function which did the trick for me.  However I then needed more, so I managed to find an algorithm to calculate the complementary colour on a forum somewhere, 
which I'm afraid I can't remember, but have subsequently replaced so I don't feel too bad about not crediting it.  From there I had the idea of replicating the 
colour manipulation functions of [Sass]("http://sass-lang.com/"), which I'd read about in a recent .Net tutorial, but hadn't had a chance to play around with 
(I have now and will no doubt be writing more about this down the line, watch this space!).

I was struggling to find the algorithms to accomplish what I needed in AS3 so I ended up pulling the source for Sass from GitHub and wading through that to find 
what I needed.  I then proceeded to rewrite the functions to AS3 which involved rewriting the original manipulation functions from the Tint library as they relied 
on manipulating the RGB values whereas Sass was working with the HSL.  I did however keep the getHex and getRGB functions as there seemed to be no real difference 
in them.  The upside to this approach was that I learnt a bit about colour manipulations, and got more experience with Ruby code, always a good thing!

Please check out the link below or on the right for the project page which contains links to the GitHub source and the Demo.

[Easel](https://github.com/OiNutter/Easel)
