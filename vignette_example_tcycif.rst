Vignettes on t-CyCIF data
=========================

We provide example vignettes to help users run Mistic. Check out our :doc:`mistic_exp` page for examples Mistic has been tested on and :doc:`function_flowchart` for a full list of functions Mistic uses. 

t-CyCIF image on Lung adenocarcinoma metastasis to lymph node
*************************************************************
This t-CyCIF image is in OME-TIFF format, 13GB in size with dimensions 10101 x 9666, and has 44 marker channels. To simultaneously test Mistic for scalability, we created duplicates of this image. In :doc:`mistic_exp` 5.3, we use 70 duplicates of this image and render it on Mistic for 6 markers: CD45, Keratin, aSMA, FoXP3, PD-1, PD-L1.

* Download Mistic as described here :doc:`install`

	* Navigate to ``Mistic_code/code/user_inputs/``

* Download data from `link`_. 

.. _link: https://www.synapse.org/#!Synapse:syn17865732/wiki/592782

	*  Go to Files -> DATASET-1 -> LUNG-1-LN -> 40X-> ometiff.

	*  Download ``lung-1-ln_40x.ome.tif`` and place it in the /user_inputs/figures/ folder

	*  Create say 3 copies of this .tif file in the /figures folder
  

* Navigate to the /user_inputs/metadata folder

	* Upload the imaging markers of interest as Markers_ids.csv

		* A sample .csv is provided in the /metadata folder

	* Upload the markers.csv provided by t-CyCIF

		* Go to `link`_.

        	* Go to Files -> DATASET-1 -> markers.csv
  
  	* Optional uploads: 
    
   		 * Image tSNE co-ordinates as X_imagetSNE.csv
   
			* If no user-generated tSNE co-ordinates are provided, Mistic will generate a set of random coordinates to render the images
 
    		 * Cluster labels as Cluster_categories.csv
      
      		 * Patient_ids as Patient_ids.csv
      
   	         * Treatments as Treatment_catgories.csv
      
                 * Patient response as Response_categories.csv 

		 * If any of these are unavailable, Mistic will use either the randomly-generated or user-provided tSNE points without any color coding i.e. dots are colored in gray, for the live panels. 
     
    	* Sample metadata files are provided for reference in the /metadata folder 

* Open a command prompt (or the Terminal application), change to the directory containing /code and type
  
   * ``pip install -r requirements.txt``  
   * ``bokeh serve --port 5098 --show image_tSNE_GUI``
   * This runs a bokeh server locally and will automatically open the interactive dashboard in your browser at http://localhost:5098/image_tSNE_GUI

* From the GUI, choose 't-CyCIF' from the dropdown menu, check the boxes for markers of interest and select other options based on image metadata (for example, border, image layout) and click 'Run'


t-CyCIF image on Primary lung squamous cell carcinoma
*****************************************************

This is an example where Mistic can be used to view a stack montage made up of the individual markers for a single multiplexed image (see :doc:`mistic_exp` 5.4). We show this option on the t-CyCIF image on Primary lung squamous cell carcinoma. This is in OME-TIFF format for all 44 marker channels. 

* Download Mistic as described here :doc:`install`

        * Navigate to ``Mistic_code/code/user_inputs/``

* Download data from `link`_.

        *  Go to Files -> DATASET-1 -> LUNG-3-PR -> 40X-> singletiff.

        *  Download the 44 single channel tifs (``lung-3-pr_40x_x.tif``) and place it in the /user_inputs/figures/ folder


* Navigate to the /user_inputs/metadata folder

        * Upload the markers.csv provided by t-CyCIF

                * Go to `link`_. 

                * Go to Files -> DATASET-1 -> markers.csv

      
* Open a command prompt (or the Terminal application), change to the directory containing /code and type

   *  ``pip install -r requirements.txt``
   * ``bokeh serve --port 5098 --show image_tSNE_GUI``
   * This runs a bokeh server locally and will automatically open the interactive dashboard in your browser at http://localhost:5098/image_tSNE_GUI

* From the GUI, choose 't-CyCIF' from the dropdown menu, select the 'Stack montage' option and click 'Run'

