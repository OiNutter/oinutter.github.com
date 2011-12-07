--- 
layout: post
title: Python Wrangling - Getting To Know The Beast
categories:
- Python
tags: 
- file
- gui
- pyqt4
- python
- renaming
status: publish
type: post
published: true
---
Okay, so this month I finally got chance to delve into Python. I'm using version 3.1, as obviously there's no point learning something thats going to be obsolete 
fairly soon, although this did make finding examples and stuff harder as the majority of stuff I found was for Python 2.

While I know python is a popular, and very capable, web programming language, I'm not really interested in that side of it. As far as I'm concerned I've got PHP 
which I use for regular development, and am pretty competent with, and Ruby on Rails, which I'm starting to try and get my head round, I neither need nor want yet 
another contender vying for position as my chosen tool when it comes to developing for the web. What I am very interested in python for, is desktop apps. From 
what I've heard python is a pretty good cross platform language with good tie-ins to the operating system and file structure. It also looks a hell of a lot 
simpler than C++, which I have tried to master on a few occasions and only ever succeeded in achieving basic competency with.

Now if you've seen any of my other posts you'll know that I tend to do a lot of work with Javascript, and also know Actionscript, so you may be wondering why I 
don't just use Air for building desktop apps. I've used Air before to build small desktop widgets using Actionscript, and will undoubtedly at some point end up 
playing around with it a bit more, but for users to run Air apps they're required to download the Air runtime, and the last time I looked the Linux version was a 
bit behind. What I'm hoping to get with Python is something I can write once, maybe with some os specific tweaks, and compile to a valid executable/installer for 
any system.

So onto my first impressions. For someone that is used to languages like PHP, Javascript and Actionscript, Python is something of a shock to the system. The lack 
of curly braces to enclose functions and statements was something I was starting to come to terms with from Ruby, but the lack of any form of closing statement 
made reading through the code a somewhat strange experience. My learning project is a file renaming utility so I found the os functions, particularly os.rename() 
really useful. I started off just building the app as a command line script, then once I'd got that basic renaming functionality figured out, (not really that 
difficult when it's just a call to one built in function), I started looking into adding a gui.

I ended up going with PyQT4, mainly because it was the only free, cross browser GUI framework that worked with Python 3. The hardest part about getting it all 
working was finding out how to actually create the window and use the ui. I'm using the following code:

{% gist 1173233%}

Where main.ui is my layout xml file. One of the things I liked about PyQT was that it came with a GUI designer utility which lets me just layout the gui as I 
wanted it and save it to xml. Makes building the layout much easier. At the moment I've not really done much more than set up a basic gui with ultra simple file 
renaming (you select a file, type a new name and hit the big rename button) but I'm intending to add batch renaming with various renaming actions such as regular 
expressions, substringing, extension changing and more.
  
The main challenge at the moment is understanding how to use PyQt as I'm afraid the documentation isn't particularly novice friendly, being more of a reference 
library. Some examples would be handy, especially as I struggled to find anything on google. I think when I'm a bit more comfortable with things I'll post some 
examples/tutorials. I'll also write a bit more about my python experiences as I get to spend more time with it.