=========================
Unity UI Toolkit & Events
=========================

This page covers Unity's UI Toolkit system

UI Toolkit Overview
~~~~~~~~~~~~~~~~~~~

UI Toolkit is Unity's modern UI framework inspired by standard web technologies (HTML/CSS). Instead of GameObjects and Canvases, it uses an asset-based visual tree structure made of UXML layout files and USS stylesheets.

Core UI Toolkit Elements
~~~~~~~~~~~~~~~~~~~~~~~~

**UIDocument**: The MonoBehaviour component attached to a GameObject that loads and renders a UXML file into the scene.

**UXML (UI XML)**: The asset file that defines the structure and hierarchy of your UI elements (similar to HTML).

**USS (UI Style Sheets)**: The stylesheet asset that controls the visual appearance, layout, and styling of elements (similar to CSS).

**Label**: Visual element used to display dynamic or static text.

**Image / VisualElement**: The core building block for visual containers, icons, backgrounds, and panels.

**Button**: Interactive element that listens for click events and runs C# callbacks.

**Flexbox Layout**: The layout engine used by USS to automatically align, distribute, and scale elements across screen sizes.

UI Toolkit Interaction Patterns
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Querying elements from the ``rootVisualElement`` in C# allows you to bind events and manipulate properties dynamically.

Querying elements from the ``rootVisualElement`` in C# allows you to bind events and manipulate properties dynamically.

* **Button Events**
  
  Set up callbacks for clicks or interactions in menus, settings, and dialogue options.
  
  * *Code:* ``button.RegisterCallback<ClickEvent>(OnButtonClicked);`` or ``button.clicked += OnButtonClicked;``

* **Updating Text**
  
  Query a text element to display real-time player scores, timers, or status updates.
  
  * *Code:* ``root.Q<Label>("Score").text = "100";``

* **Health Bars**
  
  Modify style properties to drive custom progress bars, health meters, or stamina indicators.
  
  * *Code:* ``healthBar.style.width = Length.Percent(75);``

* **Inventory UI**
  
  Dynamically populate lists or grids for item storage, shop screens, or equipment slots.
  
  * *Code:* Use ``ScrollView`` or ``ListView`` bound to C# data collections.

* **Pause Menus**
  
  Toggle visibility styles to show overlays, sub-menus, or pause active gameplay.
  
  * *Code:* ``menu.style.display = DisplayStyle.None;``

`Unity Documentation - UI Toolkit <https://docs.unity3d.com/6000.3/Documentation/Manual/UIElements.html>`_