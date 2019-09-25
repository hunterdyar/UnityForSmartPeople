---
id: 96
title: What Are GameObjects?
date: 2019-01-18T06:40:29+00:00
author: unity
excerpt: |
layout: post
guid: http://unity.hdyar.com/?p=96
permalink: /fundamentals/what-are-gameobjects/
simplefavorites_count:
  - "1"
categories:
  - Building Blocks
  - Fundamentals
---
 

The GameObject is the most important concept in Unity. Every object in a game is a GameObject. Scenes are then, at their simplest, lists of GameObjects. 

GameObjects are the Characters, items, background objects, obstacles, platforms, menus, trees, sources of audio, buttons, lights, cameras, and so on.

On it&#8217;s own, a GameObject is &#8230; nothing? A name, a position in space. It doesn&#8217;t _do_ anything. To make it do things, we give GameObjects **components**. Think of these as properties, or behaviors. 

As you can read in [Unity Manual:](https://docs.unity3d.com/Manual/class-GameObject.html) 

<blockquote class="wp-block-quote">
  <p>
    &#8220;<strong>GameObjects</strong> are the fundamental objects in Unity that represent characters, props and scenery. They do not accomplish much in themselves but they act as containers for <strong>Components</strong>, which implement the real functionality.&#8221;
  </p>
  
  <cite><a href="https://docs.unity3d.com/Manual/class-GameObject.html">Unity Manul: Creating Gameplay>GameObjects>GameObject</a></cite>
</blockquote>

We can&#8217;t get very far with just GameObjects. We need to add **Components,** the most important of which may be the **Transform** component.