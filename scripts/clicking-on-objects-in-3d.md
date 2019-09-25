---
id: 256
title: Clicking on Objects
parent: Scripts
layout: post
categories:
  - Scripts
---
I always forget the specifics of this script.

**This method uses the physics system to work, we need whatever we are clicking on to have a collider component.**

First we get a ray that starts at the cameras position and extends forward towards the mouse.

We check if it hit anything, and do the raycast in the same line, since Physics.Raycast will return true or false, accordingly.

The only tricky thing is that if Physics.Raycast is returning a bool, where do we get the information about what we casted into?  The answer is an [out modifier](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/out-parameter-modifier), which basically lets the variable we pass (in this case, &#8220;hit&#8221;) get modified by the function, even though it is outside of the scope of that function (physics.raycast). 

So we have the information we need inside of a RaycastHit object, which is [little more than a bunch of reference variables](https://docs.unity3d.com/ScriptReference/RaycastHit.html), including the collider that we raycasted into.

Now, perhaps, check if the tag of that collider is &#8220;clickableTag&#8221; or whatever you want to do.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">//Put this code inside of some click event.
   // For example, inside of update, inside of 
   //if(Input.GetMouseButtonDown(0)){}

    Ray ray = Camera.main.ScreenPointToRay(Input.mousePosition);
    RaycastHit hit;
    if(Physics.Raycast(ray, out hit, 100)){
        Debug.Log(Debug.Log(hit.collider.gameObject.name));
   }</pre>