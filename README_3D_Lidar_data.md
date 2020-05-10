# Lidar Data (3D Imaging)

## What is Lidar data?
_Lidar_ (__light detection and ranging__) is an optical remote-sensing technique that uses laser light to densely sample the surface of the earth, producing highly accurate x,y,z measurements. Lidar, primarily used in airborne laser mapping applications, is emerging as a cost-effective alternative to traditional surveying techniques such as photogrammetry. Lidar produces mass point cloud datasets that can be managed, visualized and analyzed.


he major hardware components of a lidar system include a collection vehicle (aircraft, helicopter, vehicle, and tripod), laser scanner system, GPS (Global Positioning System), and INS (inertial navigation system). An INS system measures roll, pitch, and heading of the lidar system.


Lidar is an active optical sensor that transmits laser beams toward a target while moving through specific survey routes. The reflection of the laser from the target is detected and analyzed by receivers in the lidar sensor. These receivers record the precise time from when the laser pulse left the system to when it is returned to calculate the range distance between the sensor and the target. Combined with the positional information (GPS and INS), these distance measurements are transformed to measurements of actual three-dimensional points of the reflective target in object space.


The point data is post-processed after the lidar data collection survey into highly accurate georeferenced x,y,z coordinates by analyzing the laser time range, laser scan angle, GPS position, and INS information.


<p align="center">
<img alt="lidar-demo" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-AA75201F-4A4B-4C66-967E-7F0082864C6B-web.png">
</p>


## Lidar laser returns

Laser pulses emitted from a lidar system reflect from objects both on and above the ground surface: vegetation, buildings, bridges, and so on. One emitted laser pulse can return to the lidar sensor as one or many returns. Any emitted laser pulse that encounters multiple reflection surfaces as it travels toward the ground is split into as many returns as there are reflective surfaces.

The first returned laser pulse is the most significant return and will be associated with the highest feature in the landscape like a treetop or the top of a building. The first return can also represent the ground, in which case only one return will be detected by the lidar system.

Multiple returns are capable of detecting the elevations of several objects within the laser footprint of an outgoing laser pulse. The intermediate returns, in general, are used for vegetation structure, and the last return for bare-earth terrain models.


<p align="center">
  <img alt="" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-0AE5C4B0-4EF6-43F1-B3EE-DC0BBEED4E9A-web.png">
</p>



## Lidar Data Attribute


|Lidar attribute|	Description|
|:---|:---|
|_Intensity_|The return strength of the laser pulse that generated the lidar point.|
|_Return number_|An emitted laser pulse can have up to five returns depending on the features it is reflected from and the capabilities of the laser scanner used to collect the data. The first return will be flagged as return number one, the second as return number two, and so on.|
|_Number of returns_|The number of returns is the total number of returns for a given pulse. For example, a laser data point may be return two (return number) within a total number of five returns.|
|_Point classification_|Every lidar point that is post-processed can have a classification that defines the type of object that has reflected the laser pulse. Lidar points can be classified into a number of categories including bare earth or ground, top of canopy, and water. The different classes are defined using numeric integer codes in the LAS files.|
|_Edge of flight line_|The points will be symbolized based on a value of 0 or 1. Points flagged at the edge of the flight line will be given a value of 1, and all other points will be given a value of 0.|
|_RGB_|Lidar data can be attributed with RGB (red, green, and blue) bands. This attribution often comes from imagery collected at the same time as the lidar survey.|
|_GPS time_|The GPS time stamp at which the laser point was emitted from the aircraft. The time is in GPS seconds of the week.|
|_Scan angle_|The scan angle is a value in degrees between -90 and +90. At 0 degrees, the laser pulse is directly below the aircraft at nadir. At -90 degrees, the laser pulse is to the left side of the aircraft, while at +90, the laser pulse is to the right side of the aircraft in the direction of flight. Most lidar systems are currently less than ±30 degrees.|
|_Scan direction_|The scan direction is the direction the laser scanning mirror was traveling at the time of the output laser pulse. A value of 1 is a positive scan direction, and a value of 0 is a negative scan direction. A positive value indicates the scanner is moving from the left side to the right side of the in-track flight direction, and a negative value is the opposite.|

__Note__ : Additional information is stored along with every x, y, and z positional value.




## What is a point cloud?

Post-processed spatially organized lidar data is known as point cloud data. The initial point clouds are large collections of 3D elevation points, which include x, y, and z, along with additional attributes such as GPS time stamps. The specific surface features that the laser encounters are classified after the initial lidar point cloud is post-processed. Elevations for the ground, buildings, forest canopy, highway overpasses, and anything else that the laser beam encounters during the survey constitutes point cloud data.


<p align="center">
  <img alt="" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-43D0F282-15F1-4A96-ACD0-9F8FBD1F1B9A-web.png">
</p>



## Lidar Point Classification

Every lidar point can have a classification assigned to it that defines the type of object that has reflected the laser pulse. Lidar points can be classified into a number of categories including bare earth or ground, top of canopy, and water. The different classes are defined using numeric integer codes in the LAS files.

Classification codes were defined by the American Society for Photogrammetry and Remote Sensing (ASPRS) for LAS formats 1.1, 1.2, 1.3, and 1.4.

<p align="center">
  <img alt="" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-B28B8ABA-C84C-4759-AFDF-7BF88763CE9E-web.jpg">
</p>


## Types of LIDAR

 ### 1. Airborne
 
  With airborne lidar, the system is installed in either a fixed-wing aircraft or helicopter. The infrared laser light is emitted toward the ground and returned to the moving airborne lidar sensor. There are two types of airborne sensors: 
    
   1. __Topographic__ and 
   2. __Bathymetric__

  #### __Topographic__ :
  
  Topographic lidar can be used to derive surface models for use in many applications, such as forestry, hydrology, geomorphology, urban planning, landscape ecology, coastal engineering, survey assessments, and volumetric calculations.
  
  <p align="center">
  <img alt="" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-DAC09D61-6A8E-4F1D-B164-DB5AECFF2A5C-web.png">
</p>

  #### __Bathymetric lidar__ :
  Bathymetric lidar is a type of airborne acquisition that is water penetrating. Most bathymetric lidar systems collect elevation and water depth simultaneously, which provides an airborne lidar survey of the land-water interface. With a bathymetric lidar survey, the infrared light (traditional laser system) is reflected back to the aircraft from the land and water surface, while the additional green laser travels through the water column. Analyses of the two distinct pulses are used to establish water depths and shoreline elevations. Bathymetric information is very important near coastlines, in harbors, and near shores and banks. Bathymetric information is also used to locate objects on the ocean floor.

<p align="center">
  <img alt="" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-A93C964C-F417-4523-B391-4931C05AFF31-web.png">
</p>


 ### 2. Terrestrial lidar


There are two main types of terrestrial lidar: 
  1. mobile and 
  2. static. 
  
In the case of __mobile acquisition__, the lidar system is mounted on a moving vehicle. In the case of __static acquisition__, the lidar system is typically mounted on a tripod or stationary device. Both lidar sensors consist of eye-safe lasers.

Terrestrial lidar collects very dense and highly accurate points, which allows precise identification of objects. These dense point clouds can be used to manage facilities, conduct highway and rail surveys, and even create 3D city models for exterior and interior spaces, to name a few examples.


<p align="center">
  <img alt="" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-728FDD39-C25A-4464-96F8-DB6A0EED68CC-web.png">
</p>


## Storing lidar data

Originally, lidar data was only delivered in ASCII format. With the massive size of lidar data collections, a binary format called [__LAS__](http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/file-structure-of-las-datasets.htm) was soon adopted to manage and standardize the way in which lidar data was organized and disseminated. Now it is quite common to see lidar data represented in LAS. LAS is a more acceptable file format, because LAS files contain more information and, being binary, can be read by the importer more efficiently.

_LAS_ is an industry format created and maintained by the _American Society for Photogrammetry and Remote Sensing_ (__ASPRS__). LAS is a published standard file format for the interchange of lidar data. It maintains specific information related to lidar data. It is a way for vendors and clients to interchange data and maintain all information specific to that data.

Each LAS file contains metadata of the lidar survey in a header block followed by individual records for each laser pulse recorded. The header portion of each LAS file holds attribute information on the lidar survey itself: data extents, flight date, flight time, number of point records, number of points by return, any applied data offset, and any applied scale factor. The following lidar point attributes are maintained for each laser pulse of a LAS file: x,y,z location information, GPS time stamp, intensity, return number, number of returns, point classification values, scan angle, additional RGB values, scan direction, edge of flight line, user data, point source ID and waveform information.



## What is lidar intensity data?

Intensity is a measure, collected for every point, of the return strength of the laser pulse that generated the point. It is based, in part, on the reflectivity of the object struck by the laser pulse.

Reflectivity is a function of the wavelength used, which is most commonly in the near infrared. The strength of the returns varies with the composition of the surface object reflecting the return.

Intensity is used as an aid in feature detection and extraction, in lidar point classification, and as a substitute for aerial imagery when none is available. Intensity is relative, not quantifiable, therefore you cannot expect the same value off the same target from flight to flight or from elevation to elevation.

If your lidar data includes intensity values, you can make images from them that look something like black-and-white aerial photos. ArcGIS provides the ability to create intensity imagery from lidar data.



<p align="center">
  <img alt="" src="http://desktop.arcgis.com/en/arcmap/10.3/manage-data/las-dataset/GUID-0383FDFE-6B0C-4B69-967A-966F647426C5-web.png">
</p>
