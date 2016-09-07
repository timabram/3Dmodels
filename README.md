# 3D Models

## Skull reconstruction from CT Scan
![](/skull_model.jpg)
The bright side of getting into a bike accident is getting a copy of your own CT scan to play around with. Using the free, open sourece software [3D Slicer](https://www.slicer.org/), I was able to import the raw scan data, adjust pixel thresholding to select bone, perform a little post processing, and output a solid STL file. From there, the model can be further processed to clean up background noise or fill in any undesired gaps.

Since X-ray attenuation is dependent on the density of different tissues, they're primarily used to image bone. This strong contrast makes it easy to perform automated thresholding in converting the series of images to a binary model. However, make sure to manually subtract non-specific signal from things like tooth fillings or metal plates if you're trying to isolate just bone as these dense materials also show up strongly on a CT scan.

## Importing Data
From the main menu, click on the **DCM** icon (opens the DICOM browser module). Then, select **Import** and search for the directory that contains the list of images. Hopefully, the metadata has been saved in a way that the DICOM browser will interpret everything correctly. You'll know you had a successful import when the DICOM browser lists a new patient (hopefully the patient you expected) and some other metadata such as *StudyID*, *StudyDate*, *StudyDescription*, etc. Also, you should now see some info under *SeriesNumber*/*SeriesDescription* that list out the different scans (views, locations, etc.). If all this info is visible, click on the patient name and select **Load**. If not, then something went wrong in the data import and 3D slicer may not know how to interpret or link the scan data. I'm sure there's some simple fixes for this, but I haven't looked into this yet.
