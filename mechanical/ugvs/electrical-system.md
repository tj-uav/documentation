# Electrical System

![](../../.gitbook/assets/image%20%2848%29.png)

This is a schematic of the wiring. Check the link below for the most updated version and read ahead for an explanation of the components.

{% embed url="https://docs.google.com/drawings/d/1bsmoRou3HQ3EsDoJdr0AsBylmmCoy0MUnUAX7iwoFjQ/edit" %}

Important Information:

* The Kill Switch kills the power to both of the servos and \(unfortunately\) the telemetry module. It was necessary in the case that the SPARTA UGV would "go rogue" and make it impossible to stop until the battery would die.
* The Telemetry module draws power from the Servo Rail instead of the Pixhawk because we thought that our GPS issues may have been due to the power draw from the Telemetry module. In hindsight, maybe they were to some extent, but we don't know for certain. A consequence of this, however, is that when the servos draw too much power, we have telemetry brownouts. Solution? Bigger battery \(won't fit in the current design so we'll make use without it\).
* The BEC heats up like crazy so don't touch it. I swear I could make boiled eggs with it.

