---
description: Interop client usage tutorial
---

# Interop Client

## Setup

1. Clone AUVSI Interop \([https://github.com/auvsi-suas/interop](https://github.com/auvsi-suas/interop)\) into your UAV folder
2. CD into _interop/client_
3. Install the requirements \(`pip install -r requirements.txt --user`\)
4. Copy _interop/proto_ into _interop/client/proto_
5. Download protoc.exe file from Google Drive \(TJUAV/Subsystems/Programming\) and move it to _interop/client_ 
6. Install protobuf \(`pip install protobuf`\)
7. Run _setup.py_ in _interop/client_ \(`python3 setup.py install`\)
8. Add the directory to your _interop/client_ folder to your PYTHONPATH environment variable
   1. For me, this directory is _D:/Srikar/UAV/interop/client_
   2. If you don't already have a PYTHONPATH environment variable, then you need to create one.
9. Open up a python terminal and run: `from auvsi_suas.proto import interop_api_pb2`
10. If you don't see a ModuleNotFoundError, you are good to go



