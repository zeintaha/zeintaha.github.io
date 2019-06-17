---
layout: post
title: "Game Development1 5th assignment weeks 15, 16, and 17 ChemAR"
date: 2019-04-15
---


Main requirements:
-	Create a serious game with an educational purpose in a natural science museum.
-	Target group 8-12-year-old children
-	Any AVR technologies allowed
-	Physics, Animation, Graphics, User Interfaces, Game manager, Advance scripting, Optimization and Solid principles
Starting from the project requirements presented above, developer team starts brainstorming session for getting a minimum viable product in order to fulfill requirements.
Main brainstorming focus was on fallowing themes: 
-	Choose a field of science for project
-	Choose an AVR technologies 
-	Choose the type of game
-	How can game have an educational role
-	A name for project
Each team member elaborates and purpose 3 choices for each theme topic after an individual research of themes.  
Related to the choice of field of science for project, after analyzing pros and cons between Physics, Astronomy and Chemistry we decide to go with Chemistry 
For the choice of technology or type of game developer team agreed to create a augmentative reality mobile quiz game.
Adding 3d models for each chemical substance, possibility to read extra information and adding specific question for each element will enhance the educational role of education in a fun and enjoyable experience  
The mobile game name project for 5th GMD workshop assignment chosen is ChemAR. 


Team start working on project design and implementation using one agile working methodology by dividing individual task in fallowing manner:
-	Taha – Scenes, number of scenes  
-	Mihai – Scene Content and Assets  
-	Gabriel – test AR technologies Vuforia vs AR Core	



Game scene(Taha)

Design wise developers agreed for 4 main scene: a menu scene and three main game scenes

<img src="../../../images/fifth/1.jpg">

Menu scene presented above containing application name and in game menu with access to main game scenes and exit option.



First game scene is containing application name, one Periodic table of elements and in game menu with access to menu scenes and exit option. The first game scene is accessible from Menu Scene and is presented in figure 2 below

<img src="../../../images/fifth/2.jpg">

Second game scene is containing application name, list of elements and game menu with access to menu scenes and exit option. Second game scene is presented below in 

<img src="../../../images/fifth/3.jpg">

Third game scene is presenting the quiz game with application name, question and reply versions, score and  game menu with access to menu scenes and exit option, that is presented below in figure 4

<img src="../../../images/fifth/4.jpg">


Scene content and assets(Mihai)

First game scene, presented in figure 2, contain a detailed image with Periodic table of element with all 118 elements and specific detail for each element, like Symbol, Name, Atomic number and Atomic mass.
Second game scene contain a list with all elements name and atomic number, and for each element is added an animated 3D model, and a direct connection or active link for extra information about element. We use data from Lenntech.com or Wikipedia.
Third game scene contain a set of 10 questions related to elements, each question with two clickable reply version
All 3D models assets are imported from Unity Asset market as a Science Lab paid asset, that was perfect for our project


Technologies (Gabriel)

For game implementation I have tested Vuforia and AR Core.
Initially project supposed to be implemented with AR Core, the only one that have vertical detection, but in the end after analysis of all pros and cons, we settle for Vuforia, which is faster in plane detection and use image marker.
The fun part begins from this moment with implementation, where we have a lot of compatibility challenges 



