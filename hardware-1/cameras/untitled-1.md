# See3Cam\_CU135

### General Information

The See3Cam\_CU135 \(colloquially known as the "See3Cam"\) is a 13 MP camera developed by e-con Systems, featuring a 1/3.2" sensor. It supports all M10/S-mount lenses, typically used on CCTV systems, provided that the lens supports it's given sensor size or larger. Although this camera is typically shipped with a USB-C port, our camera uses the [micro-USB3](https://images-na.ssl-images-amazon.com/images/I/61ogJoJXjEL._SY355_.jpg) \(standard micro-usb but wider\). It is generally recommended to always use this camera on a USB3 port to ensure maximum throughput.

General specifications can be found [here](https://www.e-consystems.com/4k-usb-camera.asp).

**If you are using `python-opencv`, you must set resolutions before capturing frames:**

```text
cam = cv2.VideoCapture(0)
cam.set(3, WIDTH)
cam.set(4, HEIGHT)
```

**Get all possible resolutions of camera in a Linux Terminal:**

```text
v4l2-ctl --list-formats-ext
```

**Set Exposure Command**

```text
v4l2-ctl -d /dev/video0 -c exposure_absolute=40
```

### Data Sheets

{% hint style="warning" %}
The datasheets about the board are labeled as the USB-C model. Please disregard this, for our model actually uses the micro-USB3 standard.
{% endhint %}

{% hint style="info" %}
The Lens Datasheet is for the included lens currently on the See3Cam. 
{% endhint %}

{% file src="../../.gitbook/assets/e-con\_see3cam\_cu135\_lens\_datasheet.pdf" caption="Lens Datasheet" %}

{% file src="../../.gitbook/assets/e-con\_see3cam\_cu135\_type\_c\_datasheet.pdf" caption="Module Datasheet" %}

{% file src="../../.gitbook/assets/e-con\_see3cam\_cu135\_type\_c\_getting\_started\_manual.pdf" caption="Module Getting Started" %}













