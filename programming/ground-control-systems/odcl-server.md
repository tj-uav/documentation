---
description: ODCL Server Computer description and code API
---

# ODCL Server

## Code API

### _main.py_

**@app.route**\(filepath\)  
When that filepath is requested by the frontend, the corresponding template is returned and displayed.  
  
**encode\_img**\(img: numpy.array\) -&gt; bytes  
****Returns a bytes encoded version of the image  
  
**decode\_img**\(data: bytes\) -&gt; numpy.array  
Returns a numpy image \(usable by openCV\) from the encoded bytes  
  
**sock\_comms**\(\) -&gt; None  
This method should be running in a thread. It creates the socket connection with each of the ODCL client computers, and continuously listens for incoming data. Upon receiving a submission from and ODCL client, it saves it to the static/ folder.  
  
**real\_update**\(\) -&gt; None  
This method should be running in a thread. It constantly looks for new submissions in the static/ folder. If it finds a new submission, it adds it to the data dict, which contains all submissions received from ODCL computers. This **data** dict is requested by the frontend on a said interval.  
  
**main**\(\) -&gt; None  
This method creates and starts the threads for socket communications and image updating. It also begins the Flask app.

### _main.js_

**refresh**\(\)  
Goes through each of the images. If it's been accepted, then it displays it in the **Accepted** tab. If it hasn't been discarded or accepted yet, then it's displayed in the **Requests** tab. If it's been discarded, then it isn't displayed.  
  
**openTab**\(evt: Event, tabName: str\)  
****Opens the requested tab upon button click, and closes all other tabs.  
  
**fetchSubmission**\(\)  
This function is run at a set interval \(currently every **500 ms**\). It requests the **data** dictionary from _**main.py**_ and checks to see if there are any new requests. If there are, it adds them to the **Requests** tab.  


