===============
Unity Animation
===============

This page covers how animations work in Unity, using the Mecanim System.

Animation Overview
~~~~~~~~~~~~~~~~~~

Animations in Unity are made of animation clips. Animation clips are parts of an animation that describes the change in an objects position, rotation, and scale.

They are stored in an animation controller. A controller can control all of the different animations, from idle -> walking -> running, etc.

**Core Animation Components**

* Animator Component: The component attached to a GameObject that references an Animator Controller and assigns an Avatar to drive the character's mesh.
* Animator Controller: A state machine asset used to manage multiple animation clips and handle transitions between them using scriptable parameters.
* Animation Clips: The individual animation assets containing keyframe data for bone movement, positions, or custom property changes over time.
* Avatar: The mapping system that translates a skeleton's bones into Unity's standard muscle model.

Rig Types: Humanoid vs. Generic
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Unity supports two primary rig types when importing 3D models with animations:

============= =================================================== 
Rig Type      Description                                         
============= =================================================== 
Humanoid      Designed for bipedal characters. Maps bones to a standard human skeleton structure.                

Generic       Designed for non-humanoid objects (animals,         
              monsters, vehicles, props, or simple machinery).   
============= =================================================== 

Animator Parameters & Transitions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Transitions dictate when and how the state machine moves from one animation state to another. These are triggered using Animator Parameters:

============= ================= ===================================================
Parameter     Data Type         Typical Use Case
============= ================= ===================================================
Float         Decimal number    Blend trees (e.g., controlling speed for walking/running).
Int           Whole number      State tracking (e.g., current equipped weapon ID).
Bool          True/False        Toggle states (e.g., isGrounded or isCrouching).
Trigger       Action signal     One-off events (e.g., Jump or Attack) that reset upon use.
============= ================= ===================================================

`Unity Documentation - Animation <https://docs.unity3d.com/6000.5/Documentation/Manual/animation-mecanim.html>_`