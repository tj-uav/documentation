---
description: Instructions to install the AUVSI interop server library on a raspberry pi
---

# Interop Server \(Complete me!\)

IP Address: 192.168.1.43

\*\*\*\*

**Interop server**

The interop server is how we can receive the competition details \(where the waypoints are, where the obstacles are, etc.\) and submit our telemetry and ODCL data. For testing purposes, the interop server will be setup on a raspberry pi that we can communicate to over WiFi.

**Setup**

\*\*\*\*

**Setup confirmation**



**Usage**

To start the interop server, cd into the directory "~/Downloads/interop/server" and run the command "sudo ./interop-server up"

how to make missions  
stuff u can do as admin  
how to view telemetry data that gets submitted  
how to view odcl data that gets submitted

**FIXING**

Current setup is on raspbian Jesse with docker compose installed from python3.6's pip. To remove all images:

sudo docker rmi -f $\(sudo docker images -a -q\)

Current Dockerfile configuration is from armv7:latest instead of ubuntu:18.04. This avoids the exec format error raised by ./interop-server.sh up. 

If errors involving 'yakkety' arise when building interop, use armv7:16.04 to use xenial distro instead.

