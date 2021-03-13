# Laser Cutter



**Formatting**  
Import your file into AutoCAD. Find the page for your plane, click Resources, then download the Full Plans. In a new file in AutoCAD, import the plans as a PDF.

![Select Import PDF from the top left drop down menu](../../.gitbook/assets/image%20%2810%29.png)

![Press Enter to get to the file selection menu](../../.gitbook/assets/image%20%287%29.png)

![Import the first page with the default settings shown above](../../.gitbook/assets/image%20%2831%29.png)

![Import additional pages by selecting &quot;Specify insertion point on-screen&quot;](../../.gitbook/assets/image%20%2818%29.png)

![Insert additional pages to the side of preexisting pages](../../.gitbook/assets/image%20%2829%29.png)

![Type &quot;layer&quot; and press Space to open the layer menu](../../.gitbook/assets/image%20%2814%29.png)

![Click the light bulbs to figure out which layers are for what](../../.gitbook/assets/image%20%289%29.png)

![Freeze the layers you want to keep, then select and delete what&apos;s left](../../.gitbook/assets/image%20%2816%29.png)

![Select the layers that are now empty and delete them except layer &quot;0&quot;, if possible](../../.gitbook/assets/image%20%2817%29.png)

![Now delete any fold references, additional text, and the firewall and control horns that I marked yellow](../../.gitbook/assets/image%20%285%29.png)

![Refer to the legend on the PDF plans, the Tiny Trainer&apos;s is show above](../../.gitbook/assets/image%20%288%29.png)

Foam board is like a sandwich. The bread is paper, and the inside is the foam. A full cut cuts through all three layers, score cut is one paper layer and the foam, leaving one layer of paper left, and a crease cut cuts through only one layer of paper, but no foam.

![Find the color that is being used for a cut. In this case, \(34, 31, 31\)](../../.gitbook/assets/image%20%2833%29.png)

![Type &quot;qselect&quot; and press Space to open the quick select menu. Switch ByLayer Value to &quot;Select Color...&quot;](../../.gitbook/assets/image%20%2828%29.png)

![Switch to True Color tab, change Color model to RGB, and enter the color that was used for cuts](../../.gitbook/assets/image%20%2821%29.png)

![Change all the selected lines to the correct color for cuts. In our case, &quot;Blue&quot;, not an RGB value that is blue](../../.gitbook/assets/image%20%2825%29.png)

Disclaimer: in the image above, the regular cuts were set to red, but that is incorrect. Set them to Blue. Throughout this tutorial, score cuts were mistakenly set to blue, and full cuts were mistakenly set to red. It should be the other way around.

![Looks like some cuts are &quot;ByLayer&quot; type. Qselect these lines to Blue as well](../../.gitbook/assets/image%20%2819%29.png)

![Change all the score cuts to the correct color. In this case, qselect \(235, 28, 35\) to &quot;Red&quot; for score cuts](../../.gitbook/assets/image%20%2834%29.png)

![What&apos;s left is the crease cuts, also known as reference lines. In this case, \(0, 172, 237\) to &quot;Green&quot; or &quot;Cyan&quot;](../../.gitbook/assets/image%20%2826%29.png)

![Merge all layers except &quot;0&quot; to Target layer &quot;0&quot;. You can close the layer menu now](../../.gitbook/assets/image%20%2830%29.png)

![Select all lines, then change to 0.00 mm lineweight](../../.gitbook/assets/image%20%286%29.png)

![Type command &quot;overkill&quot;, select everything, press Enter, and click OK](../../.gitbook/assets/image%20%2820%29.png)

![Save as a 2010 dxf to avoid compatibility issues with other AutoCAD programs in the school](../../.gitbook/assets/image%20%2812%29.png)

![Select everything, drag and drop to the side, then use the &quot;rectang&quot; command](../../.gitbook/assets/image%20%2824%29.png)

![First corner point is 0,0, second is 24,18. Use tab and enter to enter parameters](../../.gitbook/assets/image%20%2811%29.png)

![Use commands &quot;move&quot; and &quot;rotate&quot;. You can also move through selection then drag and drop](../../.gitbook/assets/image%20%2827%29.png)

![Green type selection selects all objects overlapped. Green: left or counterclockwise](../../.gitbook/assets/image%20%284%29.png)

![Blue type selection only selects objects that are completely enclosed. Blue: right or clockwise](../../.gitbook/assets/image%20%2822%29.png)

![Example of a final result, this one actually has the correct colors for score and full cuts](../../.gitbook/assets/image%20%2823%29.png)

Your goal will be to fit all the parts within 18x24 inch rectangles, and as least rectangles as possible. This is because TJ's largest laser cutters can cut 18x24 inches maximum. Your final result should be multiple dxf files that are numbered, each with only one 18x24 rectangle containing parts. Try not to have any parts sit on the edge of the rectangle, as the laser cutter's range is actually slightly less than 18x24.  
  
**Cutting**

![The AutoCAD Print menu](../../.gitbook/assets/autocadprint.JPG)

1. Press Ctrl+P
   1. Change the Printer/plotter name to the laser cutter you are using
   2. Click Properties..., Advanced Settings, and adjust the color settings appropriate to your color scheme \(Red: cut, Blue: score, Green/Cyan: reference\) \*
   3. Change What to plot to Window, then click on two corners of the 18x24 rectangle that are not adjacent
   4. Uncheck Fit to paper
   5. Change Scale to 1:1
   6. Change Plot style table to laser.ctb
   7. Click Apply to Layout
   8. Click Preview... to make sure your lines show up and the plot matches your format
   9. Click OK
2. Put a sheet of 18x24 inch foam board into the laser cutter
3. Click focus and adjust the laser cutter to the correct height
4. Turn on the ventilation and open the air valve
5. Press the green button on the printer to start printing

