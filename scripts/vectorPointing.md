---
id: 257
title: Pointing Vectors
parent: Scripts
layout: post
categories:
  - Scripts
---
It is very often useful to find a Vector that points from one object in space to another. 

For example, if we wanted to have a top-down 2D game where the player faces the mouse position, we would need to get the vector that points from the player to the world-space position of the mouse.

The answer is easier than you may think: We subtract positions in space to get the Vector.

```
// A vector that points from an origin position (Vector3) to the target position (Vector3).
Vector3 pointing = target - origin;
```

[Find more practical examples from the "Vector Cookbook" section in the official Unity Manual](https://docs.unity3d.com/Manual/DirectionDistanceFromOneObjectToAnother.html).


