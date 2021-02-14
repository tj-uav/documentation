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

Each point, new or old, is saved as a Node object, which is a class that contains information about a waypoint such as coordinates, altitude, and the parent Node, which is the previous Node on its path. This parent Node can also be used to determine the direction using the tangent function. New nodes are found from the current Node using the neighbors \(nbrs\) function. This method returns a list of Nodes extending from the current Node based on the process described above. Obstacles are also stored in Obstacle objects, which contain coordinates, radius, and height.

When a new point is created, it is added to a data structure called a Priority Queue. A queue is a form of data storage that is First-In-First-Out. In other words, items that are first added to the queue are also the first to leave. A Priority Queue, in addition to being a queue structure, also orders items by group or "priority". Each item is a part of a group that is ordered by priority in the Priority Queue. The queue structure is maintained within each group. In this case, the parameter that determines priority is the distance to the goal Node. Nodes that are closer to the goal are prioritized for a potential path. Nodes are not added to the Priority Queue if they result in an intersection with an obstacle.

Given these restrictions, the algorithm starts forming and testing paths extending from the current first Node in the Priority Queue, which is then removed to prevent unnecessary repetition. Thus, the algorithm will attempt to reach the goal while maintaining the shortest distance to the said goal, resulting in the best path possible.

### Pseudocode

a\_star\(root, goal\):

     node = pq.pop\(\)

     for a in successors\(node\):

          if goal\_test\(\):

               return path

          pq.add\(a, distance\)

