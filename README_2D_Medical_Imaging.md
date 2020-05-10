# Deep Learning On 2-Dimentional Images

## 1. What is 2-Dimentional image ? 
One type of picture you can come across in real life is the two-dimensional one. The two dimensions depicted are length and width and the objects on the picture are flat.

<p align="center">
<img alt='cat' src='https://vignette.wikia.nocookie.net/animal-jam-clans-1/images/e/e7/2d.jpg/revision/latest?cb=20160919185703' width=400 aling=center></p>



## 2. How to handle these data ?
There are many libraries in Python to handle these kind of data:
  1. [Keras](https://keras.io/)
  2. [Tensorflow](https://www.tensorflow.org/tutorials/)
  3. [cv2](https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_gui/py_image_display/py_image_display.html)
  


## 3. How these model work ?

![picture alt](https://www.researchgate.net/publication/314282902/figure/fig1/AS:469481303613440@1488944473917/Architecture-of-the-proposed-CNN-model-with-2-convolutional-layers.png "Title is optional")



Convolutional Neural Network is a neural network consists of convolutional layer, pooling layer (max pooling or average pooling but max pooling is preferable), fully connected layer and at last a softmax pooling

Object_detection.py explains how to create a simple convnet using keras framwork.



## 4. Area of application ?
1. Medical problems
    1. MRI dataset
    2. CT Scan
    3. Xray Scans etc.
    4. InfraRed Images
2. Thermal images
3. Satellite images etc.


## 4.1 Medical Problems
<p aling="center">
<img alt="medical imaging" src="https://www.researchgate.net/profile/Nilanjan_Dey3/publication/312222298/figure/fig2/AS:476035763445761@1490507178297/Association-between-the-electromagnetic-spectrum-and-the-medical-modalities.png"></p>



### 4.1.1 MRI/CT-Scan/X-rays dataset
#### MRI Background

Magnetic Resonance Imaging (MRI) is the most common diagnostic tool brain tumors due primarily to it's noninvasive nature and ability to image diverse tissue types and physiological processes. MRI uses a magnetic gradient and radio frequency pulses to take repetitive axial slices of the brain and construct a 3-dimensional representation. Each brain scan 155 slices, with each pixel representing a 1mm<sup>3</sup> voxel.  
<p align="center">
<img alt="Basic MRI Workflow" src="https://github.com/naldeborgh7575/brain_segmentation/raw/master/images/MRI_workflow.png" width=450>
<img alt="3D rendering produced by T2 MRI scan" src="https://github.com/naldeborgh7575/brain_segmentation/raw/master/images/t29_143.gif" width=250>  </p>


#### CT-Scan Background
A computerized tomography scan (CT or CAT scan) uses computers and rotating X-ray machines to create cross-sectional images of the body. These images provide more detailed information than normal X-ray images. They can show the soft tissues, blood vessels, and bones in various parts of the body. [(Read more...)](https://www.healthline.com/health/ct-scan)
<p align="center">
<img alt="Basic MRI Workflow" src="https://caraccidentsinorlando.com/wp-content/uploads/2017/12/ct-vs-mri.jpg" width=450></p>


#### MRI/CT-Scan/X-rays pre-processing ([code](https://github.com/naldeborgh7575/brain_segmentation/blob/master/code/brain_pipeline.py))

One of the challenges in working with MRI/CT-Scan/X-rays data is dealing with the artifacts produced either by inhomogeneity in the magnetic field or small movements made by the patient during scan time. Oftentimes a bias will be present across the resulting scans, which can effect the segmentation results particularly in the setting of computer-based models.
<p align="center">
<img alt="Bias correction before and after" src="https://github.com/naldeborgh7575/brain_segmentation/raw/master/images/n4_correction.png" width=200>  </p>



#### Dataset
<p align="center">
<img alt="segments of dataset" src="https://github.com/naldeborgh7575/brain_segmentation/raw/master/images/segment.png"></p>


Medical images follow Digital Imaging and Communications (DICOM) as a standard solution for storing and exchanging medical image-data. The first version of this standard was released in 1985. Since then there are several changes made. This standard uses a file format and a communications protocol.

   * File Format — All patient medical images are saved in the DICOM file format. This format has PHI (protected health information) about the patient such as — name, sex, age in addition to other image related data such as equipment used to capture the image and some context to the medical treatment. Medical Imaging Equipments create DICOM files. Doctors use DICOM Viewers, computer software applications that can display DICOM images, read and to diagnose the findings in the images.
   * Communications Protocol — The DICOM communication protocol is used to search for imaging studies in the archive and restore imaging studies to the workstation in order to display it. All medical imaging applications that are connected to the hospital network use the DICOM protocol to exchange information, mainly DICOM images but also patient and procedure information. There are also more advanced network commands that are used to control and follow the treatment, schedule procedures, report statuses and share the workload between doctors and imaging devices.


#### [Data file extensions](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3948928/)
  1. <strong>.dcm - handeled by pydicom library</strong>
  2. .nii
  3. .mnc
  4. .img and .hdr
  
#### Python library that handel these data
   * A very popular python package used for analyzing DICOM images is [pydicom](https://pydicom.github.io/).
You can easily install pydicom via command prompt


   <code>pip install pydicom</code>

   * Another library is [MedPy](https://pypi.org/project/MedPy/).
   
   <code>pip install nibabel pydicom medpy</code>
   
   
   * You can find such data from [kaggel competion](https://www.kaggle.com/c/data-science-bowl-2017/data)
   
   * [How to manipulate and vectorize data](https://www.kaggle.com/gzuidhof/full-preprocessing-tutorial)
   
   * Video tutorial on such data can be found [here](https://www.youtube.com/watch?v=KlffppN47lc)
   * [Simple vectorization process for dicom images](https://github.com/Deep-Mind-Hive/2D-imaging-DL/blob/master/vectorizing.py)
   
   

### 4.1.2 InfraRed Image dataset

#### Infrared Background
In infrared photography, the film or image sensor used is sensitive to infrared light. The part of the spectrum used is referred to as near-infrared to distinguish it from far-infrared, which is the domain of thermal imaging. Wavelengths used for photography range from about 700 nm to about 900 nm. Film is usually sensitive to visible light too, so an infrared-passing filter is used; this lets infrared (IR) light pass through to the camera, but blocks all or most of the visible light spectrum

<p align="center">
<img alt="InfraRed image" src="http://www.thermomed.org/images/rost-regulation_470.jpg" ></p>

#### Libraries for python
   1. [Pyradi](https://pypi.org/project/pyradi/)
       <br> <code>pip install pyradi</code>
   2. [Spy](http://www.spectralpython.net/) <bR> <code>pip install spectral</code>
   3. [Rampy](https://github.com/charlesll/rampy)<br><code>pip install rampy</code>



[White paper for reference.](https://sci-hub.tw/https://ieeexplore.ieee.org/document/7532521)




### 4.2 Thermal Images

Thermal imaging is a non-destructive, non-contact and rapid system. It reports temperature through measuring infrared radiation emanated by an object/material surface. Automated thermal imaging system involves thermal camera equipped with infrared detectors, signal processing unit and image acquisition system supported by computer. It is elaborated in wide domains applications. Extensive focus is directed to the thermal imaging in the medical domain especially breast cancer detection. This chapter provided the main concept and the different applications of thermal imaging. It explores and analyses several works in the light of studding the thermograph. It is an effective screening tool for breast cancer prediction. Studies justify that thermography can be considered a complementary tool to detect breast diseases. The current chapter reviews many usages and limitations of thermography in biomedical field. Extensive recommendations for future directions are summarized to provide a structured vision of breast thermography. 



#### Thermal imaging background

All materials/ objects that are at temperature above -273 degrees C (0 degrees Kelvin) emanate infrared energy. The emitted infrared (IR) energy from the measured object is converted into an electrical signal by imaging sensor. This imaging sensor is in the camera which connected to computer for displaying on a monitor the converted signal as a color or monochrome thermal image. The  IR  is  a form  of  electromagnetic  radiation  that  has  wavelength band  of  0.78  to 1000µm, which are longer than the wavelength of visible light and shorter than the radio waves. Several characteristics of the infrared radiation are similar to visible light, such as: the IR radiation can  be refracted,  focused,  reflected and  transmitted.  The  absorptivity,  emissivity, transmissivity, and reflectivity  of  infrared  radiation  vary for  different  objects/  materials.  Good  absorber  objects  for  the infrared radiation are also good emitters.  


#### Equipment that produces thermal image (Camera)


Thermal  imaging refers  to improve  objects visibility even  in a  dark  environment  by recognizing  the objects' infrared radiation as well as creating an image based on that information. Since, all objects emit heat (infrared energy) as a function of their temperature. This emitted infrared energy is known as the object‘s heat  signature  (Gaussorgues,&  Chomet,  2012).  Generally,  the  emitted  radiation  is  directly proportional to the object temperature (i.e. the hotter an object is, the more radiation it emits). Therefore, a heat sensor is required to detect tiny differences  in temperature. This thermal sensor  is essentially a thermal infrared (IR) camera (thermal camera) that collects the infrared radiation on the surface of the objects  under  investigation  and  produces  an  electronic  image  based  on  the  temperature  differences information. Additionally, thermal camera can detect different objects in the same view based on the object's different temperature, which make them appear as distinct objects in a thermal image.  

[For more mathematical details](https://www.researchgate.net/publication/312222298_Thermal_Imaging_in_Medical_Science)
<p align="center">
<img alt="thermal image" src="https://s3-media1.fl.yelpcdn.com/bphoto/zlyM4CeCZVcz_LcmwOy4bQ/ls.jpg"></p> 



### 4.3 Satellite Images

<p align="center">
<img width=500 alt="satellite images" src="https://cdn-images-1.medium.com/max/1200/0*iRgiB6y8atMchG0o.jpg"></p>

1. Satellite imagery are images of Earth or other planets collected by imaging satellites operated by governments and businesses around the world. Satellite imaging companies sell images by licensing them to governments and businesses such as Apple Maps and Google Maps.
2. Satellite images are one of the most powerful and important tools used by the meteorologist. They are essentially the eyes in the sky. These images reassure forecasters to the behavior of the atmosphere as they give a clear, concise, and accurate representation of how events are unfolding. Forecasting the weather and conducting research would be extremely difficult without satellites. Data taken at stations around the country is limited in its representations of atmospheric motion. It is still possible to get a good analysis from the data, but because the stations are separated by hundreds of miles significant features can be missed. Satellite images aid in showing what can not be measured or seen. In addition the satellite images are viewed as truth. There is no chance for error. Satellite images provide data that can be interpreted "first-hand".


#### Libraries of python
  1. [geoio](https://pypi.org/project/geoio/)
 
      <code>pip install geoio</code>
      
  2. [raster vision](https://github.com/azavea/raster-vision)



### Difference between Raster and Vector Images

| Raster Images | Vector Images |
| :--- | ---:|
|raster graphics are composed of pixels | vector graphics are composed of paths |
| A raster graphic, such as a gif or jpeg, is an array of pixels of various colors, which together form an image | A vector graphic, such as .svg, .eps file or Adobe Illustrator file, is composed of paths, or lines, that are either straight or curved.|
| Raster graphics become "blocky," since each pixel increases in size as the image is made larger. This is why logos and other designs are typically created in vector format -- the quality will look the same on a business card as it will on a billboard. | The data file for a vector image contains the points where the paths start and end, how much the paths curve, and the colors that either border or fill the paths. Because vector graphics are not made of pixels, the images can be scaled to be very large without losing quality. |



## 5. Geometric, Photometric and Morphological transformations

### 5.1 Geometric transformation

The functions in this section perform various geometrical transformations of 2D images. They do not change the image content but deform the pixel grid and map this deformed grid to the destination image. In fact, to avoid sampling artifacts, the mapping is done in the reverse order, from destination to the source. That is, for each pixel (x, y) of the destination image, the functions compute coordinates of the corresponding “donor” pixel in the source image and copy the pixel value:
<p align = "center">{dst} (x,y)= {src} (f_x(x,y), f_y(x,y))</p> 

#### Library for Such operation

##### [OpenCv](https://docs.opencv.org/2.4/modules/imgproc/doc/geometric_transformations.html)
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
  
  
  



