---
description: >-
  Documentation for any important rules to be kept in mind during the
  competition, as well as documentation of any important competition details.
---

# Competition Details

## Competition Description

This year, TJUAV will be competing at the \[AUVSI SUAS 2020 Competition\]\([https://www.auvsi-suas.org/](https://www.auvsi-suas.org/)\). The rules can be found \[here\]\([https://static1.squarespace.com/static/5d554e14aaa5e300011a4844/t/5e3b2a6265c5eb6706dd0054/1580935781061/auvsi\_suas-2020-rules.pdf](https://static1.squarespace.com/static/5d554e14aaa5e300011a4844/t/5e3b2a6265c5eb6706dd0054/1580935781061/auvsi_suas-2020-rules.pdf)\).

## Team Members

There will be two teams present at the competition, the guest team and the competition team, each containing 8 members.

#### Guest Team

Although the guest team will not be able to directly participate in the competition, their presence is vital. The guest team will help setting everything up before the competition \(safety checks, interop server communication, etc.\). Additionally, they get to watch everyone \(including TJ\) compete!

**Competition Team**

The competition team will do everything same as the guest team, but when the time comes, they will be the ones to actually compete. This means they are the only ones who can perform competition tasks.

**Competition tasks**

Although this tasklist isn't permanent, it is approximately what the 8  competition members will be doing during the competition.

1. Safety Pilot
2. Safety Pilot Spotter
3. Main GCS Operator
   1. Should run telemetry interop submission code and obstacle avoidance code
4. Antenna Monitor \(RFD and Antenna Tracker\)
   1. Should startup antenna tracker code for the dish
5. UGV Operator
6. Main ODCL Spotter
   1. Should also keep track of time
   2. Should run ODCL server code and interop submission code
   3. Should give the go-ahead for UGV drop to Jetson
7. ODCL Spotter 1
   1. Should run ODCL client code
8. ODCL Spotter 2

   1. Should run ODCL client code

## Rules

### Weird rules

Last year \(2019\), there were a lot of weird rules that we discovered at the competition, which took away from our mission time and caused confusion. If you remember any important rules we learned last year, list them here.

* GCS display must be in knots \(not meters / second\), MP has a setting for this
* The geofence must always be visible by the GCS judge \(last year this meant we had to stay on the Flight Plan tab, and we were unable to view the data on the Flight Data tab
* The Mission ID for the interop server is provided when you start ur setup time
* The team leader needs to debrief the judges \(5-ish minutes\) on what tasks will be attempted during the flight

### Important rules

Put anything important that you see mentioned in the rules here:

* UGV judge must give the go-ahead dropping UGV
* Although propulsion can't be used for UGV, using a sparrow or something like that w/o propulsion can be used as a guided glider
* There will be multiple people flying at the same time, meaning crashing into another plane at the same time is a possibility
  * Although it is possible that the other plane will be submitting telemetry data, it is not required, and therefore we can't depend on it
* The waypoint flight must be completed before attempting any other tasks. If any tasks \(such as ODCL\) can be completed during the waypoint flight, it is allowed as long as the plane doesn't need to steer off path to complete said task.

## **Debrief**

If there's anything important you remember from last year's competition, list it here

* Make sure you have someone keeping track of time during the competition, THIS IS EXTREMELY IMPORTANT
* Setting up hardware did not take very long, what took long was getting the right MP setting and other tweaks like that, let's make sure we do this kinda stuff beforehand
* We can't be coding at the competition, or bad stuff will happen like last year :\(. All code should be done before competition, and if it's not, then it's not gonna be used during the competition.
* We get to test with their interop server, so let's spend as much time as possible doing that.

