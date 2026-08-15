============
Unity Audio
============

This page covers the basics of Audio in Unity.

Audio Overview
~~~~~~~~~~~~~~

Audio in Unity works like a real-world recording setup: sound source objects project sound into the scene, and a single listener acts as the microphone/ears to hear it.

**Core Audio Components**

AudioClip: The actual audio file asset (e.g., .wav, .mp3, .ogg) imported into Unity that holds the sound data.

AudioSource: The component attached to a GameObject that plays back an AudioClip in the scene. Controls properties like volume, pitch, looping, and spatial blend.

AudioListener: The component that receives audio from AudioSources and outputs it to the computer's speakers. Note: Only one active AudioListener should exist in a scene (typically attached to the Main Camera).

Audio Mixer: An asset used to route, mix, adjust volume levels, and apply audio effects (like reverb or low-pass filters) across multiple AudioSources.

2D vs. 3D Audio
~~~~~~~~~~~~~~~

The spatial behavior of an AudioSource is determined by its **Spatial Blend** property:

============= =================================================== ===================================================
Audio Type    Spatial Blend Value                                 Typical Use Case
============= =================================================== ===================================================
**2D Sound**  0.0 (Fully 2D)                                      Background music, UI button clicks, or narration. 
              Plays at a constant volume regardless of position.  Ignores listener location.

**3D Sound**  1.0 (Fully 3D)                                      Footsteps, gunshots, or environmental hazards.
              Volume and panning change based on distance         Fades over distance using audio attenuation curves.
              and angle relative to the AudioListener.
============= =================================================== ===================================================

`Unity Documentation - Audio <https://docs.unity3d.com/6000.5/Documentation/Manual/Audio.html>`_