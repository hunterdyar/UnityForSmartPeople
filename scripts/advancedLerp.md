---
id: 257
title: Simple Lerp with Coroutines
parent: Scripts
layout: post
categories:
  - Scripts
---
Here is a more advanced example for lerping with coroutines.

It uses an array of Transforms to hold position references. Transforms are more convenient to edit in a scene, and the array lets us move through more than just two positions.

It uses an enum, which is sort of like an integer with a name, to give the inspector a convenient drop-down set of options for how the object should move through the list. Top to bottom once, loop around, or ping-pong top to bottom then back to the top.

It evaluates an AnimationCurve for the t value of the lerp. This animationCurve can be set in the inspector in some advanced ways. We can use it to easily provide easing to the movement.

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public enum LoopType{
    once,
    loop,
    pingPong
}
public class LerpPositionAdvanced : MonoBehaviour
{
    public Transform[] positions;
    public LoopType loopType;
    public float timeToMove;
    public AnimationCurve curve;
    
    private int nextPosition;
    private int currentPosition;
    private int dir;
    void Start(){
        currentPosition = 0;
        nextPosition = 0;
        dir = 1;
        DoNextMove();
    }

    public void Move()
    {
        StartCoroutine(LerpPos(positions[currentPosition].position,positions[nextPosition].position,timeToMove));
    }
    public void DoNextMove()
    {
        currentPosition = nextPosition;
        nextPosition = currentPosition+dir;

        if(nextPosition == positions.Length || nextPosition == -1)//out of bounds
        {
            if(loopType == LoopType.once)
            {
                return;
            }else if(loopType == LoopType.loop)
            {
                nextPosition = 0;
            }else if(loopType == LoopType.pingPong)
            {
                dir = dir*-1;
                nextPosition = currentPosition+dir;
            }
        }
        Move();
    }
    IEnumerator LerpPos(Vector3 start, Vector3 end, float timeToMove)
    {
        float t = 0;
        while(t < 1)
        {
            transform.position = Vector3.Lerp(start,end,curve.Evaluate(t));
            t = t + Time.deltaTime / timeToMove;
            yield return new WaitForEndOfFrame();
        }
        transform.position = end;
        DoNextMove();
    }
}

```



