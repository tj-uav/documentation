---
description: Isolates the properties of a cropped image
---

# targetIsolation.py

### Intent

### Methods

#### main\(\)

A tester method that allows direct interaction with targetIsolation.py's methods without the need of creating an additional helper file.

#### isolate\(roiCrop\)

A shorthand method that returns the output of every method in this file.

#### checkDependencies\(\)

Ensures that all files that must exist in CV\_DATA for targetIsolation.py to work actually exist.

#### checkMainDependencies\(\)

Checks for dependencies used in the main\(\) method.

#### isolateTarget\(croppedimage\)

Removes the background of the target by means of sampling the edge regions for colors.

#### isolateLetter\(target, mask\)

Takes an input from isolateTarget\(\) and reduces the image to just the letter.

#### quantize\(image, n\)

Reduces each of the color channels of `image` into n colors. Output of this is significantly different than kMeansQuantize\(\).

#### kMeansQuantize\(image, n\)

Uses kMeans to reduce `image` into n distinct colors. May be inconsistent between runs.

#### dominantKMeans\(image, mask\)

Uses kMeans to find the most common color in a masked area of `image`. May be inconsistent between runs.

#### dominantSimple\(image, mask\)

**INEFFICIENT:** Locates the most common color in a masked area of `image`. Consistent between runs.

#### hsv2name\(hsv\)

Inputs a 1x1px HSV image and gets its English name.

#### bgr2name\(bgr\)

**INCONSISTENT WITH `hsv2name`:** Inputs a 1x1px BGR image ad gets its English name. 



