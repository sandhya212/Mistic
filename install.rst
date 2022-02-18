Code Installation
=================

Download Mistic
***************

* Download this code repository from `link`_.

.. _link: https://github.com/MathOnco/Mistic

* Open a Terminal and at the command line, type: 

``$ git clone https://github.com/MathOnco/Mistic.git``

* Code can also be downloaded from `here`_. 

.. _here: https://zenodo.org/record/5912170#.YfrkKljML1I

Preload user data
*****************

 
* In the Mistic folder, navigate to /user_inputs folder to upload input files:
  
  * ``Mistic_code/code/user_inputs/``
  
  * Use the /figures folder to upload the multiplexed images
  
  * Use the /metadata folder to upload the imaging markers of interest as Markers_ids.csv
  
  * (Optional) Use the /metadata folder to 
    
    * Upload image tSNE co-ordinates as X_imagetSNE.csv
    
    * Upload image metadata such as 
     
      * Cluster labels as Cluster_categories.csv
      
      * Patient_ids as Patient_ids.csv
      
      * Treatments as Treatment_catgories.csv
      
      * Patent response as Response_categories.csv 
    
    * Sample metadata files are provided for reference 

* Open a command prompt (or the Terminal application), change to the directory containing /code and type
  
   *  ``pip install -r requirements.txt``


Run Mistic
**********
 
* Upon successful completion of the previous step, Mistic can be run. 
* To run the application, at the command prompt pointing to /app, type
  
  * ``bokeh serve --port 5098 --show image_tSNE_GUI``
  * This runs a bokeh server locally and will automatically open the interactive dashboard in your browser at http://localhost:5098/image_tSNE_GUI


