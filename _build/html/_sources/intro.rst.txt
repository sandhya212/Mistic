Introduction
============

What is Mistic
--------------
This is a Python tool using the Bokeh library to view multiple multiplex images simultaneously.
The code has been tested on 7-panel Vectra TIFF, 32- & 64-panel CODEX TIFF, 16-panel CODEX QPTIFF, 4-panel CyCIF TIFF,  and 44-panel t-CyCIF TIFF images.

.. image:: figures/Mistic_GUI.jpg
  :width: 600
  :alt: Mistic GUI. **A.** User-input panel where imaging technique choice, stack montage option or markers can be selected, images borders can be added, new or pre-defined image display coordinates
        can be chosen, and a theme for the canvases can be selected. **B.** Static canvas showing the image t-SNE colored and arranged as per user inputs.
        **C.** Live canvas showing the corresponding t-SNE scatter plot where each image is represented as a dot.
        The live canvas has tabs for displaying additional information per image.
        Metadata for each image can be obtained by hovering over each dot.

.. 
 
..

A sample Mistic GUI with user inputs is shown. **A.** User-input panel where imaging technique choice, stack montage option or markers can be selected, images borders can be added, new or pre-defined image display coordinates can be chosen, and a theme for the canvases can be selected. **B.** Static canvas showing the image t-SNE colored and arranged as per user inputs. **C.** Live canvas showing the corresponding t-SNE scatter plot where each image is represented as a dot. The live canvas has tabs for displaying additional information per image. Metadata for each image can be obtained by hovering over each dot.

Motivation behind developing Mistic
-----------------------------------

* Multiplex imaging of tissues, allows the simultaneous imaging of multiple biomarkers on a tissue specimen of interest, and is a critical tool for clinical cancer diagnosis and prognosis. 

* There are many commercial and open-source software to view and process single images where processing could involve normalization, segmentation, tiling, and image processing to extract and prepare single cell images for actual analysis. Many of the images are large data files. 

* The value in simultaneously viewing such multiple images is to get a preliminary overview of existing patterns in the data such as presence of multiple spatially- distributed cell phenotypes, and the tissue architecture. 

* This exploratory understanding will also enable viewing a specific marker expression pattern across all images, helps to identify images expressing a particular phenotype or to select images for subsequent downstream analysis. 

* Mistic aims to fill this gap as there are currently no freely available tools providing this functionality.

Mistic features
---------------------

* Two canvases: 
  
  *   static canvas with the image tSNE rendering 
  
  *   live canvases with tSNE scatter plots for image metadata rendering

* Dropdown option to select the imaging technique: Vectra, CyCIF, t-CyCIF, or CODEX

* Option to choose between Stack montage view or multiple multiplexed images by selecting the markers to be visualised at once

* Option to place a border around each image based on image metadata

* Option to use a pre-defined tSNE or generate a new set of tSNE co-ordinates

* Option to shuffle images with the tSNE co-ordinates

* Hover functionality available on the tSNE scatter plot to get more information of each image

* Save, zoom, etc each of the Bokeh canvases
	
