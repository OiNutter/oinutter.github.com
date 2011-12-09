--- 
layout: post
title: Objective-C and iOS Development - Taking My First Steps
categories:
- Objective-C
- iOS
tags: 
- applications
- iOS
- iPad
- iPhone
- objective-c
- xCode
status: publish
type: post
published: true
---
I recently managed to get myself a Macbook, which besides finally giving me a home computer that can cope with what I'm throwing at it, has finally enabled me to start looking at iOS development. I've briefly 
played with Android development but what little Java skills I picked up at university and was able to remember after all this time weren't quite up to the task. So you'd think that tackling developing in 
Objective-C, a language I've never used, would be an even bigger challenge right? Well thankfully I managed to find some help, primarily from iTunes U. If anyone hasn't checked this out yet I'd highly recommend 
it, there are a load of free to download lectures from several of the big universities on there (primarily US from what I could see but there were some others). The course I've been following is Stanford's 
[cs193p](http://itunes.apple.com/us/podcast/cs193p-student-final-projects/id395605774?i=90218598 "iTunes U Download for C193p") course on iOS application development by Paul Hegarty. If you can get past Paul's 
slightly eccentric seeming nature, anyone wanting to get into iOS development would do well to check this out. I'm only a few lectures in at the moment but the course has already succeeded in helping me finally 
get my head around MVC.

So what do I think of Objective-C? Well I'm still in my early stages of playing with the language so this is really just a first impression but I think I'm going to like developing in it, and I certainly think 
I'm going to find it easier and more enjoyable than I ever did Java. It's very different from most of the languages I've ever learned and certainly a huge change from the languages I use on a daily basis (PHP 
and Javascript). One of the first things I've noticed is how verbose it is. There is very much a convention of the code reading like plain english, with things such as long variable names and methods. The way 
methods are defined is one of the primary examples I would give of this verbosity, and of the difference of Objective-C to languages I'm used to. The following examples show a comparison of how methods are 
defined in Actionscript 3 (I know, I know, but it's the only langauge I know well enough to write comparison code in that defines the return and argument types) and Objective-C.

{% gist 1171831 as3style.as %}

{% gist 1171831 objcstyle.m %}

As you can see the single argument methods are pretty straight forward, return type at the start, followed by the method name, then the argument and it's type listed after a semi colon (felt weird having no 
brackets). From what I've seen there doesn't seem to be any indication of public or private with the method definitions. What seems to happen is that you just don't define methods you want to be private in your 
header file, which defines the class' public api. The - at the start of the definition indicates that this is an instance method, a + indicates a static method. The primary difference in the way methods are 
defined is when it comes to methods with multiple arguments, where you see this splitting of the method name. The only real purpose I can see of this is that if you write your method names and variables properly 
it helps the code read like plain english.

As for developing in XCode, so far I'm liking it. The built-in Interface Builder Gui tools are really helpful, especially when it comes to linking the controller to your views.  It's taking me a little while to 
find everything in the property inspectors, possibly because what I'm looking for isn't available for customisation but you never know. The in-line error and warning highlighting is really helpful as it makes it 
much easier to see where you've missed that semi-colon or curly brace. I think I'm really going to like the property synthesization (more on that once I've gone more in-depth with it) that allows the compiler to 
auto generate methods for you.

Developing for iOS is going to present me with some new challenges that I wouldn't normally have to contend with such as Memory Management, which is going to take some getting used to, but that's half the fun. 
So hopefully before too long I'll be posting about my new app that you can all go and buy and make me millions, (although based on how many readers I probably have  I might be lucky to make a pound!).  I promise 
it won't be a new fart app!