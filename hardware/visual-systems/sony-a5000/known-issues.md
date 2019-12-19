# Known Issues

* The α5000 may not power on if there is a USB connection to a computer.
* Looping and saving using Python's [gphoto2](https://pypi.org/project/gphoto2/) library may cause the α5000 to reboot. 
* Although most aspects of the camera can be controlled using gphoto2, it is impossible to focus and zoom an attached lens. 
  * The camera can be switched to Autofocus-S \(Single Shot Autofocus\) then back to manual after taking a photo to refocus the camera if necessary.
  * There is no known method of zooming/retracting an attached lens remotely even if the lens allows powered \(i.e. not done by hand\) zooming. There is a zoom value in gphoto2 when tethered but it doesn't seem to do much.

