# COMPUTER VISION IN GEOSCIENCE: RECOVER SEISMIC DATA FROM IMAGES

## Naive 3D seismic fault segmentation workflow in Python

 This post is mostly to share back with the community what I’ve learned in my playground session with [Kerry-3D Seismic data](https://wiki.seg.org/wiki/Kerry-3D).
 
Kerry-3D is collection of Data provided by the New Zealand Crown Minerals is a prestack migrated final volume. The volume is 1 GBytes. All data are time migrated.
 
Please refer to the 

NOTEBOOK  - 

This notebook aims at presenting a simple example of relative seismic inversion. This notebook uses both the Kerry3D data and the [Volve data](https://www.equinor.com/no/how-and-why/digitalisation-in-our-dna/volve-field-data-village-download.html) as input data to our inversion and we will leverage the open-source segyio and pylops libraries to accomplish our task as follows:

  - Data is read from SEG-Y file using segyio (note that for the Volve data we will have to deal with irregular geometry)
  - Relative seismic inversion is applied by means of pylops.avo.poststack.PoststackInversion
  - Inverted data is saved back to SEG-Y file using segyio
  
https://github.com/equinor/segyio-notebooks/blob/master/notebooks/pylops/01_seismic_inversion.ipynb for 
  
## Want to get access of free loads of 3D Seismic Datasets
 Please access ["The SEG Wiki](https://wiki.seg.org/wiki/Main_Page)
 The SEG Wiki's main mission is to supply scientific materials to the geoscience community.
 
 Well! A sample (An example 3D plot of a subset of Kerry-3D) data and inline and xline displays are below - 
 https://wiki.seg.org/images/6/6e/Kerry3d.png
 https://wiki.seg.org/images/8/8b/Kerry_sidebyside.png
 
## Working with Seismic Data (3D data)
 Ability to work with Seismic Data has been a sore spot for some time. How to go about converting Seismic data (generally SEGY files with .SGY extensions) to numpy arrays/Tensors,  Seismic image processing, and particularly morphological image processing, to the task of fault segmentation, et al? So, think about - 
  - how to read seismic volumes as NumPy arrays?
  - how to manipulate the similarity to create a discontinuity/fault volume?
  - how to write the fault volume to SEG-Y file using re-using the headers from the input file?
  - how to basic Segy editing, such as how to perform manipulations of traces length, both resampling and cutting, etc?
  - how to transfer binary and trace headers in pandas dataframes and visualize headers and data with matplotlib?
  - how to perform Seismic inversion, such as how to download and read a SEG-Y file, perform colored inversion to a portion of the data and saved the inversion result in a brand new SEG-Y?
 
 ** Enters [segyio](https://pypi.org/project/segyio/) , a fast, open-source library, developed precisely to work with SEGY files. The aforementioned whole load of questions get answered by python libraries - [segyio](https://pypi.org/project/segyio/) along with [pylops](https://pypi.org/project/pylops/) and NumPy. ** 
 
## Reference
https://youtu.be/7DnudEsb6hU
 
