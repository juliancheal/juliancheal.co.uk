---
layout: post
title: How to make a robot dance
---

# Introduction
Dancing robots are wonderful things, they go from being inanimate objects to ones with a personality. Now depending on the music you choose, the type of dancing the robot does to that music, will in my mind at least change the robots personality.

However it's a widely know fact[1], that most robots actually have a favourite genre of music; which is Dubstep. They really love it, and as the wordsmith Taylor Swift once said;

"Getting down to this sick beat"[2]

Beat is an important word in that paragraph, but we'll leave that for another day. TODO: Maybe write about beat controlled robots in a another post.

# Recipe
To get a robot to dance one requires a certain je ne sais quoi. Once you find out what it is, you'll then need the following ingredients.

## Ingredients
* A robot to dance[3]
* Some codes[4]
* A Playstation 2 Dancemat[5]
* A Sick Beat

## Method
* Write code to make drone fly and respond to dancemat controls.
* Play some kick-ass tunes.
* Profit.
Or skip to one I prepared earlier.<link to Here's one I prepared earlier section>

### Here's one I prepared earlier
Point your git client de jour at `github.com/juliancheal/dancingrobots.git`. Once cloned `cd` into the folder.
Running `bundle install` should hopefully get you set up with all the dependencies[6]
While that's bundle installing, plug in your `dancemat` to your computers `usb`.[7]

Now connect your computer to your drone's wifi hotspot. Hopefully you called your drone something rad like, `Sherlock Drone` or `Amilea Droneheart`.

Fire up those engines! Well run `ruby zomg_dancing_robot.rb`

Fingers crossed nothing dramatic should have happened yet. I assume your `terminal` is telling you to `Get Ready to Dance`? Yes? Good.

Now press the `start` button with your foot. (Did I mention it's probably best to do this either barefoot or in socks?).
*wurrrr* goes the drone's engines as it majestically rises into the air. *Womp* *Womp* goes your song. Now let the fun begin.

You'll notice I didn't tell you the controls until the drone was already flying, and if you really are literally doing one step at a time, you'll have fun reading the controls while dancing!
It's pretty simples really.

* Start - Starts the music and the drone takes off
* Select - Stops the music and the drone lands, gracefully one hopes
* Left - Drone goes left
* Right - Drone goes right
* Up - Drone goes, wait for it… …forward. It goes forward, you thought I was going to say up. :troll:
* Down - Drone goes backwards
* <left-top diagonal> - Drone goes up
* <Right-top diagonal> - Drone goes up down.
* Pressing both `left` and `right` at the same time makes the drone `flip` ZOMG right?!

If at any point your drone crashes, assuming you placed it flat on the ground after it's near-fatal incident, pressing `start` again will get the drone to take off.[8]

# Epilogue
There we have it. Nothing too it really. The fun part though is seeing what else you can make dance, or control with a dancemat[9].

[1] A fact in the sense that, if it's on the internet it must be true.

[2] <Insert song details - also correct quote>. Astute viewers should note that <song> is not actually dubstep, but I always liked the way she refers to the beat being sick, such poeticism.

[3] I find the Parrot AR Drones a good source of dancing fun, but other such danceable robots include…

[4] I prefer the Ruby brand of code, but feel free to substitute Ruby for your own brand preference.

[5] Yours for only <some money> on Ebay

[6] Don't we all love dependencies. If you do read this by Justin Searls and you soon won't. <add link>

[7] You have `usb` right? Not that fancy `usb-c` I mean good old fashioned `usb-whatever`.

[8] There is some real nice magic here, and actually my first ever open source commit I believe.<insert story of my first commit>

[9] When my nephews were much younger, I let them have a go of this, forgetting they had no sense of danger they promptly crashed and broke my drone into wall. So to still teach them code albeit in a much safer way, we got the dancemat to control Spotify<link to code>. Still just as much fun for them, but ultimately much cheaper and safer for me.
