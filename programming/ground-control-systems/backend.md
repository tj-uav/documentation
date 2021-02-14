---
description: Built using the Python-Flask framework
---

# Backend

The backend uses helper classes and endpoints to deliver information from the flight computer and imaging system to the interop server and ODCL Client computers.

### **Backend Files**

**config.json** - contains serial port information for the MavHandler and login information for InteropHandler

**mav\_handler.py** - defines the MavHandler class

**dummy\_mav\_handler.py** - defines the DummyMavHandler class, a substitute for MavHandler used when the pixhawk is unavailable.

**interop\_handler.py** - defines the InteropHandler class

**main.py** - runs the backend Flask server and initializes MavHandler and InteropHandler connections

**requirements.txt** - lists python libraries necessary to run main.py. To install these, run “**pip install -r requirements.txt”**.

### **Endpoints**

**/** - homepage, testing endpoint

**/interop/login** - prompts the InteropHandler to attempt a login and returns its success/failure

**/interop/get/&lt;key&gt;** - gets a mission attribute, current keys are: "mission": The entire mission \(json object\)  
"waypoints": List of \[latitude \(float\), longitude \(float\), altitude \(float\)\] lists  
"obstacles": List of \[\]  
"teams": self.teams  
"search": self.search\_grid  
"ugv": self.ugv\_points  
"odlc": self.odlc\_points  
"lost\_comms": self.lost\_comms\_pos

**/interop/telemetry**

**/interop/odlc/id/&lt;dtype&gt;**

**Helper Classes**

**MavHandler**

The MavHandler class is used to communicate with the Pixhawk via the dronekit and pymavlink libraries. Documentation for its methods are here:

**connect\(\)**

