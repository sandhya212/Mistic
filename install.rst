Code Installation
=================

Download Mistic
***************

* ``pip install mistic``

* To download Mistic's code repository, perform one of the three options:
  
  * Download the code repository from `link`_.

  .. _link: https://github.com/MathOnco/Mistic

  * Open a Terminal and at the command line, type: 

  ``$ git clone https://github.com/MathOnco/Mistic.git``

  * Code can also be downloaded from `Zenodo`_. 

  .. _Zenodo: https://doi.org/10.5281/zenodo.5912169

Preload user data
*****************

 
* In the Mistic folder, navigate to /user_inputs folder to upload input files:
  
  * ``Mistic_code/code/user_inputs/``
  
  * Use the /figures folder to upload the multiplexed images
    
    * Example NSCLC dataset is available from `Zenodo_data`_.
  
     .. _Zenodo_data: https://doi.org/10.5281/zenodo.6131933
  
  * Use the /metadata folder to upload the markers.csv and imaging markers of interest as Markers_ids.csv
    
    * Note: For the Stack Montage option, only the markers.csv file is required.
	
  
  * (Optional) Use the /metadata folder to 
    
    * Upload image tSNE co-ordinates as X_imagetSNE.csv
      
      * If no user-generated tSNE co-ordinates are provided, Mistic will generate a set of t-SNE coordinates to render the images
    
    * Upload image metadata such as 
     
      * Cluster labels as Cluster_categories.csv
        
        * If cluster labels are not provided, Mistic will cluster the images using a Bayesian mixture model.
      
      * Patient_ids as Patient_ids.csv
      
      * Treatments as Treatment_catgories.csv
      
      * Patient response as Response_categories.csv 
    
      * If any of these are unavailable, Mistic will use either the randomly-generated or user-provided tSNE points without any color coding i.e. dots are colored in gray.

    * Sample metadata files are provided for reference 


Run Mistic
**********
 
* To run the application, at the command prompt pointing to /code, type
  
  * ``find . | grep .git | xargs rm -rf``
  * ``find . -name ".DS_Store" -delete``
  *  ``bokeh serve --port 5098 --show image_tSNE_GUI``
  * This runs a bokeh server locally and will automatically open the interactive dashboard in your browser at http://localhost:5098/image_tSNE_GUI



