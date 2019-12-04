---
id: 266
title: 'Attributes'
parent: Scripting Basics
layout: post
categories:
  - Scripting Basics
---

# What are Attributes
Attributes are small bits of metadata that change how Unity compiles code for the editor. They are ignored by the game, and only are used by the unity engine, like the Inspector window.

## How To apply an Attribute

Attributes are small statements inside of [square brackets] that go on the lines above a property or method. One property can have a number of attributes, however many are on the lines above it.

Some attributes have properties, these go in a parenthesis after the attribute name, and usually take a string (in double quotation marks) sort of like calling a function. For example, the Header attribute takes a string that we can use to define the title of the header.

[AttributeName("Property")]

[Header("This is a header")]

# Attributes

A full list of attributes can be found by going to [this page](https://docs.unity3d.com/ScriptReference/AddComponentMenu.html) in the Unity documentation, and looking at the sibling pages next to it in the list. Explore! 

A few of my most often used attributes below.

## HideInInspector
[HideInInspector] is my most frequently used attribute. I use this whenever I have a public property that I don't need to edit in the inspector.

## Space
[Space] Just creates a gap in the Unity inspector. Nifty! 

## Header
[Header("Title")] is probably my second most-used attribute, it really helps organize the inspector window. 

## SerializeField
[SerializeField] is genious. Forget everything you thought you knew about public functions. This attribute exposes **private** functions to the inspector, so we can edit them there (their value is serialized). Yet, the function is still private! So other scripts can't access it, and so on. If all you have is a property that is only used by one script, we probably should make it private and use the [SerializeField] attribute on it. 

## ContextMenu
[ContextMenu("Name")] is extremely useful. The context menu of a component is a little gear icon that gives you a dropdown list. Apply this attribute to a function - not a property - and the dropdown list will have a new item, "Name" that *runs the function* right then and there. Without even being in play mode!

I often create little helper scripts that do things like find/assign game objects, generate levels, or clear an object cache I'm using. I especially like it for doing things like finding and assigning game objects, because those don't really need to be done at run-time, its just convenient. We can do it during run-time while editing, and then turn that code off and just run this script before the build.

## ContextMenuItem 
[ContextMenuItem("Name","NameOfFunctionInScript")] on a property will allow you to right clock on the property, and select Name, which will then just execute NameOfFunctionInScript().

Last time I used it, it was to run a GameObject.FindObjectOfType on the property, which saved me lots of time instead of dragging and dropping.

## Text Area Attributes
[TextArea] lets a string be edited more like a text field. Multiple lines, and a scrollbar! Nice. [Multline] Forces a string to give us multiple lines, even if the text doesn't fill it. Useful!

## Range Attribute
Have a float or an int that should only be in a certian range? Give it a [Range(min,max)] attribute! Now the variable will show up as a *slider* in the inspector, instead of as a text entry box.

## Selection Base
I always forget about this one. This is an attribute that we apply to a class, not a property or method. [SelectionBase] means that if we click on the gameObject that has a component with this class (I sometimes make an empty component that is just this), it will select this object's parent instead.

Since I often put graphics as children of parents, this saves me time and frustration.

# More Resources
One of my developer friends swears by the [NaughtyAttributes](https://assetstore.unity.com/packages/tools/utilities/naughtyattributes-129996) editor extension but I've never used it. Personally, I purchased [Odin](https://assetstore.unity.com/packages/tools/utilities/89041) a while back and while I think it's overkill for small projects, It is extremely powerful and useful, if you put the time in to set it up.



