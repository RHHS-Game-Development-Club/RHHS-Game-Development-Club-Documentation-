==============
Unity Basics
==============

This page details an overview of Unity. It is going to contain the core concepts, but not explain every detail/code implementation. It will contain a link to the Unity Documentation

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