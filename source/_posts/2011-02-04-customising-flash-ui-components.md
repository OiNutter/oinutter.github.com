--- 
layout: post
title: Customising Flash UI Components
tags: 
- Actionscript
- Coding
status: draft
type: post
published: false
meta: 
  _wp_jd_wp: ""
  _wp_jd_clig: ""
  _wp_jd_bitly: ""
  _jd_twitter: ""
  _jd_tweet_this: ""
  _wp_jd_yourls: ""
  _wp_jd_url: ""
  _wp_jd_target: ""
  _jd_wp_twitter: ""
  _jd_post_meta_fixed: "true"
  _edit_last: "1"
---
Typically, no sooner do I start writing a programming blog with an intention to focus on Javascript and I spend all month working in Flash.  That being said, this is a programming blog and I intended to talk about Actionscript stuff as well.  One of the biggest headaches I've had this month is dealing with Flash UI components, predominantly the form components.  In actuality I've had this headache every time I've had to deal with them, but now I feel like I'm starting to get a handle on the best way to deal with them.  So lets get into it.

###The Headache###
On the surface of things, Flash UI Components are a great thing.  They are little bits of prewritten functionality that you can just drop into your movie and, with out too much fiddling, have a working widget.  Which is fine, as long as you just want them to act and look how Adobe have designed them. If you don't, which is pretty likely if, like me, you are having to build your forms in flash in the first place, then they are a nightmare.

Making them look different is, on the surface of things, relatively easy.  You just go into the component and edit the skins.  The problem with this is that it doesn't change the component's avatar, so trying to lay components out is something of  a guessing game, seeing as they look nothing like what they are supposed to.

###The Solution###
While not a perfect solution, the best way I found to deal with it was to extend the components and overwrite the parts I needed.   To demonstrate I'll take you through extending a Button and a TickBox.

1. First create a blank movie clip.  For this we'll be creating a rounded button, so, to be totally original, we'll name our movie clip RoundedButton. Save the whole movie into a project folder. This just gives us somewhere organsied to work from.

2. Create a second keyframe, then create 2 layers.  Name one skins and one avatar.  In the second keyframe, on the skins layer, draw a rounded rectangle.

<a href="http://www.oinutter.co.uk/wp-content/uploads/2011/02/Image1.jpg"><img class="aligncenter size-medium wp-image-46" title="Image1" src="http://www.oinutter.co.uk/wp-content/uploads/2011/02/Image1-300x129.jpg" alt="Step 2" width="300" height="129" /></a>

3. Convert this rectangle to a MovieClip called RoundedButton_upSkin.

4. For now we'll just create the 3 basic states we want for the button so duplicate the MovieClip in the library twice and rename the copies to RoundedButton_downSkin and RoundedButton_overSkin.

5. Change the rectangle in the over skin to a different colour, then change the rectangle in the down skin to yet another colour and make is slightly smaller.  Drag these onto the stage with the over skin.

<a href="http://www.oinutter.co.uk/wp-content/uploads/2011/02/Image2.jpg"><img class="aligncenter size-medium wp-image-48" title="Image2" src="http://www.oinutter.co.uk/wp-content/uploads/2011/02/Image2-300x160.jpg" alt="Step 5" width="300" height="160" /></a>6. Copy the up skin to the first keyframe on the avatar layer.

7. You've now got your basic movie clip set up.  Now to turn it into a component.

8. Create a folder under your project src directory called components, then create a second directory under that called RoundedButton

9. Create a new file in this directory with your preferred ActionScript editor called RoundedButton.as.  Create a class called RoundedButton that inherits from the default button component.

[as3]
package components.RoundedButton {

import fl.controls.Button;

public class RoundedButton extends Button{

public function RoundedButton() {

}

}

}
[/as3]

11)  In your flash file, right click on the RoundedButton MovieClip in the library and select Export SWF. Export the movie to the same folder as your RoundedButton.as file as RoundedButton.swf.

12) Once again right click the Movie Clip, and this time select Component Definition
