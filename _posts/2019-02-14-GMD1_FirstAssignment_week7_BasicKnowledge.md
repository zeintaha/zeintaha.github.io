---
layout: post
title: "Game Development1 1st assignment week7 BasicKnowledge"
date: 2019-02-14
---

For our first assignment in GMD1 we had about 2 weeks to form our groups, come up with an idea, and implement it with the help of Unity. Our group is formed of Gabriel Baciu, Mihai Barbus and Taha Zein. Everyone had to come up with an idea and some implementation of it until Friday 08/02-19. Eventually we chose Mihai Barbus’s idea, a pinball game, inspired of course from one of our first PC games ever played. 
For this assignment, certain requirements were set, we had to make use of:
•	Triggers
•	Colliders
•	Rigidbodies
•	Physics materials
•	Raycasting
•	Prefabs
•	Assets from the Asset Store
Basic scripting (e.g. user input, instantiating game objects, etc.)
In week 7, all our team members researched and learned how to get around Unity(still a new tool to us), through different tutorials and resources.
Mihai was in charge of the implementation of:
-	Game table
-	All around Boundaries
-	BallPrefab
-	Flippers
For each game object, material assets were created and added to Prefabs to fulfill one of the project requirements
Rigid body component was added for the ballPrefab and the Flippers, moreover, a hinge joint was created in order to set anchor to the Flippers
Mihai also did the script for Flippers and added some gravity through the option available in the project settings/physics.
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FlipperScript : MonoBehaviour
{
    public float restPosition = 0f;
    public float pressedPosition = 45f;
    public float hitStrenght = 10000f;
    public float flipperDamper = 150f;
    private HingeJoint hinge;
    public string inputName;

    void Start ()
    {
        hinge = GetComponent<HingeJoint>();
        hinge.useSpring = true;

    }
	
	
	void Update ()
    {
        JointSpring spring = new JointSpring();
        spring.spring = hitStrenght;
        spring.damper = flipperDamper;

        if (Input.GetAxis(inputName) == 1)
        {
            spring.targetPosition = pressedPosition;
        }else
        {
            spring.targetPosition = restPosition;
        }

        hinge.spring = spring;
        hinge.useLimits = true;
    }
}

me as Taha was in charge of making the blog as well as the enemies(our collectibles and scoring system)
Gabriel was in charge of making the bouncy obstacles that the ball would hit and reach certain collectibles, making the game as “authentic” as possible and correcting some of the grammatical errors in everyone’s report before uploading it to the blog.
