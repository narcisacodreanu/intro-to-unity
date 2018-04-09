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
	-	[2.1 Another Subsection](#another-subsection)
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

<a id="another-subsection"></a>
### 2.1 Another Subsection

___________
<a href="#top" class="top" id="additionalresources">Top</a>
## Additional Resources

Along with this tutorial, there is a wealth of information available on Unity all across the web. Below are some good places to start:

- [Unity's official tutorial page][unity-tutorials]
- [The Roll-a-ball official tutorial][roll-a-ball]
- [More on the Unity Editor][editor-mike-geig]

?? gallery/showcase -> usecases of unity; mention multiplatform 
asset store; packages

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
 
