## Geometric, Photometric and Morphological transformations

### Geometric transformation

The functions in this section perform various geometrical transformations of 2D images. They do not change the image content but deform the pixel grid and map this deformed grid to the destination image. In fact, to avoid sampling artifacts, the mapping is done in the reverse order, from destination to the source. That is, for each pixel (x, y) of the destination image, the functions compute coordinates of the corresponding “donor” pixel in the source image and copy the pixel value:
<p align = "center">{dst} (x,y)= {src} (f_x(x,y), f_y(x,y))</p> 

#### Library for Such operation

##### [OpenCV](https://docs.opencv.org/2.4/modules/imgproc/doc/geometric_transformations.html)
  1. getAffineTransform
  2. getPerspectiveTransform
  3. getRectSubPix
  4. getRotationMatrix2D
  5. invertAffineTransform
  6. LinearPolar
  7. LogPolar
  8. remap
  9. resize
  10. warpAffine
  11. warpPerspective
  12. initUndistortRectifyMap
  13. getDefaultNewCameraMatrix
  14. undistortPoints
  15. undistort
  
  
  
