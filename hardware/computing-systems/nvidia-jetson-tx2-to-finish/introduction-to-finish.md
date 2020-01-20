# Introduction

{% hint style="danger" %}
As of late, pip3 is broken on the Jetson. Use python3 -m pip instead.
{% endhint %}

[https://elinux.org/Jetson\_TX2](https://elinux.org/Jetson_TX2) contains some super useful information. Package installation guides are found in the [Deep Learning](https://elinux.org/Jetson_TX2#Deep_Learning) section.

The Jetson can be adjusted for performance or battery life. Check performance mode and processor status with:

`sudo nvpmodel -q --verbose`

Change mode with:

`sudo nvpmodel -m [mode]`

![](../../../.gitbook/assets/image.png)

