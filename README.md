# 3D Models

## Skull reconstruction from CT Scan
The bright side of getting into a bike accident is getting a copy of your own CT scan to play around with. Using the free, open sourece software [3D Slicer](https://www.slicer.org/), I was able to import the raw scan data, adjust pixel thresholding to select bone, perform a little post processing, and output a solid STL file. From there, the model can be further processed to clean up background noise or fill in any undesired gaps.

Since X-ray attenuation is dependent on the density of different tissues, they're primarily used to image bone. This strong contrast makes it easy to perform automated thresholding in converting the series of images to a binary model. However, make sure to manually subtract non-specific signal from things like tooth fillings or metal plates if you're trying to isolate just bone as these dense materials also show up strongly on a CT scan.
