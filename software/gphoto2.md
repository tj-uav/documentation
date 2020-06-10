# gphoto2

### Useful **Commands:**

Trigger capture: `gphoto2 --trigger-capture`

Capture image and download: `gphoto2 --capture-image-and-download`

Battery life: `gphoto2 --get-config d218 | grep Current`

Specify filename: `gphoto2 --capture-image-and-download --filename=PATTERN`

**List of patterns:** 

* %A is day of the week
* %B is month
* %d is day \(number\)
* %H is hour \(military time\)
* %k
* %y year

