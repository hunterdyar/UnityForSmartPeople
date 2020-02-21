---
id: 257
title: Scriptable Object Asset Menu Item 
parent: Scripts
layout: post
categories:
  - Scripts
---

# Creating a Scriptable Object Asset Menu Item
Scriptable objects don't appear in the asset menu by default, which can make them annoying to work with.
You need to add an Attribute right above the class declaration for the scriptable object.

``` 
using UnityEngine;

[CreateAssetMenu(fileName = "Data", menuName = "Category/Item", order = 1)]
public class SomeScriptableObject : ScriptableObject
{
    //
}
``` 
The three properties are fileName, which is the default filename, menuName, which is what you care about editing for the menu, and order, which changes the position in the menu. 

