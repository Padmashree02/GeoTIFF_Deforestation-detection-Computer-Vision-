# Measure the presence of vegetation (forest areas) in the satelite images of geotiff or tif format for the year 2001.

Note -

  > The satelite images are usually forms in satelite imagery that is satelite imaging companies. Hence these images can be used for multiple applications including deforestation there are other cardinal applications also such as in meterology, defence, geology, oceanography, fishing, agriculture, biodiversity conversation etc.

  > To extract information GeoTiff or Tiff types of satelite images, GDAL (Geospatial dat abstraction python library) is used.
  
  > The input image is in the form of .tiff format (formed by satelite space program "Landsat5").

  > This image has 7 rastor bands such as - Blue, Green, Red, Near-infrared, Shortwave-infrared, Shortwave-infrared 1, Thermal, Shortwave-infrared 2.
  
  > NDVI (Normalized Difference Vegetation Index) - computes the vegetation index by taking difference between the visible (Red band) and Near-infrared band or regions.
    It results the index within the range of -1 to 1, where the value 0.3 is as light vegetation and 0.8 is as heavy vegetation 


Libraries - cv2, numpy, matplotlib, gdal

Language - Python

Topics - GeoTiff images, GDAL, Raster bands, NDVI, Threshold mask, Image segmenation

Pipeline -

    > Read the .tif images using GDAL library (gdal.open).
  
    > Pre-processing :-

        * Split the image into each bands using GDAL (GDAl can extract one band at a time).

    > Compute NDVI between the Red and Near-infrared bands. Normalize the NDVI value of the image from -1 to 1 into 0 to 255 (valid image's pixel intensity range).

    > Pass the pre-processed image into the thresholding function by setting the threshold value (as per the image) and set the threshold type as THRESH_BINARY.

    > As a result it returns into setted threshold value and the threshold mask
    
    > Post-processing :-
   
        * calculate the green part by calculating the number of pixels that are non-zero (255=white).
