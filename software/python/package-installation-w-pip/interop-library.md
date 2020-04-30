# Interop Library

**Interop Client Library**

The interop library is how we can communicate with the interop server over python during the competition. For testing purposes, the interop server will be setup on a raspberry pi that we can communicate to over WiFi, however the computer that is communicating with the interop server must have the interop client python library downloaded.

**Download**

First, make sure you download the AUVSI Interop GitHub directory using the command `git clone https://github.com/auvsi-suas/interop.git`  
Make sure you use the git command to download the library so that you can always `git pull` to install new updates in the future.

The steps for installation are similar for both Windows and Linux/MacOS, however there are subtle differences.

**Linux/MacOS  Installation**

1. Go into the interop/client directory `cd interop/client`
2. Install requirements`pip3 install -r requirements.txt --user`
3. Copy interop/proto into interop/client/proto `cp -r interop/proto interop/client/proto` \(If this command doesn't work, simply copy the folder via file explorer\)
4. Install protobuf `pip3 install protobuf`
5. Run setup.py in interop/client `python3 setup.py install`
6. Open configure.sh in an editor and delete line 7 `source ${CLIENT}/venv2/bin/activate`
7. Configure environment variables `./configure.sh`
8. If using Windows, this will not work unless you use Git Bash or install Cygwins
9. Git Bash install: [https://gitforwindows.org/](https://gitforwindows.org/)
10. Check if setup worked with these commands: `python3 from auvsi_suas.proto import interop_api_pb2`

13. If you did not see a ModuleNotFoundError, you are good to go \(edited\)

**Windows Installation**

1. Go into the interop/client directory `cd interop/client`
2. Install requirements

   `pip3 install -r requirements.txt --user`

   * if the above doesn't work, try taking out the --user

3. Copy interop/proto into interop/client/proto `cp -r interop/proto interop/client/proto` \(If this command doesn't work, simply copy the folder via file explorer\)
4. Download protoc.exe file from Google Drive \(TJUAV/Programming\)
5. Copy the protoc.exe file to the directory where your python3 is installed, and place it in the Scripts folder \(for me it's in C:\Users\Srikar\AppData\Local\Programs\Python\Python36\Scripts\)
6. Run setup.py in interop/client `python3 setup.py install`
7. Configure environment variables. Note that this step is different from Linux/MacOS. Search your computer for "Edit the system environment variables." Then, click the "Environment Variables..." button. In the catalog that opens, go to "System Variables" and look for PYTHONPATH. If PYTHONPATH does not exist, create a new system environment variable named PYTHONPATH, otherwise just add to the existing variable. The directory to add is the absolute path of the interop/client directory.

**Confirm the installation**

Check if setup worked with these commands:  
`python3  
from auvsi_suas.proto import interop_api_pb2`

If the setup worked, then you shouldn't encounter a ModuleNotFound error. If you do encounter a ModuleNotFound error, make sure you followed each of the steps above completely, make sure that your PYTHONPATH variable is set to the current location, and make sure that the auvsi-suas folder is located in the interop/client folder.  


