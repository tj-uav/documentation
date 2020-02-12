# ODCL Client

## Code API

### _main.py_

**@app.route**\(filepath\)  
When that filepath is requested by the frontend, the corresponding template is returned and displayed.

**encode\_img**\(img: numpy.array\) -&gt; bytes  
****Returns a bytes encoded version of the image.  
  
**decode\_img**\(data: bytes\) -&gt; numpy.array  
Returns a numpy image \(usable by openCV\) from the encoded bytes.

**submit\_odcl**\(img\_num: int, odcl\_data: dict, img\_crop: dict\)  
Reads the image for the given **img\_num** from the local machine, then crops the image based on the dimensions in **img\_crop**. The cropped image and **odcl\_data** are sent to the server over sockets. **Note:** img\_crop contains the coordinates of the bottom left corner of the cropped image as well as its width and height. odcl\_data contains the classification data for the given image. Both are sent from _**index.js**_ to _**main.py**_ over Flask.  
  
**receiver**\(\) -&gt; None  
When a POST request is received, the JSON file included in the request is read. The image ID,  ODCL data, and the dimensions of the cropped image are passed to _**submit\_odcl**_ to be sent to the server.  
  
**main**\(\) -&gt; None  
This method initializes the socket and connects it to the server for image and ODCL data submission. It also begins the Flask app.

### _index.js_

**openTab**\(evt: Event, tabName: str\)  
****Opens the requested tab upon button click, and closes all other tabs.

**submit\_standard\(\)**  
Generates a dictionary containing all the classification data and the cropped image. This dict is passed to add\_submission to be displayed on the submissions tab of the client, and to server\_post to be sent to the server.

**server\_post**\(post\_dict: dict\)  
****Converts the contents of post\_dict \(classification data\) into a JSON object, which is then sent to the URL at which _**main.py**_  responds to POST requests.   


