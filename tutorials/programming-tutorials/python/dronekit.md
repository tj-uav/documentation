---
description: Basic dronekit usage tutorial
---

# Dronekit



## Introduction

Dronekit is an extremely useful tool that can be thought of as an easier way to use pymavlink \(which dronekit is built off of\). Dronekit allows you to interface with flight computers \(like the Pixhawk\) over serial, read data from them like yaw and speed, and perform actions like arming and taking off.

The official documentation for dronekit can be found [here](https://dronekit-python.readthedocs.io/en/latest/). This tutorial will only briefly explain dronekit and it's various uses.

## Installation

## Dronekit-sitl

## Basic Usage

To use dronekit, you need to have an actual Pixhawk connected to the device that you're running it from over serial. If you wanna test out your dronekit code locally without any hardware, use dronekit-sitl.

#### Dronekit usage

#### Connecting to a vehicle

To connect to a Pixhawk, use the following script:

```text
from dronekit import connect

vehicle = connect('/dev/ttyAMA0', wait_ready=True, baud=57600)
```

In dronekit's connect\(\) method, the `/dev/ttyAMA0` string is the name of the serial device over which the Pixhawk is connected, and 57600 is the baud rate of the serial connection.

#### Getting / Setting vehicle data

The following [link ](https://dronekit-python.readthedocs.io/en/latest/guide/vehicle_state_and_parameters.html)shows how to get various attributes of the target vehicle, such as params, GPS location, and other attributes that are often displayed on Mission Planner.

To get / set parameters using dronekit, use the `vehicle.parameters` dictionary. For example, you can get parameters using the command `vehicle.parameters['THR_MIN']` and set them using the command `vehicle.parameters['THR_MIN'] = 100`. [This ](https://ardupilot.org/plane/docs/parameters.html)is a link to ArduPlane's full parameter list.

Arming and changing modes also involves setting attributes of the vehicle object, for example `vehicle.armed = True` is used to arm the vehicle and `vehicle.mode = dronekit.VehicleMode("GUIDED")` to switch to guided mode. 

#### Messages

Mavlink, which dronekit is based off of, uses **messages** __to communicate between the flight computer and the companion computer. Dronekit is simply a mediator that implements common messages in an easy-to-use way, for example setting parameters through a dictionary instead of sending **messages**. However, dronekit doesn't have everything already implemented, so there are many times when you have to send a **message** to communicate w/ the device.

Dronekit has a **message factory** that makes it easier to send these  
 messages. For example, to set the velocity of the plane, you could do:

```text
# mavutil must be imported! i.e.: import mavutil
msg = vehicle.message_factory.set_position_target_local_ned_encode(
        0,       # time_boot_ms (not used)
        0, 0,    # target system, target component
        mavutil.mavlink.MAV_FRAME_LOCAL_NED, # frame
        0b0000111111000111, # type_mask (only speeds enabled)
        0, 0, 0, # x, y, z positions (not used)
        velocity_x, velocity_y, velocity_z, # x, y, z velocity in m/s
        0, 0, 0, # x, y, z acceleration (not supported yet, ignored in GCS_Mavlink)
        0, 0)    # yaw, yaw_rate (not supported yet, ignored in GCS_Mavlink)
vehicle.send_mavlink(msg)
```

`MAV_FRAME_LOCAL_NED` is the command used for setting the velocity, but there are a variety of other commands that the Pixhawk can interpret, such as `MV_CMD_DO_SET_ROI` to set the ROI \(region of interest\) of the plane. **Note** that these commands are defined by a packaged named **mavutil** \(which needs to be imported here\), a python package that dronekit is built off of. More info on these commands can be found [here](https://dronekit-python.readthedocs.io/en/latest/guide/copter/guided_mode.html).

### Dronekit-sitl usage



## Common Issues

Note down here any common issues that you come across while using dronekit AND how you fixed them.



