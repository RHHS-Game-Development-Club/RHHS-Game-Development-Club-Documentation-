===========
Unity Input
===========

This page contains how to accept user input in Unity. 

.. note::

    We use the **new** input system. There is an legacy input system, which has slightly different syntax. 

**Making sure the new Input System is setup**

Go to Edit -> Project Settings -> Player -> Configuration and set Active Input Handling to Input System Package (New) or Both
If its not there, follow the steps below:

1. Go to ``Window > Package Manager``.
2. Change the package source drop-down to **Unity Registry**.
3. Search for **Input System** and click **Install**.
4. Click **Yes** when prompted to restart the editor and activate the new backend.

**Core Concepts of the New Input System**

You will see this on the Unity documentation page, but the New Input system has some core concepts that are neccessary to understand it properly.

============ =========================================================
Concept      Description
============ =========================================================
User         The person that is sending the input signal to the engine
Control      The various buttons/keys a user can press
Action       A description of what the code should be executed when a user presses a certain button
Action Map   A group of differnet actions (such as Jump, Run, Walk, for a Player)
Binding      The connection between the Action and the Control (see Unity Docs for more info)
Action Code  Actual code that happens when that key is pressed
============ =========================================================

**The Setup Workflow**

Setting up the input system always follows the exact same 4-step loop, regardless of what kind of game you are making.

1. **Create the Input Action Asset**
   * Think of this asset as a master database for your controls.
   * Right-click in your Project window -> ``Create > Input Actions``. 
   * Double-clicking this asset opens the visual graph editor.

2. **Group into Action Maps**
   * Divide your game into logical states or contexts.
   * Create separate maps like ``PlayerMovement``, ``Driving``, or ``PauseMenu``.
   * This allows you to completely turn off player movement while a menu is open so inputs don't overlap.

3. **Define Actions and Add Bindings**
   * Inside your map, create an **Action** (e.g., "Fire").
   * Choose its type (a *Button* for taps, or a *Value* like a Vector2 for joysticks/WASD).
   * Click the plus icon on the action to add a **Binding**, then pick the physical hardware keys (e.g., Spacebar, Gamepad South Button).

4. **Connect to C# Scripts**
   * **The Direct Method:** Turn on "Generate C# Class" in the asset's inspector. This turns your visual map into a code file you can reference.
   * **The Hookup:** In your player script, initialize the controls, enable the Action Map inside ``OnEnable()``, and disable it inside ``OnDisable()`` to clean up memory.
   * **The Execution:** Write a normal function (like ``void DoJump()``) and subscribe it to your action's event (e.g., ``controls.Player.Jump.performed += ctx => DoJump();``).

`Unity Documentation - Input <https://docs.unity3d.com/6000.3/Documentation/Manual/working-with-gameobjects.html>`_
