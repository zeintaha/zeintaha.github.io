---
layout: post
title: "Game Development1 1st assignment week8 BasicKnowledge"
date: 2019-02-21
---

In week 8, we started implementing the game even more.
Mihai added Icy material as physical material to the ball and table.
Created and implemented launcher and the launcher’s trigger. Imported audio assets from Assets store and Added PowerSlider Canvas.

Here is the code for it:
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using UnityEngine;
using UnityEngine.UI;

public class LauncherScript : MonoBehaviour
{
    float power;
   
    public float maxPower = 100f;
    public Slider powerSlider;
    List<Rigidbody> ballList;
    private bool ballReady;

	
	void Start ()
    {
        powerSlider.minValue = 0f;
        powerSlider.maxValue = maxPower;
        ballList = new List<Rigidbody>();
    }
	
	
	void Update ()
    {
        if (ballReady)
        {
            powerSlider.gameObject.SetActive(true);
        }
        else
        {
            powerSlider.gameObject.SetActive(false);
        }

        powerSlider.value = power;
        if (ballList.Count > 0)
        {
            ballReady = true;
            if (Input.GetKey(KeyCode.Space))
            {
                if (power <= maxPower)
                {
                    power += 50 * Time.deltaTime;
                }
            }
            if (Input.GetKeyUp(KeyCode.Space))
            {
                foreach (Rigidbody r in ballList)
                {
                    r.AddForce(power*Vector3.forward);
                }
            }
        }
        else
        {
            ballReady = false;
            power = 0f;
        }
    }

    private void OnTriggerEnter(Collider other)
    {
        if (other.gameObject.CompareTag("Ball"))
        {
            ballList.Add(other.gameObject.GetComponent<Rigidbody>());
        }
    }

    private void OnTriggerExit(Collider other)
    {
        if (other.gameObject.CompareTag("Ball"))
        {
            ballList.Remove(other.gameObject.GetComponent<Rigidbody>());
            power = 0f;
In week no. 8 Taha, implemented the collectibles as well as the scoring system.
This is how he did it.

He created a new cube and renamed it PickUp, then he resets their transform to origin, so this cube will be his Pickup object, in order to be more effective it must attract the attention of the Player, by making it smaller and tilt it over 45, 45, 45 in each of the axis of the transform rotation, then he had to add rotation to the cube, to do this he needed a script:

	using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class Routator : MonoBehaviour {
		// Use this for initialization
		void Start () {
		}
		// Update is called once per frame
		void Update () {
			transform.Rotate(new Vector3(15,30,45)*Time.deltaTime);
		}
}


Ball Prefab:
When a ball collides with those pickups they disappear and a point is added to the count, after collecting 8 pickups, the player wins.
When the ball collides with the down hall, the player will lose, the code is illustrated below: 
using System.Collections;
using System.Collections.Generic;
using UnityEditor;
using UnityEngine;
using UnityEngine.SceneManagement;
using UnityEngine.UI;

public class sc : MonoBehaviour
{
    public Text countText;
    public Text winText;
    private int count;
    // Use this for initialization
    
void Start () {
      		count = 0;
      		setCountText();
        		winText.text = "";
   	 }

	// Update is called once per frame
	void Update () {
        		if (Input.GetKeyDown("r"))
{	SceneManager.LoadScene(SceneManager.GetActiveScene().name);
        		}
 }
    	void OnTriggerEnter(Collider other)
    	{
        		if (other.gameObject.CompareTag("Pick Up"))
        		{
           		 other.gameObject.SetActive(false);
            	count = count + 1;
          		 setCountText();
       	 	}
        		if (other.gameObject.CompareTag("Losing"))
        		{
           	SetYouLose();
        		}
}
    	void setCountText()
    	{
        		countText.text = "Count: " + count.ToString();
       		if (count >= 8)
        		{
           		winText.text = "You Win!";
       		 }
  	 }
   	void SetYouLose()
    	{
        winText.text = "You Lose, Press R to restart";
    	}
}

Finally, Gabriel’s part came, where he implemented the obstacles, the ball was hitting.

The usual bouncy obstacles weren’t that hard to make, they were only some 3d Objects like some cylinders or some cubes that had a script, through that script, the bounciness of the said object can be set. For the script he chose to use JavaScript, as he had a bit of previous knowledge about it.


#pragma strict

var explosionStrength : float = 100;

function OnCollisionEnter (_other : Collision)
{
    _other.rigidbody.AddExplosionForce(explosionStrength, this.transform.position, 5);
}
then, implemented a rotating Obstacle, a gearwheel/mill, that will interact with the ball. For that he didn’t use any Script. He only used the components integrated in unity.
A cylinder was created which was the anchor and the rotating pivot of the whole gear and 4 arms made out of remodeled cubes. The movement of this mill, was possible through unity’s function of motor, after you anchored the arms on the cylinder and blocked a few axis, it was possible to set the velocity(speed) and the force of this motor.

Personal reflections:

Taha: As I have no prior before about using Unity, this is very excited assignment, as it boost my skills in two weeks, to be able to create prototype for a solution i need, looking forward for more assignments :)


Gabriel:
 I think this project was a nice and easy way to learn and get used to unity, I like the idea of problem base learning and learning trough practice. I think our team had a good connection established trough communication at every stage of the development of the project.


Mihai: Nice experience with learning by doing, achieved knowledge related to Unity assets like Scene, Game Object, Components, Materials, Physical Materials and Basic Scripting in C#. The most challenging part was Launcher Trigger and Launcher Script where we needed to use UnityEngine.UI, and Input setup. Good group teamwork and good communication achieved with help of Unity Collaborate and Slack

Our final result!
 

