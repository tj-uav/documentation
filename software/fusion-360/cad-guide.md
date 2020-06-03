---
description: The basics of how to CAD effectively.
---

# CAD Guide

## Sketches

Sketches are used to model in Fusion 360.  A sketch is a 2d plane you define where you define 2d shapes to be modified in 3d.  By using the project command, sketches can include geometry from outside the plane or the intersections of the plane and 3d geometry.

### Constraints

When making your sketches, make sure your lines are all black. If the lines are blue that means the lines have some range of motion and you can see this for yourself by clicking and dragging the line. If the line isn't fully constrained it may move in an unpredictable way when dimensions are changed. There are many ways to prevent this, and often times you'll need more than just one of the following tools: 

\*insert image\*

You should also use dimensions to parametrize your lines.

## Parameterization

CAD designs change frequently. That's why it's necessary to program variables in your CAD, called parameters, in case any of your dimensions change. To access it, just click on modify, and then change parameters. 

![](../../.gitbook/assets/screen-shot-2020-02-15-at-3.35.16-pm.png)

Parameters must match the dimensions of what they describe. Angular measurement must be made in degrees or radians, lengths in some form of meters, etc.  Another important thing to note is that you shouldn't have to use a calculator to calculate any dimensions. This is because computations can be put directly in your definitions of parameters: addition, multiplication, etc.



## Timeline

Another basic concept in Fusion is a series of events. Many different operations may need to be performed to create complex shapes, and Fusion keeps track of this in the Timeline. Different icons represent different operations, like New Sketch, Extrude, and Revolve. 



