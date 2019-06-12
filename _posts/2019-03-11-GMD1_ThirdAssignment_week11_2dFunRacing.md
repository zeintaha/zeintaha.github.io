---
layout: post
title: "Game Development1 3rd assignment week11 2D FunRacing"
date: 2019-03-11
---

Main requirements :
-	Create a 2D local multiplayer game OR a 2D mobile game.
-	Use everything you have learned so far (input, physics, audio, animations...).
-	Your game should include a menu and multiple user interface elements.
Starting from the project requirements presented above, team choose a topic, research options, brainstorming content ideas and finally agreed on idea of a 2D racing car mobile game and a name for project, FUN Racing. Project is an endless game where you need to try and dodge as much cars as possible. It doesn’t have and end purpose, it is just a fun way to kill time.
For this idea we research further use a YouTube Unity Racing Game Development Tutorial by Charger Games and use imported car sprites from that project.
Group worked on game design and decide we will have a number of 4 scenes:  Menu, Options, Level1, Tank. Developing scenes assign for each team member Taha work on Menu and Option scene, Mihai game Level1 scene and Gabriel game Tank scene    	

FIRST scene(level1)(Mihai)

<img src="../../../images/third/road.JPG">

In this scene, we used some Sprites for the “enemy” cars, for the to spawn and come into a certain direction we used the following script which sets their delay as well 

<img src="../../../images/third/ss1.JPG">

In order for the “hero” car to move, we used a function called RigidBody2D to give it some Physics or, more correct take some physics of off it. We did that so the car won’t be affected by the gravitation pull.

<img src="../../../images/third/rigidbody.JPG">

Second scene(tank/GOD mode)(Gabriel)

<img src="../../../images/third/road2.JPG">

We made this scene for fun and giggles basically. The tank uses the same movement script and properties as the car from the previous scene. The only addition is that, in this scene the tank, obviously shoots projectiles continuously, at a delay of .5 ms.
Gabriel drew a separate sprite for the tank projectile and scripted it in order to move.
The projectile is a sprite, has a box collider and a RigidBody2D property. We’ve set the gravity to 0 again for the same reasons as the car and the tank. We then, set an empty game object as a child to the car and put the projectile into the game object as a prefab. The GameObject acted as a spawner for the bullets using this script.

<img src="../../../images/third/script2.JPG">

The road movement was implemented  by Taha, as well as the ui manager and menus
Road movement script: 

<img src="../../../images/third/script3.JPG">

And Taha continued by starting work with animation for police car