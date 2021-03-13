# Sony α5000

### General Information

The Sony α5000 \(known as the a5000\) is a 20.1 MP camera developed by Sony using an APS-C sensor \(1.53x sensor crop\). 

The α5000 can be controlled using [gphoto2](https://pypi.org/project/gphoto2/).

General specifications can be found [here](https://www.e-consystems.com/4k-usb-camera.asp).

### Information

{% hint style="info" %}
The link for the lens is for the included lens currently on the α5000. 
{% endhint %}

{% file src="../../.gitbook/assets/ilce5000.pdf" caption="α5000 Specifications Sheet" %}

[SELP1650 Lens Information \(Sony Website\)](https://www.sony.com/electronics/camera-lenses/selp1650/specifications)

### Known Issues

* The α5000 may not power on if there is a USB connection to a computer.
* Looping and saving using Python's [gphoto2](https://pypi.org/project/gphoto2/) library may cause the α5000 to reboot. 
* Although most aspects of the camera can be controlled using gphoto2, it is impossible to focus and zoom an attached lens. 
  * The camera can be switched to Autofocus-S \(Single Shot Autofocus\) then back to manual after taking a photo to refocus the camera if necessary.
  * There is no known method of zooming/retracting an attached lens remotely even if the lens allows powered \(i.e. not done by hand\) zooming. There is a zoom value in gphoto2 when tethered but it doesn't seem to do much.

