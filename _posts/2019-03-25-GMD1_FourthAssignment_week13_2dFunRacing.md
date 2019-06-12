---
layout: post
title: "Game Development1 4th assignment week13 2D FunRacing"
date: 2019-03-25
---
Main requirements :
-	Create a short, replayable game with a highscore system.
-	Intermediate gameplay scripting concepts where applicable.
-	At least two scenes, where gameplay data is persisted between scenes (e.g. character select)
-	An in-game pause menu
-	Persistence of data between gameplay sessions (e.g. progress, profiles, custom settings) using PlayerPrefs
-	A configuration-file (e.g. in JSON) to configure the game without having to rebuild it (use the 'Resources' folder)
-	The use of coroutines in a meaningful way
-	Event delegates to decouple parts of your code
-	Scriptable objects that hold game related data
Starting from the project requirements presented above, developer team choose to upgrade and further develop FUN Racing , which is the previous 2d mobile game project for third GMD workshop assignment. 
Task was divided in fallowing manner:
-	Taha - persistence of data between scene(scoring system),JSON 
-	Mihai - two main game scene -Level1 & Level2, in game pause menu 
-	Gabriel - use coroutines	
Second game scene(level2)(Mihai)
For second scene, I have used previously constructed Level1 scene and just modify some parameters like speed for road movement, speed of enemy spawn and change sprite for car in order to differentiate from first game scene
For all scenes I have added pause buttons, which all accessed Pause() method from gameManager script.

<img src="../../../images/fourth/script1.jpg">

For enhance product I added one Audio Manager with three audio source sounds with behavior mainly controlled in carController script

<img src="../../../images/fourth/script2.jpg">

Coroutines(tank/GOD mode)(Gabriel)
I use coroutine here in the example below in order to separate the shooting times from frame time and avoid shooting projectile at every frame, so by creating an IEnumurator I can define the coroutine method which setup the time for the projectile to shoot, and then in update method we call the coroutine


<img src="../../../images/fourth/script3.jpg">

Scoring system using JSON format (Taha)
In order to save progress data through 2 main playable scene I have used PlayerPref class which is provided by unity engine, I  create a public class Save as a model which has a public integer to hold the score from the current level, and that occurs only when the current level score is bigger than the existing top score, and then save it to MySettings string.
Regarding to load method, it is reading date from my settings and keep it in the top score variable in order to compare it with current score.
Booth methods are shown below:

<img src="../../../images/fourth/script4.jpg">

<img src="../../../images/fourth/script5.jpg">