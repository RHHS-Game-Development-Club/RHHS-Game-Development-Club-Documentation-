==================
Unity Fundamentals
==================

This page contains some of the fundamentals needed to understand/use Unity.

Unity Editor
~~~~~~~~~~~~

When you first open Unity, you will see the editor. Below is a breakdown of what you are seeing.

On the left, you will see the **Project Hierarchy.** This is essentially a list of all the objects in your current scene. 
You have your parent objects, and the child objects. For example, you can have a Tree parent, and the child is all the indivual shapes that make up the tree. 

Down below, you can see the **Asset Pool.** Most of the files here, you can completly ignore, since they are Unity-specific files. However, look inside the Assets folder
This is where your game specific assets, such as scripts/art/music files, live. You can drag them onto the scene, and they will appear in the Hierarchy.

The box in the middle is your **Viewport**. It can have other windows (which will be talked about later), but for now it is simply the scene. 
You can drag objects onto the scene, and move them around, using the arrow gizmos.

On the right, you have your **Inspector**. This can tell you all about the object you can click on in your hierarchy.
It can list the components, as well as object specific things, such as the type of light (directional, point, etc.)

Remember, this is just a core overview of the Unity Editor. There are a lot more windows, and UI's to talk about, but they cover specifc areas of Unity, which may be covered later.

`Unity Documentation - Editor <https://docs.unity3d.com/6000.3/Documentation/Manual/unity-editor.html>`_

Game Objects and Components
~~~~~~~~~~~~~~~~~~~~~~~~~~~

A GameObject in Unity is, an object that is used in the game. It can have scripts, and components attached to it. 
A component is a a functional piece of the GameObject. Without it, the GameObject is just an empty player. It really can't do anything else.

There are a few core components that are commonly used:

===================  ======================================================
Component            Description
===================  ======================================================
Transform            Positions, rotates, and scales the GameObject.
Mesh Renderer        Draws the mesh geometry of the object
Collider             Varies depending on shape (Box, Capsule, etc.)
Rigidbody            Allows an object to interact with physics
Camera               What the Player sees (can add multiple perspectives)
Light                Lights the scene with different styles
CharacterController  An all-around controller for the main player
Audio Source         Plays audio in the scene
Animator             Allows animations to be played on a Game Objects
Canvas               Core component for adding a UI
===================  ======================================================

**To add a component to a GameObject,** 
1. Click on the GameObject in the project Hierarchy. 
2. Look over at the inspector, and click "Add Component".
3. Then select the component from the dropdown menu.

**To remove a component from a GameObject,**
1. Select the GameObject in the Hierarchy window.
2. Look over at the inspector, and find the component you want to remove.
3. Click the three vertical dots in the top-right corner of that component.
4. Select Remove Component from the dropdown menu.

`Unity Documentation - GameObjects and Components <https://docs.unity3d.com/6000.3/Documentation/Manual/working-with-gameobjects.html>`_

Scenes
~~~~~~

Scenes in Unity are collections of GameObjects, and are commonly used for things like levels. 
You can create a scene called Level-1 for example, and when they beat the level it switches them to a new scene called Level2

**To create a scene in Unity,**

1. Click File in the top left corner -> New Scene
2. Give your scene a name (such as Level1)

**Registering a scene in Unity**

This is a neccessary step for Unity to load your scene in the final game, and so you can interact with it with code scripts

1. Navigate to File -> Build Settings.
2. Drag and drop your scene assets into the Scenes in Build window list.
3. The scene located at position Index 0 will serve as the starting scene when your game boots up.

`Unity Documentation - Scenes <https://docs.unity3d.com/6000.3/Documentation/Manual/working-with-scenes.html>`_

Scripting
~~~~~~~~~

Scripting in Unity is what allows things to happen. A GameObject can have different components, but without scripts, they don't do much.
The vast majority of this Unity documentation is related directly to scripting.

**To create a script**

1. Right click an empty area in your Asset Pool
2. Hover over the scripting tab
3. Select "Empty C# Script"
4. Make sure the name is relevant to what the script will do, and **always add .cs at the end** (this turns it into a C# script, which is what Unity uses)

.. note:: 

    This website is not here to teach you C#/Programming. If you do not know how to program, please reach out to Norrie Adams (or another coder with the "God" Role) and they will help you.

MonoBehaviour 
~~~~~~~~~~~~~

MonoBehaviour is the base class that almost every Unity script derives from. It allows your code to run as a component on a GameObject and hook into Unity's built-in event lifecycle.

**Core Lifecycle Methods**

* **Awake():** Called once when the script instance is loaded. Used for initializing variables or states.
* **Start():** Called before the first frame update. Used to set up interactions between scripts.
* **Update():** Called every frame. Ideal for gameplay logic, inputs, and timer checks.
* **FixedUpdate():** Called at fixed time intervals (independent of framerate). Used strictly for physics code.

**Key Features**

* **Inspector Control:** Mark variables as ``public`` or use ``[SerializeField]`` to expose them directly in the Unity Inspector.
* **Component Access:** Use methods like ``GetComponent<T>()`` to communicate with other components on the same GameObject.
* **Coroutines:** Execute logic over time or pause execution using ``StartCoroutine()``.

Prefabs
~~~~~~~

A prefab in Unity is a reusable version of a GameObject. Its very similar to something like Tree Model.
You export a Tree Model once, and you can use it in 30 different places. But in Unity, if you just drag it onto the scene, it does not have any of the components that you assigned to it.

**Prefabs fix this problem**

Prefabs are GameObjects that store all the components, and the data about that component. You can edit one Prefab, and every model of it in the scene will update.

**How to Create a Prefab:**

1. Prepare Your GameObjectCreate the object: 
   * Right-click in the Hierarchy window to create a 3D object, 2D sprite, or an Empty GameObject.
   * Configure it: Customize the object in the Inspector window. 
   * Add scripts, materials, colliders, or physics components.
   * (Optional) Group multiple objects: If you want a complex prefab (like a multi-part vehicle or character), make an Empty GameObject the "Parent" and drag the individual components inside it.
2. Convert It Into a Prefab
   * Organize: In your Project window, right-click inside the Assets folder and choose Create -> Folder. 
   * Name it Prefabs to keep your project organized.
   * Drag and drop: Left-click and hold your configured GameObject from the Hierarchy. Drag it down into your new Prefabs folder in the Project window.
3. Verify the Visual CuesBlue Text / Icon: 
   * The text and cube icon next to your GameObject in the Hierarchy will turn blue. This confirms that the object in your scene is now a "Prefab Instance" linked to your asset file.Asset file: A new file with the .prefab extension will appear in your Project folder.