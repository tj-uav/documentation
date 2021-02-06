---
description: >-
  Description of Ground Control Systems, as well as APIs for each system and
  documentation on how to test it.
---

# Ground Control Systems

The Ground Control Systems is the system of computers used to perform any tasks from the ground, including submitting ODCL images, submitting telemetry data, tracking the plane via Mission Planner, and running the Antenna Tracker.

## Block Diagram

TODO: ADD BLOCK DIAGRAM

## GCS Computers

### **ODCL Server Computer**

The ODCL Server computer is responsible for communicating with the Jetson \(receiving geotagged images as well as sending UGV confirmation\), communicating with the ODCL computers \(distributing those images and receiving ROIs\), classifying ODCLs, and communicating with the interop server \(to submit ODCL submissions\).

### **ODCL Client Computers**

ODCL Client computers are responsible for receiving images from the ODCL Server, manually detecting those images, and sending ROIs back to the ODCL Server.  
  
The ODCL Client computers may also be running the auto-assisted ROI code.  
  
The API for this is under the ODCL Client tab.

