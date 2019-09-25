---
id: 254
title: Follow Focus for PostProcessing DOF effect
date: 2019-03-14T04:55:15+00:00
author: hdyar
layout: post
guid: http://unity.hdyar.com/?p=254
permalink: /scripts/follow-focus-for-postprocessing-dof-effect/
categories:
  - Scripts
---
 

The following script can be used with the [post processing stack](https://github.com/Unity-Technologies/PostProcessing/wiki). Editing the script at [runtime](https://github.com/Unity-Technologies/PostProcessing/wiki/Manipulating-the-Stack) is kind of a pain. Attach the script to an object that has the PostProcessing layer, such as the same object you are using for a post processing volume.

Calculate the distance as needed &#8211; I&#8217;m just getting the distance between the camera transform and the player transform, but if you have a larger player, you may want to use a raycast and get the distance to the closest point to the camera.

<pre class="EnlighterJSRAW" data-enlighter-language="generic" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="" data-enlighter-lineoffset="" data-enlighter-title="" data-enlighter-group="">using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.Rendering.PostProcessing;
public class FollowFocus : MonoBehaviour
{
    Transform player;
    public PostProcessVolume m_Volume;
    public DepthOfField m_DOF;
    public float distance = 10f;
    void Start()
    {
        m_DOF = ScriptableObject.CreateInstance&lt;DepthOfField>();
        m_DOF.enabled.Override(true);
        m_DOF.enabled.value = true;
        m_DOF.focusDistance.Override(1f);
        m_Volume = PostProcessManager.instance.QuickVolume(gameObject.layer, 100f, m_DOF);
        player = GameObject.FindGameObjectWithTag("Player").transform;    
    }

    void Update()
    {
        distance = (Camera.main.transform.position-player.position).magnitude;
        m_DOF.focusDistance.value = distance; 
    }

    void OnDestroy()
    {
        RuntimeUtilities.DestroyVolume(m_Volume, true, true);
    }
}
</pre>