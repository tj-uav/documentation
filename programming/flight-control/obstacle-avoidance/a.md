# A\*

## **Background**

A\* is what is known as an informed search algorithm. There are different types of these algorithms, but their overall purpose is the same. To find the best path between a start and endpoint while given a set of restrictions and/or conditions.

These conditions can include:

* Obstacles in which the path cannot intersect
* Certain points must be reached in a certain order before the goal
* A maximum angle at which the path is allowed to turn

All of these conditions are those used in our own A\* code, where we attempt to find the best and shortest path between each waypoint while avoiding given obstacles.

## Algorithm Overview

The algorithm begins at a given starting waypoint and runs the A\* algorithm with the next given waypoint as the goal. In order to reach the goal, the algorithm tests new waypoints a certain distance from the current position. Using the direction the craft is facing, three new points are created in front of the current point at a previously determined bank angle. For example, if the plane was facing 0 degrees North, the new waypoints could be 50 meters and 30 degrees NW, 0 degrees N, and 30 degrees NE.

Each point, new or old, is saved as a Node object, which is a class that contains information about a waypoint such as coordinates, altitude, and the parent Node, which is the previous Node on its path. This parent Node can also be used to determine the direction using the tangent function. Obstacles are also stored in Obstacle objects, which contain coordinates, radius, and height.

When a new point is created

