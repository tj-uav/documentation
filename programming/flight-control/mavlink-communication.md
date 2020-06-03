# Mavlink Communication

The Jetson communicates with the Pixhawk using dronekit, a python library that implements mavlink over serial communication. In order to get started, you need to set some stuff up on the Jetson and the Pixhawk.

## Setup

### Pixhawk setup

Connect the Pixhawk to Mission Planner. Go to parameters, and set SERIAL0\_BAUD to 921 \(921600\) and set SERIAL0\_PROTOCOL to 2. Write these parameters to the Pixhawk. Flash the latest image of Raspbian onto an SD

