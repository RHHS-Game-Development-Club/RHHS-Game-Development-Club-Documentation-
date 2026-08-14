==============
Unity Physics
==============

This page covers the core components and concepts of Unity's 3D physics system.

Core Physics Concepts
~~~~~~~~~~~~~~~~~~~~~

* **Rigidbody:** The component that places a GameObject under the control of the physics engine. Adding a Rigidbody allows an object to respond to gravity, forces, and torque.
* **Colliders:** Components that define the physical shape of an object for the purpose of physics collisions. Common primitives include Box, Sphere, and Capsule colliders.
* **Triggers:** A property on a Collider (``Is Trigger``). When enabled, the collider no longer acts as a solid physical barrier; instead, it allows other colliders to pass through while firing collision events.
* **Physics Materials:** Assets used to adjust the surface behavior of colliding objects, such as changing friction and bounciness (restitution).
* **Forces:** Vectors applied to Rigidbodies via script (e.g., ``Rigidbody.AddForce``) to accelerate or alter their velocity in world or local space.
* **Gravity:** A global acceleration force (configurable in Physics Settings) applied automatically to any Rigidbody that has ``Use Gravity`` enabled.
* **Collision Detection:** The underlying system that calculates contact between colliders. Modes include Discrete (performance-friendly) and Continuous (prevents fast-moving objects from passing through walls).

**Collisions vs. Triggers**
Understanding when to use physical interactions versus trigger intersections is essential for gameplay logic.

============= =================== ===================== ===================================================
Type          Primary Function    Script Event Call     Use Case Example
============= =================== ===================== ===================================================
Physics       Physical impact     OnCollisionEnter()    A crate bouncing off a floor or a car hitting a wall, & solid blocking

Trigger       Invisible detection OnTriggerEnter()      A player walking over a health pickup or checkpoint area (no blocking)
============= =================== ===================== ===================================================

Key Distinction:

OnCollisionEnter() provides a Collision object filled with physics data (impact point, relative velocity, contact normals). In contrast, OnTriggerEnter() simply passes the Collider component of the object that entered the volume, as no physical impact actually occurred.

`Unity Documentation - Physics <https://docs.unity3d.com/6000.5/Documentation/Manual/rigidbody-physics-section.html>_`