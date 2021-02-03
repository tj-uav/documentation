---
description: Overview
---

# Map Stitching

## Overview

Map Stitching is one of the newer tasks that AUVSI SUAS has added to this year's competition. 

### Summary of the rules

* Teams will have to generate a map conforming to the WGS 84 Web Mercator Projection.
* Graded on quality: 100% for high quality \(professional, Google Maps like\) map, 50% for medium quality \(minor stitch errors, varying exposures\) map, 0% for anything else.
* 16:9 aspect-ratio
* Interop server will give a GPS location for the center of the map and a height, in feet, of the length of area that needs to be covered by the height of the image.

### Interpretation

There's two main subtasks that we need to perform for this task: **pathfinding** and I**mage stitching**. 

**Pathfinding** includes deducing the area that needs to be covered, creating an ideal path that will allow us to cover the entire area \(and preferably have redundancy\) and incorporating that path into the existing waypoints path.

**Image stitching** refers to putting together individual images to create a large map of the target area. Image stitching often involves finding overlaps in images and piecing them together. While manual image stitching is possible, we definitely want an autonomous process for this \(or atleast an auto-assited one\).

## Auto-assisted image stitching

**NOTE: This is not yet completed / coded out, and is just an idea that we have right now.**

Auto-assited image stitching would involve the computer quickly guessing where the image should be, and having a user make slight adjustments on the Ground Station. This process should be done live if possible so that we don't get penalized for taking extra time. You can read more about auto-assisted image stitching [here](../../ground-control-systems/auto-assisted-image-stitching.md).

## Autonomous image stitching

There are currently two autonomous image stitching methods that we're using: **SIFT Stitcher** and **Line Detection**.

The **SIFT Stitcher**, which stands for Scale Invariant Feature Transform, uses certain keypoints across the images to map them onto each other.

@Daniel explain line detection

