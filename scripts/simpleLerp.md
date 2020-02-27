---
id: 257
title: Simple Lerp with Coroutines
parent: Scripts
layout: post
categories:
  - Scripts
---
Here is an example script that uses a coroutine to lerp between two provided positions.

There is some extra code to allow the script to ping-pong back and forth between the positions.

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class LerpPositionSimple : MonoBehaviour
{
    public Vector3 startPosition;
    public Vector3 endPosition;
    public float timeToMove;
    public bool pingPong;
    void Start(){Move();}
    public void Move()
    {
        StartCoroutine(LerpPos(startPosition,endPosition,timeToMove));
    }
    public void MoveFinished()
    {
        if(pingPong)
        {
            Vector3 temp = startPosition;
            startPosition = endPosition;
            endPosition = temp;
            Move();
        }
    }
    IEnumerator LerpPos(Vector3 start, Vector3 end, float timeToMove)
    {
        float t = 0;
        while(t < 1)
        {
            transform.position = Vector3.Lerp(start,end,t);
            t = t + Time.deltaTime / timeToMove;
            yield return new WaitForEndOfFrame();
        }
        transform.position = end;
        MoveFinished();
    }
}
```



