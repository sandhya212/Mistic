Quickstart
==========

What is Mistic
--------------
This is a Python tool using the Bokeh library to view multiple multiplex images simultaneously. Currently the code supports 7-panel Vectra images.

.. image:: https://github.com/sandhya212/Mistic_RTD/figures/Mistic_GUI.png
  :width: 600
  :alt: Mistic GUI.a. User-input panel where markers can be selected, images borders can be added, new or pre-defined image display coordinates
        can be chosen, and a theme for the canvases can be selected. b. Static canvas showing the image t-SNE colored and arranged as per user inputs.
        c. Live canvas showing the corresponding t-SNE scatter plot where each image is represented as a dot.
        The live canvas has tabs for displaying additional information per image.
        Metadata for each image can be obtained by hovering over each dot.

.. 
 
..

A sample Mistic GUI with user inputs is shown. a. User-input panel where markers can be selected, images borders can be added, new or pre-defined image display coordinates can be         chosen, and a theme for the canvases can be selected. b. Static canvas showing the image t-SNE colored and arranged as per user inputs. c. Live canvas showing the corresponding t-        SNE scatter plot where each image is represented as a dot. The live canvas has tabs for displaying additional information per image. Metadata for each image can be obtained by hovering over each dot.


Motivation behind developing Mistic
-----------------------------------

Motivation: 

Mistic features
---------------------

* Two canvases: 
  
  *   static canvas with the image tSNE rendering 
  
  *   live canvases with tSNE scatter plots for image metadata rendering

* Option to choose between Stack montage view or multiple multiplexed images by selecting the markers to be visualised at once

* Option to place a border around each image based on image metadata

* Option to use a pre-defined tSNE or generate a new set of tSNE co-ordinates

* Option to shuffle images with the tSNE co-ordinates

* Hover functionality available on the tSNE scatter plot to get more information of each image

* Save, zoom, etc each of the Bokeh canvases
	
