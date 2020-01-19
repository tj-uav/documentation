# Flashing the NVIDIA Jetson TX2 Orbitty Carrier

**Flashing the NVIDIA Jetson tx2**

You might need to flash the Jetson for a JetPack upgrade, USB access, or missing libraries. Here’s a guide for doing so.

First, you will need Nvidia’s SDK Manager at [https://developer.nvidia.com/nvidia-sdk-manager](https://developer.nvidia.com/nvidia-sdk-manager)

Pay very close attention to the System requirements. It will be a big problem if you don’t match these. From a terminal window, install and run: 

`sudo dpkg -i /sdkmanager-[version].deb`

`sudo apt-get install -f`

`sdkmanager`

Download all the software you want uploaded to the Jetson, but **do not flash from sdkmanager.**

Now, find an appropriate Jetpack version under **L4T Board Support Packages** from [http://connecttech.com/product/orbitty-carrier-for-nvidia-jetson-tx2-tx1/](http://connecttech.com/product/orbitty-carrier-for-nvidia-jetson-tx2-tx1/)

There will be a folder named nvidia in the download location you previously specified. You will have to find this folder, copy the CTI-L4T.tgz file into /nvidia\_sdk/JetPack\_\[VERSION\]/Linux\_for\_Tegra/, and unzip it with:

`tar -xvf CTI-L4T.tgz`

You are ready to flash the Jetson now. Put the device into recovery mode by unplugging power, then power up, press the power button, then press and hold the force recovery button, press the reset button and after 5 sec release the force recovery button. Now connect to the Jetson from your Ubuntu machine with a USB-microUSB cable and flash:

`sudo ./cti-flash.sh`

Follow the script’s instructions, flashing should take between 30 mins to an hour.

