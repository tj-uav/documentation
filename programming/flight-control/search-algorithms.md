---
description: The algorithm used to create an optimal waypoint path around the search area.
---

# Search Algorithms

### **Background**

There are many algorithms out there that can serve this purpose. We have started researching and reading papers on what an optimal algorithm could be, and how we could incorporate it into our system. Here are some specifications for the algorithm:

* Doesn't use too many waypoints
* Allows for maximum footage of the ground from the camera
* Low maximum bank angle

### **Research papers**

Some research papers we've looked at / should look at:  
[https://www.cim.mcgill.ca/~mrl/pubs/anqixu/icra2011\_optcov.pdf](https://www.cim.mcgill.ca/~mrl/pubs/anqixu/icra2011_optcov.pdf)  


## **Algorithms**

### **Sine wave function**

The sine wave search algorithm is basically just drawing a sine wave over the search area. This idea is useful because it allows for a low bank angle during turns. However, the sine function doesn't do a good job of covering all of the ground.

* Doesn't use too many waypoints ✅
* Allows for maximum footage of the ground from the camera [❌](https://emojipedia.org/emoji/%E2%9D%8C/)
* Low maximum bank angle ✅

### **Search by rows**

The idea of searching by rows is a simple idea that comes to mind quickly. It offers many advantages, such as being able to fully  scan the entire field and using very few waypoints \(since the plane will mostly be travelling in a straight line\). However, it will be difficult to implement the turns between rows while keeping the bank angle low, making sure to stay in bounds, AND making sure to search every spot.

* Doesn't use too many waypoints ✅
* Allows for maximum footage of the ground from the camera ✅
* Low maximum bank angl[e ❌](https://emojipedia.org/emoji/%E2%9D%8C/)

