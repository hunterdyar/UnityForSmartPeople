---
id: 37
title: Unity Building Blocks
layout: default
parent: Fundamentals
nav_order: 0
categories:
  - Fundamentals
tags:
  - basics
---
A Unity project is made up of four main things:

  1. [Scenes](what-are-unity-scenes.md)
  2. [GameObjects](what-are-gameobjects.md)
  3. [Components](what-are-components.md)
  4. [Assets](what-are-assets.md)

Click on each for an introduction to each part, and read on to learn about how they all relate to each other.

It&#8217;s useful to understand the hierarchy here. A **project** is a collection of **scenes**, and scenes are collections of **GameObjects**. Each **GameObject** has a number of **Components** attached to it, and components utilize **Assets.**

## Scenes

A [scene](what-are-unity-scenes.md) is a three dimensional environment. It&#8217;s a Cartesian coordinate System, 3D or 2D, depending on the game.

## GameObjects

A [GameObject](what-are-gameobjects.md) is anything in the game. For an object to be in the game, it needs to be in the scene, and thus it has some location in space. The object might just be something that plays background music &#8211; it doesn&#8217;t always need to be visible, it will still technically exist in the scene somewhere. These sorts of &#8220;management&#8221; objects that one would think of as existing outside of the scene are, in Unity, just part of the scene. If you can&#8217;t see them and they don&#8217;t take up space for the physics system, then who cares?

Every GameObject has at least one component: The [Transform component](the-transform-component.md). The transform component stores the information of where they object is in 3D space. Because every object exists in the scene, they need the Transform component. You can&#8217;t delete it.<figure class="wp-block-embed-youtube wp-block-embed is-type-video is-provider-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio">

<div class="wp-block-embed__wrapper">
</div></figure> 

## Components

A [component](what-are-components.md) is, in most cases, a behavior. Adding them to a GameObject makes the GameObject do something. You could add a Sprite Renderer component to a 2D project to make the gameObject appear in the scene as an image. Light components will create various types of light sources, and Camera components give the player a perspective with which to view the game from. 

In order to see the 2 or 3 dimensional space full of stuff, we need a camera. A camera does what it does in real life. From a single point, it takes what is visible in front of it and projects it onto a 2 dimensional rectangle: the computer screen when we play the game. We could put the camera where the main player would be for a First Person game, behind some 3D model of the player for third-person games, or just leave it sticking out in space. Frankly, we can do whatever the hell we want with the camera. Sometimes I like attaching it to unexpected objects. 

Once I was making a golf game, and I didn't have a model of a golf club. I quickly put a camera on the end of an &#8220;invisible&#8221; stick (I rotated it around a point), and when you swung to hit the ball, it was like hitting the ball with your face. Later I put the camera &#8220;inside&#8221; the ball, and you got to fly around. I forgot to lock the camera from rotating, so when you hit the ball the entire world turned into a nauseating spinning mess. The gold ball object and the camera object are, in this case, the same. One gameObject with multiple components.

Almost every game will need a [camera](camera-component.md). If there is only one camera component in the scene, then Unity will automatically use that camera to display content to the player. This is useful, we don&#8217;t often need to &#8220;set&#8221; a main camera. (TIP: if you wan to do fancy camera stuff, go install [cinemachine](https://assetstore.unity.com/packages/essentials/cinemachine-79898)).

In the [Scene view](../interface/the-scene-view.md), we are looking at the scene, so we have a &#8220;camera&#8221; but that&#8217;s just part of the editor. There is the camera that is attached to a GameObject (&#8220;Main Camera&#8221; by default when you create a scene). 

#### Assets

Finally, we have assets. [Assets](what-are-assets.md) are files on our hard drive that the game uses. Things like images, 3D models, sounds, and so on. Without assets, out game wouldn&#8217;t be very much. Just lots of &#8216;primitives&#8217; (like cubes or spheres). They are stored in an Assets folder, accessed through the [project window](../interface/the-project-window.md), and referenced by [components](what-are-components.md).