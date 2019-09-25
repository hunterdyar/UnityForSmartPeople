---
id: 101
title: What Are Components?
date: 2019-01-18T07:15:12+00:00
author: unity
excerpt: |
layout: post
guid: http://unity.hdyar.com/?p=101
permalink: /fundamentals/what-are-components/
categories:
  - Fundamentals
---
Components are where the real functionality of GameObjects gets implemented. 

The **[Transform](http://unity.hdyar.com/fundamentals/the-transform-component/)** [component](http://unity.hdyar.com/fundamentals/the-transform-component/) is part of every single [GameObject](http://unity.hdyar.com/fundamentals/what-are-gameobjects/) in Unity. You can&#8217;t delete it, and it&#8217;s always there, right at the top. It gives objects positions, rotations, and scales. It also handles how objects can be &#8220;children&#8221; or &#8220;parents&#8221; of each other.

<div class="wp-block-image">
  <figure class="aligncenter is-resized"><img src="http://unity.18.232.137.204.xip.io/wp-content/uploads/sites/2/2019/01/inspector_cameraComponents.png" alt="" class="wp-image-178" width="437" height="236" srcset="http://unity.hdyar.com/wp-content/uploads/sites/2/2019/01/inspector_cameraComponents.png 620w, http://unity.hdyar.com/wp-content/uploads/sites/2/2019/01/inspector_cameraComponents-300x162.png 300w" sizes="(max-width: 437px) 100vw, 437px" /><figcaption>The Default Main Camera in new scenes have three components: Transform, Cameras, and Audio Listener.</figcaption></figure>
</div>

#### Properties

It&#8217;s important to understand the main feature that Components give us: properties. Components add behavior and functionality to GameObjects, but properties makes this useful. We can edit many properties of any GameObject&#8217;s component. The position data in the Transform component are it&#8217;s _properties_. 

There are two types of properties: _Values_ and _References._ Basically, properties are either:

  * Values: variables in a script (numbers, checkboxes/booleans, colors, strings, etc) 
  * References: Telling us which other thing to use. Such as other GameObjects, other Components, or Assets.

For Example, the **audio source** component has a volume property, which is a number (a _value_) telling unity how loud to play the audio, but it also has an AudioClip property. This property is a _reference._ 

#### Editing Properties

Many value properties are just numbers or letters, and editing them is as simple as typing in whatever number we want. Some values, like colors, would be annoying to edit as numbers (do you know the RGBa values for all of the colors you want to use?). Unity gives us special editors for many values. Colors, to continue the example, have a color picker that will be familiar to you if you have used almost any graphics software.

For numerical properties, you can change the value by clicking and dragging left/right on the properties label. I find it especially useful to click and drag on the &#8220;x&#8221;, &#8220;y&#8221; or &#8220;z&#8221; text to the left of the value in the Transform component to quickly shuttle objects around the scene without messing up my scene view.

<div class="wp-block-image">
  <figure class="aligncenter"><img src="http://unity.18.232.137.204.xip.io/wp-content/uploads/sites/2/2019/01/MovingACubeWithLabel-1.gif" alt="" class="wp-image-182" /><figcaption>Clicking and dragging on labels can easily adjust numerical properties.</figcaption></figure>
</div>

Reference properties look like light grey rectangles and have a small circle to the side of them. We can drag and drop files from our assets (ie: the project window) into here to tell components what _thing_ to use. Audio sources need to know what audio clip, sprite renderer&#8217;s need to know what sprite to render, colliders often use physics materials, and so on.<figure class="wp-block-image">

<img src="http://unity.18.232.137.204.xip.io/wp-content/uploads/sites/2/2019/01/DraggingAndDroppingAssetToProperty.gif" alt="" class="wp-image-188" /> <figcaption> Dragging a Physics Material, from the Project window, onto an appropriate property in the Inspector window</figcaption></figure> 

The little circle is the Object Picker, which basically lets us not have to drag and drop from the project window, it opens a window with the possible things from our game that the property could be referencing, and we can quickly select them there without navigating around the project window.<figure class="wp-block-image">

<img src="http://unity.18.232.137.204.xip.io/wp-content/uploads/sites/2/2019/01/UsingTheQuickSelector.gif" alt="" class="wp-image-191" /> <figcaption>Using the Object Picker to quickly grab the desired asset.</figcaption></figure> 

Read about how to edit many types of properties in the [Unity Manual](https://docs.unity3d.com/Manual/EditingValueProperties.html). 

#### Adding Components To GameObjects

With a GameObject selected (Click on it in the Hierarchy or in the Scene view), it&#8217;s components are available to be edited in the Inspector Window. In the [Inspector window](http://unity.hdyar.com/interface/the-inspector/), there is an &#8220;Add Component&#8221; button at the bottom you can use. 

<div class="wp-block-image">
  <figure class="aligncenter is-resized"><img src="http://unity.18.232.137.204.xip.io/wp-content/uploads/sites/2/2019/01/AddingAComponentInTheInspector.gif" alt="" class="wp-image-185" width="226" height="320" /><figcaption>Adding the rigidbody component to a gameobject in the inspector.</figcaption></figure>
</div>

Without using the inspector window, you can use the Component menu at the top menu bar to add a component to a selected GameObject.

A third way to add components to a GameObject is with code. Components can be added and removed during a games run-time.

#### Making Our Own Components

When we make a script for Unity, most of the time that script will behave as a component. In fact, all components are written in C#, and we can even look at their code. Neat! 

#### Common Components

Other fundamental components we will see in most 3D projects include: [Camera](http://unity.hdyar.com/fundamentals/camera-component/), Light,&nbsp;Mesh&nbsp;Filter,&nbsp;Mesh&nbsp;Renderer,&nbsp;Collider&nbsp;Components,&nbsp;and [Rigidbody](http://unity.hdyar.com/fundamentals/rigidbody-component/). 2D games can use components for 3D games, but there are also components specific to 2D. Sprite Renderer&#8217;s are one example. There are also 2D versions of many components (for performance reasons). 

Lets break down something fundamental into the components involved: A Cube.

<div class="wp-block-image">
  <figure class="aligncenter is-resized"><img src="http://unity.18.232.137.204.xip.io/wp-content/uploads/sites/2/2019/01/InspectorWindow_BasicCube-441x1024.png" alt="" class="wp-image-174" width="317" height="737" srcset="http://unity.hdyar.com/wp-content/uploads/sites/2/2019/01/InspectorWindow_BasicCube-441x1024.png 441w, http://unity.hdyar.com/wp-content/uploads/sites/2/2019/01/InspectorWindow_BasicCube-129x300.png 129w, http://unity.hdyar.com/wp-content/uploads/sites/2/2019/01/InspectorWindow_BasicCube.png 461w" sizes="(max-width: 317px) 100vw, 317px" /></figure>
</div>

A cube has 3 Components.

  * Mesh Filter
  * Mesh Renderer
  * Box Collider

You don&#8217;t need to worry about the **mesh filter**. It takes a mesh asset (the file on your computer) and make it usable by the mesh renderer. The specifics of this don&#8217;t matter to us. So much that if you add a Mesh Renderer to a GameObject, Unity will automatically add a mesh renderer.

The **Mesh Renderer** makes the mesh visible to the cameras. Look at it&#8217;s properties: Cast Shadows (on/off), Recieve Shadows, Materials, light probes, and other graphics jargon. All of it affects how the mesh is seen by the camera, in the scene. Useful! 

The third component is a **Box Collider**. This makes the cube _solid_. Without a collider, the box would just be visible, but unity&#8217;s physics system would not be able to calculate if something is colliding with it or not.