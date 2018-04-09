<a id="top"></a>
# Intro to Unity

*This curriculum is meant to introduce beginners to the Unity platform.*

Written by [Narcisa](mailto:narcisa@adicu.com) and [ADI][adi], based off material, code and tutorials found on the [Unity official website][unity-website].

<a href="#top" class="top" id="getting-started">Top</a>
## Getting Started

### What will this tutorial teach me?
You will learn how to navigate the Unity interface and build a simple 3D game to get you started.

### What is Unity?
Unity is a popular tool that allows you to create interactive applications for many platforms. You can use Unity to build high-quality 3D and 2D games or experiences, deploy them across mobile, desktop, VR/AR, consoles or the Web.   

### What topics should I know before starting? 
We prefer that you have a basic familiarity with at least one programming language (Python, Java, C/C++ etc.). We do NOT expect you to have knowledge of C#, which is the language that the platform uses. 

### Environment Setup 
Download latest version of Unity (currently 2017.4) [here][unity-download]. For now, we will be using the Personal version, which is free. During the installation, you will be asked to do a component selection. You can just go with the default options. This might require around 11 GB, so make sure you have enough space, and it will take a few minutes.  


<a href="#top" class="top" id="table-of-contents">Top</a>
## Table of Contents

-	[Level 1: Unity Basics](#basics)
	-	[1.1 How to navigate the Unity Editor](#editor)
	-	[1.2 GameObjects and components](#objects-and-components)	
	-	[1.3 Your first project](#project)	
-	[Level 2: Roll-a-ball Game](#roll-a-ball)
	-	[2.1 Introduction](#intro)
	-	[2.2 Environment and Player](#env-and-player)
	-	[2.3 Camera and Play Area](#cam-and-play)
	-	[2.4 Collecting, Scoring, and Building the game](#collecting-scoring-building)
-   [Additional Resources](#additionalresources)


------------------------------
<a href="#top" class="top" id="basics">Top</a>
## Level 1: Unity Basics

<a id="editor"></a>
### 1.1 How to navigate the Unity Editor

The Unity Editor is made up of different views and windows. We will go over what each of these is:

- **Scene View** - Unity games are built out of scenes, which you can think of as containers. They contain everything that is part of your game, like the characters, the world etc. We use this view to arrange objects in your scene. 
- **Game View** - This view shows what the player sees when they play the game. This is where you will test your game. You enter Play Mode, by clicking the **play button** at the top center of the Editor.
- **Inspector Window** - This is the window that gets highlighted whenever you select a GameObject (see next subsection), and allows you to add Components (see next subsection) to your GameObject and manipulate values of Components.
- **Hierarchy window** - This is the window that contains a list of all of your objects and everything you see in the Scene view. You use this to organize and also select objects in the Scene.
- **Project Window** - This is the window where you see all of the files in your project. You can add different directories, like a scenes directory, where you will save all of your scene files, or a scripts directory, which we will talk about later.

<a id="objects-and-components"></a>
### 1.2 GameObjects and Components

Games in Unity are built using GameObjects and Components.  

- **GameObjects** - They are building blocks of Unity, and do not do anything. Everything in a Scene is a GameObject.
- **Components** - They tell Unity what a GameObject does. You can add Components to GameObjects to define their behavior. While Unity provides lots of useful Components, you should know that you can define your custom ones as well. 
	- One of the most important Components in Unity is the **Rigidbody** component. Rigidbodiy Components are intrinsic parts of the built-in Unity physics engine. Adding it to a GameObject will allow that GameObject to be affected by physics forces, such as gravity. 

<a id="project"></a>
### 1.3 Your first project

Let's now put all that we've learned into practice! :)

- First, open Unity and log in with your Unity or Google/Facebook account.
  
![Unity welcome window][welcome-window]  

- Then click on the **NEW** button, add in a name for your project and the location where to save it. Leave 3D selected. You should see something like this:  

![Unity new project window][new-project] 

- You should now be able to see the Unity Editor with the views and windows we talked about earlier!   

![Unity Editor][editor]

- The next step is saving our current empty scene. You can do that by going to **File** -> **Save Scene**. You can now name your scene and save it in a new Scenes directory under the Assets directory. Select the **Create** menu in your Project window and click on **Folder**. It's customary to call the directory \_Scenes, with an underscore before the name, so that this directory, which is really important, always shows up top in your project. You do not need to worry about the Assets directory for now, but keep in mind that most of the files you will need will end up in this directory. You should now see this:  
![Editor with First Scene saved][first-scene]  

- Now it's time for our first GameObject! Go to **GameObject** -> **3D Object** -> **Plane** and rename this object Ground. You can do that by right-clicking and then hitting **Rename** on the object in the Hierarchy window and typing in the new name.   
![Create Plane Object][plane]  

- If you select the Ground object, you will see in the Inspector window the characteristics and components of our plane. One of these is the Transform component. Make sure that the position value is set to 0, 0, 0, the origin. This is the origin of the world in your scene, and everything will be calculated with respect to it. Then make the scale on the X and Z axes equal to 2 to make the ground larger.  
![Set ground to origin and scale it up][ground-transform]   

- Next, add a new object, but this time a sphere. Name it Player, and double-click on it to bring it in focus (You can also do that by clicking on the sphere, and hitting the **F** key, which stands for Frame Selected). Figure out on your own how to make the sphere appear as floating above the ground.  
![Sphere floating above the ground][sphere]  

- You are now ready to enter Play mode! Click the play button at the top center. It will seem that nothing has changed, and nothing should be moving. A nice tip to differentiate from scene to play view is to go to **Unity** -> **Preferences** -> **Colors** and under **General** next to **Playmode tint**, select a color that your editor will appear in when you are in play mode. Unity allows you to change values while in play mode, but it does not actually apply them - this is more for you to test things out, so being able to know whether you're making actual changes can be life-saving!  
  
- OK, but what if we want our objects to be more distinguishable? You add color or texture to an object you use what's called a **Material**. First, create a new directory in your project called **Materials**. With the Materials directory selected, click on Create again, but this time select **Material**. You should have a new material instance. Rename it Background, then in the Inspector, under **Main Maps**, click on the **Albedo** color field and give a nice color to your background. To apply the material to an object, click on the Material in the Project window, then drag it onto the desired object.  
![Ground in purple][purple-ground]   

- 'But why is my sphere floating instead of falling!?' Remember how we talked about physics and components? That is because your sphere object is not yet using physics - it needs a Rigidbody component. To attach one, click on the Player object, then **Add component** -> **Physics** -> **Rigidbody** in the inspector. This will attach the Rigidbody component to the object selected. In our case, the sphere. You'll notice that there are multiple values that the component comes with. If you have **Use Gravity** selected, and hit play again, your sphere should fall to the ground, pulled by gravity.  
![Sphere pulled by gravity to the ground][gravity-sphere]  
  
If you've made it so far, you are **extra awesome**!!! Unity is known to have quite a steep learning curve, so remember to be patient and persistent. They also have great documentation and online support communities, so don't be afraid to look up any questions if you hit a roadblock. Now you're ready to move on to more advanced stuff - you're going to build Unity's classic roll-a-ball game.  
___________
<a href="#top" class="top" id="roll-a-ball">Top</a>
## Level 2: Roll-a-ball Game

<a id="intro"></a>
### 2.1 Introduction

This is one of the introductory Unity games, which uses most of the concepts you've learned so far, and introduces scripting, which is the code you write to control the behavior of objects in your scene. In the game, the player controlls a ball with the keyboard, and picks up and counts special objects on a gameboard. You can find the official video tutorial [here][roll-a-ball]. 

<a id="env-and-player"></a>
### 2.2 Environment and Player

- **Environment**: Luckily, you have already set up most of the environment by completing the project at the previous step. You can bring the sphere back to touch the platform. You should also make another change will be helpful later: you should rotate the main directional light, to get better lighting on the player. You might have noticed that we haven't mentioned lighting yet, and you don't need to worry about that. For now, all you need to know is that Unity automatically provides your scene with a **Directional Light** object, which is used to light up your scene. Click on it and set the Transform Rotation on the Y axis to 60 for better shade to our sphere.  
  
- **Player**: Let's think about what you want your Player object to be able to do. You want it to roll around on the game area, and not fly off into space, as well as collide with and collect objects. For this, you need physics. You have already added a Ridigbody component, which is the first step.  

	- Next, you want to be able to control the player using the keyboard. You want to apply the keyboard input to the object using forces. You can do this by using a script that you attach to the object. Select the player object, then add a new component, called **New Script**. Call it **PlayerController** and leave it in C#. This will create a new script, compile and attach it to the sphere player.  
	![Creating a new script][new-script]  

	- Now you want to be able to modify your script. You cannot modify a script inside the Unity Editor, but you can double-click on it and open it with a script editor of your choice. MonoDevelop should be the default editor that Unity comes bundled with, and it will try to open it with that. I personally use Visual Studio, which is a popular one among Unity developers, but you can find what your preference is and go with that. You should see something like this:  
	![Empty script in editor][script-editor]  

	- Delete the **Start()** and **Update()** code for now. If you are wondering what MonoBehavior is in the code that you see, for now you need to know that it is the base code from which every Unity script derives. It offers what are called 'life cycle' functions that make it easier for you to develop your app and game. Deriving from a base class is called polymorphism and is a paradigm that is important for object-oriented programming. You do not need to understand any of that, but feel free to look all of it up if you are curious. I will link to an image that shows all the life cycle functions that come with MonoBehavior.  

	- Copy and paste the following code in your script. I will explain all of this in a second:  


			using System.Collections;
			using System.Collections.Generic;
			using UnityEngine;
			
			public class PlayerController : MonoBehaviour {

			    public float speed;

			    private Rigidbody rb;

			    void Start ()
			    {
			        rb = GetComponent<Rigidbody>();
			    }

			    void FixedUpdate ()
			    {
			        float moveHorizontal = Input.GetAxis ("Horizontal");
			        float moveVertical = Input.GetAxis ("Vertical");

			        Vector3 movement = new Vector3 (moveHorizontal, 0.0f, moveVertical);

			        rb.AddForce (movement * speed);
			    }
			}
		- **FixedUpdate()** is one function that allows you check for input at every frame and which gets called just before performing any physics calculations, which makes it the place where we want our physics code to go. To find out more about how to use current Unity code and documentation (what is called the Unity API), you can start typing (like **Input**, for instance) then selecting what you want to research, and then use shortcut **CMD + ' (Mac)** or **CTRL + ' (PC)**, which will automatically open the Unity docs, where you can find every reference in the Unity documentation related to that search.  

		- The two floats take in input from . We then create a vector with that input and use it to apply a force along the direction of the vector to our sphere's Rigidbody component. We also have a public **speed** variable, which we can set to whatever value we want. The fact that the variable is public makes it actually appear in the Inspector for our sphere object as an editable property. Play around with different values for speed until you find one that you like.  
		![Script component with speed property][filled-script] 

		- Something that is key is to understand that we are applying the force to the sphere's Rigidbody component, which means that we need to get access to it. There are mulptiple ways of accessing a different component on the same GameObject, but here are using a variable to hold the reference in the script, and we set it in the **Start()** function. If there is a Rigidbody component, the **GetComponent<Rigidbody>()** function will find it and hold the reference to it. All the code in the **Start()** object is called in the very first frame.    

<a id="cam-and-play"></a>
### 2.3 Camera and Play Area

- **Camera**:
	- As you can notice, you have a **Main Camera** object in your scene by default. I will not go into details about the camera, but for now you need to know that it determines what you see while in play mode.  

	- Let's first lift it up by 10 units, and tilt it down by 45 degrees, so we get a better view of our scene. Next, select the camera and make it a child of the Player, by dragging it onto the Player object in the Hierarchy window. This will make the camera follow the Player. This is a typical third-person setup.    
	![Camera Transform component][camera]  

	- However, if you click play, you notice that the camera now rotates like crazy, because the player roatate on all axes. We might want to attach the camera in a different way, with a script where we can set an offset between the camera and the Player. Dettach it from the Player, and add a new script to it called **CameraController**. Here is the code in the script:  


			using System.Collections;
			using System.Collections.Generic;
			using UnityEngine;

			public class CameraController : MonoBehaviour {

			    public GameObject player;

			    private Vector3 offset;

			    void Start ()
			    {
			        offset = transform.position - player.transform.position;
			    }
			    
			    void LateUpdate ()
			    {
			        transform.position = player.transform.position + offset;
			    }
			} 

		- You need a reference to the player object, and a vector that represents the offset. The offset will a vector that represents the difference between the position of the camera and the position of the player. Then, every frame we set the position of the camera to be the position of the player + the offset. We use **LateUpdate()**, which runs every frame, just like **Update()**, but it is guaranteed to run after all items have been processed in **Update()**, which means that we know our player has definitely moved in that frame. Before testing this, we need to drag the player object in the slot for the Player in the CameraController component in the inspector. Then hit play and now you have what you want!  

- **Play area**:

	- First thing you want to set is walls so that the ball does not fall off the edge. Create a new empty GameObject called **Walls**, which you will use as an organizing GameObject for your four walls. Make sure the position is at the origin. Organization is key! Using an empty GameObject to hold other other objects is customary in Unity. Now add one Cube GameObject, and call it **West Wall**. We need to change the size of the cube to make it fit our plane. Change its scale values to **0.5, 2, 20.5**. Then set its position along the X axis to -10 to place it along the edge of the plane.    
	
	![West Wall good scale][west-wall]  

	- You can duplicate the West Wall object three times, to keep the correct scale. Rename the new objects East, South, and North wall accordingly. Figure it out on your own how to place them in the correct position and correct rotation. Now you have all walls!   

	![All walls][walls]  

	- The next thing is create collectible objects for the player to pick up. Create a new cube, call it **Pick up** and lift it up to rest on the plane. To make it more attractive, make it smaller, which will make it appear like floating, by setting the scale on all axes to 0.5, and tilting it by 45 degrees in all directions. 

	![PiclUp cube][pick-up-cube]  

	- To make the cube even cooler, we can make it move. Add a new script called **Rotator** and place it in the script folder. To make the cube spin you need the following code: 

			using System.Collections;
			using System.Collections.Generic;
			using UnityEngine;

			public class Rotator : MonoBehaviour
			{
				void Update()
				{
					transform.Rotate(new Vector3(15, 30, 45) * Time.deltaTime);
				}
			}

		-  The vector gives the direction of rotation. Multiply the vector by **Time.deltaTime** to get smooth rotation, that is frame-rate independent. Check in the documentation what deltaTime represents!  

  
	- Add more of these pick up cubes, and organize all of them in an empty GamePbject called **PickUps**. Select them and spread them across the play area. Then make a new Material for them to give them a color that stands out. I trust that you can do all of this on your own! :) You can always go back if you don't remember something. When you're creating multiple duplicate instances, you might want to look into what is called a **Prefab**. I will add a link to learning about them.     
	![10 Pick Up cube objects][pick-ups]       

<a id="collecting-scoring-building"></a>
### 2.4 Collecting, Scoring, and Building the game 

- **Collecting**: In order to pick up the collectible objects, we need to detect collisions between the player and the objects, and we want collisions to trigger a new behavior, as well as checking which objects we collided with. All the objects have colliders. If we don't test the collisions, we might pick up the wrong object, say a wall or the plane. You can take a closer look at the collision component of your Player, and also learn more about colliders [here][colliders].  
![Player collider in the Inspector][player-collider]  

	- Here's the code in the PlayerController script after adding the collision detection component:  

			public class PlayerController : MonoBehaviour {

			    public float speed;

			    private Rigidbody rb;

			    void Start ()
			    {
			        rb = GetComponent<Rigidbody>();
			    }

			    void FixedUpdate ()
			    {
			        float moveHorizontal = Input.GetAxis ("Horizontal");
			        float moveVertical = Input.GetAxis ("Vertical");

			        Vector3 movement = new Vector3 (moveHorizontal, 0.0f, moveVertical);

			        rb.AddForce (movement * speed);
			    }

			    void OnTriggerEnter(Collider other) 
			    {
			        if (other.gameObject.CompareTag ("Pick Up"))
			        {
			            other.gameObject.SetActive (false);
			        }
			    }
			}     

		- The **OnTriggerEnter()** function is called when the Collider other enters the trigger. The other represents the object our Player is colliding with. What's nice about this function is that it does not actually perform the collision itself, just allows us to detect when the collision is just about to happen. When the trigger collider of other is touched, we check that the tag of the object is "Pick Up" and we deactivate it to make it disappear. Unity has this nifty feature that allows you to tag objects for various purposes. Create a new tag, call it **Pick Up**, and add it to each Pick Up object by clicking on it and selecting the tag in the Tag property at the top left of the Inspector window. Make sure that the tag is spelled correctly. 

		![Add Pick Up tag][tag] 

		- One final step to make it work is to go to the Box Collider component of every cube and select the **Is Trigger** box. This will allow the objects to use trigger colliders, instead of actually performing the collisons. This might not make much sense, but is a really useful collision feature that you should look up. There are a few steps regarding performance that I skipped over, but I encourage you to investigate and learn more about by looking at the official documentation. 

		![Is trigger][trigger]     

- **Scoring**: If you want to learn how to set up a scoring system, I encourage you to take a look at Mike Geig's official Unity Roll-a-ball tutorial. You can find the scoring section [here][scoring].     
    

- **Building the game**: If you've made it so far you are definitely **super awesome**! You have a great game, and the final step is to build it. You can deploy your game to multiple platforms, which is great. There is documentation everywhere as to how to build and deploy your applications to multiple platforms, including mobile phones or VR headsets. Definitely look it up! 

	- What you will do is first save your scene, then go to **File** -> **Build Settings**. This brings up the Build Settings window. To build a standalone application, select **PC, Mac & Linux standalone in the Platform** section on the left. Now you need to add the current scene by clicking **Add Current**, then select the **Target Platform** (in my case, I have Mac OS X), and then click the **Build** button. 

	![Build window][build]  

	- This will open up a dialog box that asks for a build location and name. Create a new folder called **Builds** at the root of your directory, and name your build, then click save. If you go to the location of the build, you can now play it on your computer!!! **Congrats!** 

	![Dialogue box][dialogue]  

	![Game][game]    
___________
<a href="#top" class="top" id="additionalresources">Top</a>
## Additional Resources

Along with this tutorial, there is a wealth of information available on Unity all across the web. Below are some good places to start:

- [Unity's official tutorial page][unity-tutorials]
- [The Roll-a-ball official tutorial][roll-a-ball]
- [More on the Unity Editor][editor-mike-geig]
- [More on scripting][scripting]
- [MonoBehavior life cycle][lifecycle]
- [Prefabs][prefabs]

[unity-website]: https://unity.com/
[github]: https://github.com/narcisacodreanu/intro-to-unity.git
[unity-download]: https://store.unity.com/
[unity-tutorials]: https://unity3d.com/learn/tutorials
[editor-mike-geig]: https://unity3d.com/learn/tutorials/topics/interface-essentials/editor-basics
[adi]: http://adicu.com
[roll-a-ball]: https://unity3d.com/learn/tutorials/projects/roll-ball-tutorial/introduction-roll-ball
[welcome-window]: imgs/welcome-window.png
[new-project]: imgs/new-project-window.png 
[editor]: imgs/editor.png 
[first-scene]: imgs/first-scene.png
[plane]: imgs/plane.png
[ground-transform]: imgs/ground-transform.png
[sphere]: imgs/sphere.png
[purple-ground]: imgs/purple-ground.png
[gravity-sphere]: imgs/gravity-sphere.png
[new-script]: imgs/new-script.png
[script-editor]: imgs/script-editor.png
[lifecycle]: https://docs.unity3d.com/uploads/Main/monobehaviour_flowchart.svg
[filled-script]: imgs/filled-script.png
[camera]: imgs/camera.png
[west-wall]: imgs/west-wall.png
[walls]: imgs/walls.png
[pick-up-cube]: imgs/pick-up-cube.png
[pick-ups]: imgs/pick-ups.png
[prefabs]: https://docs.unity3d.com/Manual/Prefabs.html
[scripting]: https://unity3d.com/learn/tutorials/s/scripting
[scoring]: https://unity3d.com/learn/tutorials/projects/roll-ball-tutorial/displaying-score-and-text?playlist=17141
[colliders]: https://docs.unity3d.com/Manual/CollidersOverview.html
[player-collider]: imgs/player-collider.png
[tag]: imgs/tag.png
[trigger]: imgs/trigger.png
[build]: imgs/build.png
[dialogue]: imgs/dialogue.png
[game]: imgs/game.png
 
