---
title: Developing simple robot control app with Atmosphere
layout: post
author: ashley
tags:
- News
- LED
- Atmosphere
---

<p>Developing an app can be a challenging project, but with the right set of tools and a good dose of enthusiasm, it can be rewarding as well! In this entry, I will walk you step-by-step through the design of my first app: a robot remote control.</p>

<h4>Getting Started</h4>

<p>Starting any new task is always the hardest part.  Just like driving, when you set out to develop an app it is essential to have a good roadmap of where you want to go.  As you twist and turn along the way, your roadmap will serve as a guide to keep you on course.</p>

<p>The goal of our project was to create a user-friendly app to play a 2-on-2 robot soccer game.  And oh yeah, did I mention that the robots were to be remote controlled by the user’s smartphone via Bluetooth?  The app has a set of light-up arrow keys that the users can press to wirelessly direct the robots in the field of play.</p>

<p>To make all of this possible, the app uses an up-and-coming development environment called Anaren Atmosphere’s Developer.  What this means is that the Anaren Developer contains the blueprint with instructions that allows the user’s smartphone to communicate with the robot over the Bluetooth network.</p>

<h4>Look for Examples</h4>

<p>Once you have a vision for your app, it is a good idea to surf the web to check out if there are already any existing projects similar to yours.  If so, you may be able to use them as a springboard for your own project (giving proper credit to the sources, of course).  I mean, why reinvent the wheel when Google is only a few touches of the keyboard away?</p>

![Broken image link](/assets/look_for_examples.PNG)

<p>The Anaren Developer actually already has many sample projects to explore.  In fact, my initial app design was heavily based on the Robot sample that can be found under the help menu of the developer.</p>

<p>This sample provides a great introduction to the software and even looks a bit like the app that I had envisioned designing.  It has buttons that cause a robot to move in ways similar to what I needed as I set forth to design my app.  This turned out to be a great starting point and was inspiration for the rest of my work.</p>

<h4>Make it Work</h4>

<p>After reviewing some potentially useful sources, the next step is to decide what you can use from the existing apps but also (and perhaps most importantly) what you need to change to fit your specific task.</p>

<p>In my case, the sample app’s general layout could be incorporated into my work.  However, the way the sample app communicated with the robot was not exactly what I needed.</p>

![Broken image link](/assets/make_it_work.PNG)

<p>The SMAC robot needs specific commands to know where to go.  It requires the commands to be in a particular form in order for it to understand. For example, if {“motor1”: “off”} is sent to the robot, it will know to turn motor 1 off.  These commands were set so that they are automatically sent to the robot when the arrow buttons are pressed.</p>

<h4>Make it Visually Appealing</h4>
<p>Once you finally get the app working properly (programmers use the term “debugging” to talk about the process of checking for errors), the next step is to make your app look beautiful.  By this point, you have poured your heart and soul into making this app, so why not add some visual appeal so that everyone else sees how beautiful it really is?</p>

<p>The Anaren Developer automatically starts out with a white background and light grey buttons.  While an app may work perfectly, it is always more appealing if it has some color and a pinch of pizazz.</p>

![Broken image link](/assets/make_it_visually_appealing.PNG)

<p>In the Anaren Developer, one of the easiest ways to accomplish this is with the use of images.  In my next design, I added a background and a title block.  I also added images of arrows that went underneath the corresponding buttons.  But I wasn’t finished quite yet.</p>

<h4>Keep Revising</h4>

<p>After creating this initial design, I came across another example app from Anaren that showed how to create a more sophisticated user interface (https://atmosphere.anaren.com/wiki/UI_Demo_Example).  This discovery allowed me to make several more improvements.</p>

![Broken image link](/assets/keep_revising.PNG)

<p>The arrows evolved from simple pictures in the background to real buttons with functionality of their own!  Rather than having to press the exact rectangular button, as before, the user could now press anywhere in the arrow to send the robot instructions to start zooming off in that direction.  To top off the new design, I added an actual photo of the robot in the bottom corner of the app.  Pretty nifty, eh?</p>

<p>Besides having better graphics, the revamped app design also contains some sweet interactive features as well.  I added a hyperlink to our website in the bottom of the app.  I even got the arrows to change from purple to yellow when the user presses them.  Cooler still is that every time one of the arrows is pressed, the wheel on the robot picture rotates.</p>

<p>The wheel rotating was by far the trickiest part of the design process.  There were several angles of the problem that needed to be considered.  I wanted the wheel to start rotating whenever a button was pressed. The image of the wheel needed to do a single, full rotation and then stop.  The rotation had to happen at just the right speed (in case you are curious, this was accomplished by rotating the image 40 degrees every 40ms).</p>

<p>As you can see, my app project was quite challenging at several points in the development process.  I spent many hours working with my teammates in order to find solutions to complex issues.  But in the end, I have a great feeling of satisfaction looking at our final product.  I hope that you enjoy viewing my app as well.  After all, I didn’t design it for my own enjoyment, but rather for you to have a great educational tool.  And I hope that you can see that building an app, frustrating as it may be at times, is highly rewarding and certainly worth it.</p>

<p>"Click <a href="/assets/Robot_Remote.atmo">here</a>" to download the code to our app to check it out for yourself."</p>