==============
Unity Raycasts
==============

This page covers the topic of raycasts, which is a common way to detect collisions.

**What is a Raycast?**
~~~~~~~~~~~~~~~~~~~~~~

A raycast is a common way to detect collisions in games. It shoots an invisible ray a certain range (often defined by the Game Developer), and checks if it hits something. If it does, it executes a block of code.

**Parts of a Raycast**
~~~~~~~~~~~~~~~~~~~~~~

There are 2 parts to a Raycast. The Origin and the Direction. They are both pretty self explanatory. 
The origin is where the ray was shot from.
The direction is the direction the ray was shot in (usually stored as a Vector3)

**Raycast Hit struct**
~~~~~~~~~~~~~~~~~~~~~~

When a Raycast hits a GameObject with a collider, it populates this struct with a bunch of information, that can be used to execute more code

The most common parts of the struct that are used are: 

============= ============================
Struct Part   Description 
============= ============================
hit.collider  The specific Collider component intersected by the ray. Use hit.collider.gameObject to access the underlying GameObject.
hit.point     A Vector3 representing the exact world-space coordinates where the ray struck the object.
hit.normal    A Vector3 surface normal vector perpendicular to the struck surface. Crucial for aligning bullet holes or calculating bounce trajectories.
hit.distance  A float measuring the distance from the ray’s origin point directly to the impact point.
hit.transform Shortcut to the Transform component of the hit object or its structural Rigidbody.
============= ============================

**Filtering Raycasts**
~~~~~~~~~~~~~~~~~~~~~~

If you were to just assign a raycast to a player, and it would destory whatever GameObject it looked at, you could destory whatever you clicked. However, we can filter this using a LayerMask.
A LayerMask is a 32-bit interger used (in this case) to filter Raycasts.

**How to use LayerMasks?**

1. Create a LayerMask in the Inspector
2. Assign it (typically with a SeralizeField) in the Inspector to your GameObject
3. Make sure your Physics.Raycast check includes the name of the LayerMask

`Unity Documentation - Raycasts <https://docs.unity3d.com/6000.0/Documentation/ScriptReference/Physics.Raycast.html>`_