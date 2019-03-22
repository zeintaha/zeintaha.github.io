---
layout: post
title: "Game Development1 2nd assignment week9 AnimatingCharacter"
date: 2019-02-28
---

<img src="../../../images/second/main.png">

For this second assignment our group made a scene, containing an animated object, sounds, custom skybox and multiple sources of light.
    This assignment helped us develop or improve the knowledge regarding
    <ul>
<li>Basic game object animation</li>
<li>Character animation</li>
<li>Shaders (which were one of the hardest things to comprehend)</li>
<li>Image effects</li>
<li>Textures</li>
<li>Custom skyboxes</li>
<li>Multiple lightning techniques</li>
<li>Particles </li>
<li>Importing audio into the game</li>

 
</ul>

The group made this scene as an exercise to try and comprehend the new techniques presented to us in class, you just walk around on the plane surface try to observe the difference between certain way of lightning and how the particle system works (we tried to use snow particles for this).
 


In the picture above we can see a knight, that was our imported 3D asset from the unity asset store. We added sound effects to it when moving and/or attacking with his sword using the following scripts. Everything related to sounds was done by Mihai. He also did the snow particle system

Moving character:
the character has multiple animations, the Walk and Attack animation and Idle has been used, 
Each state has two-way transitions, and a script is controlling these animation states,
Below the animation states are diagram:

<img src="../../../images/second/animation_state.png">
 

A script for movement and attack is added as follow:

<img src="../../../images/second/Knight_controller_script.png">
