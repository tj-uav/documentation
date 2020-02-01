# Image Compression

I first tried a bunch of lossless compression methods, including zlib, bz2, and lzma. These methods more or less performed the same. with maximum improvements of only 3 percent. The compression ratios greatly improved after converting the picture's binary to base64, but when converting to base64, the data is always increased in size by 133%. With this in consideration, the increased compression ratios were offset by the increased size of the binary. The different run times and compression sizes are commented in lzmav2.py. 

After seeing no results, I reverted back to lossy compression, and found that it was much faster and compressed the images to a far greater degree. The loss of quality is also practically unnoticeable above a quality threshold of 35. I have the imgc.py file perform lossy compression using PIL. I included a command line argument to allow the user to dynamically specify quality, and if the user does not specify a quality, it is automatically set to 50. It should be kept in mind that higher quality images transmit slower over radio. 

Image sizes can range from 2 to 5 megabytes, and compression ratios on quality=35 are usually on the factor of 4. Detailed instructions, warnings, and comments are coded into the file and are designed to warn the user against mistakes and make them aware to optimizations.

