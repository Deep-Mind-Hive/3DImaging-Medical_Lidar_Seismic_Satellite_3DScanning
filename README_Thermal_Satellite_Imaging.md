# Thermal Images

Thermal imaging is a non-destructive, non-contact and rapid system. It reports temperature through measuring infrared radiation emanated by an object/material surface. Automated thermal imaging system involves thermal camera equipped with infrared detectors, signal processing unit and image acquisition system supported by computer. It is elaborated in wide domains applications. Extensive focus is directed to the thermal imaging in the medical domain especially breast cancer detection. This chapter provided the main concept and the different applications of thermal imaging. It explores and analyses several works in the light of studding the thermograph. It is an effective screening tool for breast cancer prediction. Studies justify that thermography can be considered a complementary tool to detect breast diseases. The current chapter reviews many usages and limitations of thermography in biomedical field. Extensive recommendations for future directions are summarized to provide a structured vision of breast thermography. 



## Thermal imaging background

All materials/ objects that are at temperature above -273 degrees C (0 degrees Kelvin) emanate infrared energy. The emitted infrared (IR) energy from the measured object is converted into an electrical signal by imaging sensor. This imaging sensor is in the camera which connected to computer for displaying on a monitor the converted signal as a color or monochrome thermal image. The  IR  is  a form  of  electromagnetic  radiation  that  has  wavelength band  of  0.78  to 1000µm, which are longer than the wavelength of visible light and shorter than the radio waves. Several characteristics of the infrared radiation are similar to visible light, such as: the IR radiation can  be refracted,  focused,  reflected and  transmitted.  The  absorptivity,  emissivity, transmissivity, and reflectivity  of  infrared  radiation  vary for  different  objects/  materials.  Good  absorber  objects  for  the infrared radiation are also good emitters.  


#### Equipment that produces thermal image (Camera)


Thermal  imaging refers  to improve  objects visibility even  in a  dark  environment  by recognizing  the objects' infrared radiation as well as creating an image based on that information. Since, all objects emit heat (infrared energy) as a function of their temperature. This emitted infrared energy is known as the object‘s heat  signature  (Gaussorgues,&  Chomet,  2012).  Generally,  the  emitted  radiation  is  directly proportional to the object temperature (i.e. the hotter an object is, the more radiation it emits). Therefore, a heat sensor is required to detect tiny differences  in temperature. This thermal sensor  is essentially a thermal infrared (IR) camera (thermal camera) that collects the infrared radiation on the surface of the objects  under  investigation  and  produces  an  electronic  image  based  on  the  temperature  differences information. Additionally, thermal camera can detect different objects in the same view based on the object's different temperature, which make them appear as distinct objects in a thermal image.  

[For more mathematical details](https://www.researchgate.net/publication/312222298_Thermal_Imaging_in_Medical_Science)
<p align="center">
<img alt="thermal image" src="https://s3-media1.fl.yelpcdn.com/bphoto/zlyM4CeCZVcz_LcmwOy4bQ/ls.jpg"></p> 



### Satellite Images

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
