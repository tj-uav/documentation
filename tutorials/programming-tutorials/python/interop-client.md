---
description: Interop client usage tutorial
---

# Interop Client

## Setup

1. Clone AUVSI Interop \([https://github.com/auvsi-suas/interop](https://github.com/auvsi-suas/interop)\) into your UAV folder
2. CD into _interop/client_
3. Install the requirements \(`pip install -r requirements.txt --user`\)
4. Copy _interop/proto_ into _interop/client/proto_
5. Download protoc.exe file from Google Drive \(TJUAV/Programming\) and move it to _interop/client_ 
6. Install protobuf \(`pip install protobuf`\)
7. Run _setup.py_ in _interop/client_ \(`python setup.py install`\)
8. Open configure.sh in an editor and delete line 7 \(`source ${CLIENT}/venv2/bin/activate`\)
9. Configure environment variables \(`./configure.sh`\)
10. If using Windows, this will not work unless you use Git Bash or install Cygwin
    1. Git Bash install: [https://gitforwindows.org/](https://gitforwindows.org/)
    2. Cygwin install: [https://cygwin.com/install.html](https://cygwin.com/install.html)
11. Open up a python terminal and run: `from auvsi_suas.interop import interop_api_pb2`
12. If you don't see a ModuleNotFoundError, you are good to go



