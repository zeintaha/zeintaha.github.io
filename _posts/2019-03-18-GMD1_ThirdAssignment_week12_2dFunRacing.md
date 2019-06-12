---
layout: post
title: "Game Development1 3rd assignment week12 2D FunRacing"
date: 2019-03-18
---

Mihai continued work on first Scene(level1)

After this we proceeded and added a script to the car. The script has made possible the detection of the collision between the player and the enemy. On impact, a sound would pe played through the method “void OnCollisionEnter2D(Collision2D col)” and the game is terminated. Accelerometer is a method specific for the mobile games, the car uses the accelerometer sensors of the phone in order to move, we locked the movement only to horizontal movement.

<img src="../../../images/third/script4.jpg">

Enemy cars

<img src="../../../images/third/enemy_cars.jpg">

Every “enemy” car sprites are added to Prefab folder and each one have a script attached to it, this script sets the speed and the direction so they are heading towards the player


<img src="../../../images/third/script5.jpg">

This two parts were created and implemented by Mihai
Gabriel continue work on his task Tank scene by adding scripts and assets for tank and projectile
However this script didn’t make the projectile actually move, it just spawn it, so we applied a script to the actual projectile

<img src="../../../images/third/script6.jpg">

Can’t really die, only if you are trying to

Main scene/menu scene(Taha)

<img src="../../../images/third/main_menue.jpg">

<img src="../../../images/third/game_controls.jpg">

Both scenes are created using Inkscape and have active buttons controlled through uiManager script methods like Menu() and Option() where is used UnityEngine.SceneManagement and specific scene is loaded when this methods are called with buttons

<img src="../../../images/third/script7.jpg">


All buttons in all scene use methods like Play(), Pause() or TankMode() from this uiManager.

Taha finish the animation for police car by using animation and animator component showed below:

<img src="../../../images/third/animatoion.jpg">

<img src="../../../images/third/animator.jpg">