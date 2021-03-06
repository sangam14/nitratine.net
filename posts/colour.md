title: "Colour"
date: 2017-11-18
category: Apps
tags: [Android, Java]
feature: feature.png
description: "This app is based off the goal of obtaining all 16,777,216 colours by randomly generating colours when taping the screen. This figure is the amount of colours a screen can display today and it's your challenge to find them all."

{% with video_id="x56o7b9Uor8" %}{% include 'blog-post-embedYouTube.html' %}{% endwith %}

<a href="https://play.google.com/store/apps/details?id=com.pythonanywhere.brentvollebregt.colour">
	<img src="/post-assets/colour/google-play.png" alt="Get it on Google Play" style="height: 60px;"/>
</a>

## The Idea
One night I was having a chat with a friend on how stupid apps always seem to make it to the top. We started to think of stupid apps and thus this app was born. Based off the simple idea of just tapping the screen to randomly generate colours I managed to turn an idea into an app in a couple of months in between my study.
This idea also made me wonder how long would it actually take to complete an app of this nature for users? The investigation can be found [here]({{ url_for('blog_post', path='randomly-generating-numbers-to-fulfil-an-integer-range') }}).

## The Goal
So the app has a pretty simple goal; find all the colours. Now it may seem that all you have to do is tap the screen 16,777,216 times to finish but colours are randomly generated. This means if you did get to 16,777,215 colours, you would have a 1 in 16,777,216 of finishing.
On the chance that you get two of one colour, you can merge it with another duplicate colour you have in the colour mixer to find another colour.

## Screenshots
<div style="text-align: center;">
    <img src="/post-assets/colour/tap-screen.png" alt="Main screen" style="width: 24%; display: inline;"/>
    <img src="/post-assets/colour/colour-viewer.png" alt="Colour finder" style="width: 24%; display: inline;"/>
    <img src="/post-assets/colour/colour-mixer.png" alt="Colour mixer" style="width: 24%; display: inline;"/>
    <img src="/post-assets/colour/previous-colours.png" alt="Recent colours" style="width: 24%; display: inline;"/>
</div>

## Features
- Recent Colours: Hold down on the tap screen on swipe to the right to look at the 10 most recent colours found
- View Colours: Look at the colours you currently have
- Status: On the tap screen your taps, progress and current colour count are displayed
- Mix Colours: When you find duplicates of colours, mix them together to find a new colour
- Achievements: Get milestone achievements as you play
- Gestures: Swipe to get to different areas of the app (can be toggled)

## Bug Reporting and Feedback
Think you've found a bug or just want to give back some feedback? Send me an [email](mailto://{{ site.email }}?subject=Colour%20Bug%20Report) and i'll look into it!
For bug reports please include:
- Your name
- Model of your phone
- Android version
- A summary of the bug
- How you found the bug (how to reproduce it)

## Other Projects Used
- [github.com/chiralcode/Android-Color-Picker](https://github.com/chiralcode/Android-Color-Picker)
- [github.com/balysv/material-ripple](https://github.com/balysv/material-ripple)
- [materialdesignicons.com](https://materialdesignicons.com)
- [material.io/icons/](https://material.io/icons/)
