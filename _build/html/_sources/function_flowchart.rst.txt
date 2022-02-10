Functions
=========


.. image:: figures/flowchart_mistic.jpg
   :width: 700
   :alt: Table

..

..

Flowchart sketching flow between functions and processes in Mistic.

get_cell_coords(pt,a)
*********************

	
	Get the coordinates of the cell that pt = (x,y) falls in.
	
       
	.. code-block:: python

		def get_cell_coords(pt,a):
    			return int(pt[0] // a), int(pt[1] // a)


	
	**Parameters:** 

	``pt : float`` 
	2D coordinates of a point

	``a : float``
	scaled minimum distance between cells


	**Output**
	
	``list``
	coordinates of the cell that pt lies in 



get_neighbours(coords,nx,ny,cells)
**********************************
        
	
        Return the indexes of points in cells neighbouring cell at coords.
    	For the cell at coords = (x,y), return the indexes of points in the cells
    	with neighbouring coordinates illustrated below: ie those cells that could 
    	contain points closer than r
	

        .. code-block:: python

                def get_neighbours(coords,nx,ny,cells):
                    # Refer main.py on Github
		     return neighbours



        **Parameters:**

        ``coords : float``
        2D coordinates of a point

        ``nx, ny : int``
        Number of cells in the x- and y-directions of the grid

	``cells : dictionary``
         Dictionary of cells or grid squares: each key is a cell's coordinates, the
         corresponding value is the index of that cell's point's coordinates in the
         samples list (or None if the cell is empty)

        **Output**

        ``neighbours: list``
        List of neighbouring cells for coords




point_valid(pt,a,nx,ny,cells,samples,r)
****************************************

        
        Returns True or False based on if the pt is valid point to be added to samples.
	It must be no closer than r from any other point by checking the cells in its
	immediate neighbourhood.
        

        .. code-block:: python

                def point_valid(pt,a,nx,ny,cells,samples,r):
	            # Refer main.py on Github
                     return True (or False)



        **Parameters:**

        ``pt : float`` 
        2D coordinates of a point

        ``a : float``
        scaled minimum distance between cells

        ``nx, ny : int``
        Number of cells in the x- and y-directions of the grid

        ``cells : dictionary``
         Dictionary of cells or grid squares: each key is a cell's coordinates, the
         corresponding value is the index of that cell's point's coordinates in the
         samples list (or None if the cell is empty)


        ``samples : list``
         List with valid neighbouring coordinates for a given point pt 

	``r : int``
	Minimum distance between samples. Set to 2         

	
	**Output**

        ``boolean``
        Returns True or False if sampled point is eligible to be pt's neighbour




get_point(k, refpt,r,a,nx,ny,cells,samples)
*******************************************

        
	Try to find a candidate point relative to refpt to emit in the sample.
    	We draw up to k points from the annulus of inner radius r, outer radius 2r
    	around the reference point, refpt. If none of them are suitable (because
    	they're too close to existing points in the sample), return False.
    	Otherwise, return the pt.
	
        
	.. code-block:: python

                def get_point(k, refpt,r,a,nx,ny,cells,samples):
		     # Refer main.py on Github
                     return True (or False)



        **Parameters:**

        ``k : int`` 
        number of candidate points sampled arounf the reference point, refpt

        ``refpt : float``
        2D coordinates of the reference point

        ``a : float``
        scaled minimum distance between cells

        ``nx, ny : int``
        Number of cells in the x- and y-directions of the grid

        ``cells : dictionary``
         Dictionary of cells or grid squares: each key is a cell's coordinates, the
         corresponding value is the index of that cell's point's coordinates in the
         samples list (or None if the cell is empty)


        ``samples : list``
         List with valid neighbouring coordinates for a given point pt

        ``r : int``
        Minimum distance between samples. Set to 2


	**Output**

        ``boolean``
        Returns True or False if candidate point is eligible to be refpt's neighbour


.. note:: The above functions: ``get_cell_coords()``, ``get_neighbours()``, ``point_valid()``, ``get_point()`` are modified from 
	https://scipython.com/blog/poisson-disc-sampling-in-python/


button_callback()
*****************

       
        Function that is called when user clicks 'Run' from the GUI
       

        .. code-block:: python

                def button-callback():
                     # Refer main.py on Github
                     return ([p,p1,p2,p3,p4, source, tabs])

        **Output**

        ``p : figure``
        Static figure canvas with the image tSNE

        ``p1, p2, p3, p4 : figure``
        Live canvas with tSNE scatter plots for each of the image metadata

        ``source : ColumnDataSource, dictionary``
        Dictionary of metadata and associated variables (like colour, thumbnail location) for each image which is maintained and
        updated based on user preferences for each 'Run' episode


        ``tabs : Tabs``
        Tabs of Panels where each panel corresponds to an image metadata



create_figure()
***************

        
        Function collects the user choices from the GUI and calls either the generate_stack_montage() for reading in a single image
        or the generate_image_tSNE() for multiplexed images
        

        .. code-block:: python

                def create_figure():
                     # Refer main.py on Github
                     return ([p,tsne_points, file_name_hover])

        **Output**

        ``p : figure``
        Static figure canvas with the image tSNE

        ``tsne_points : float``
        2D coordinates for each image where coordinates can be randomly generated/arranged in rows/user defined.
        The coordinates are generated based on number of images and size (length and breadth) of the static canvas

        ``file_name_hover : str``
        file name with path to populate the 'thumbnail' entry in the Hover tool





generate_stack_montage(chk_box_marker_sm, LABELS_MARKERS)
**********************************************************

        
        Function generates a stack montage by using each marker channel of a multiplexed image.
	

	- Generates evenly-spaced points on the static canvas to arrange the images in rows
	- Reads in the user-provided tSNE
	- Generates thumbnails, and pastes these onto the static canvas
	- Stores the thumbnails in the output folder
	- Updates the hover tool with thumbnail paths, marker names and metadata
	

        .. code-block:: python

                def generate_stack_montage(chk_box_marker_sm, LABELS_MARKERS):
		     # Refer main.py on Github
                     return([file_name_rot,tsne, file_name_hover])


        **Parameters:**

        ``chk_box_marker_sm : int``
        If checkbox is checked by user on the GUI, chk_box_marker_sm = 1 indicating that the stack montage option is selected. 
	If checkbox is unchecked, the multiple image tSNE generation process proceeds based on markers chosen by the user using the GUI

        ``LABELS_MARKERS : list``
        List of all marker channels in the multiplexed images. This is provided by the user in user_inputs/metadata folder as Markers.csv. 
	User can still choose a subset of LABELS_MARKERS, through the GUI, for visualizing the image tSNE

        **Output**

	``file_name_rot : str``
	file name with path where the final image with thumbnails is located

	``tsne : float``
	2D coordinates for each image to be rendered in rows. 
	The coordinates are generated based on number of images and size (length and breadth) of the static canvas 

	``file_name_hover : str``
	file name with path to populate the 'thumbnail' entry in the Hover tool


generate_image_tSNE(chk_box_marker,rb_val,rb_rs_val,rb_shf_val, LABELS_MARKERS)
*********************************************************************************

        
        Function generates the image tSNE using the multiplexed images and based on user inputs
	

        - Generates random or evenly-spaced points on the static canvas to arrange the images in rows/Reads in the user-provided tSNE
        - Generates thumbnails, and pastes these onto the static canvas
        - Stores the thumbnails in the output folder
        - Updates the hover tool with thumbnail paths, marker names and metadata
	- shuffle or no shuffle option is handled in this function where images are randomly shuffled


        .. code-block:: python

                def generate_image_tSNE(chk_box_marker,rb_val,rb_rs_val,rb_shf_val, LABELS_MARKERS):
		     # Refer main.py() on Github
                     return([file_name_rot,tsne, file_name_hover])


        **Parameters:**

        ``chk_box_marker : int``
        If checkbox is checked by user on the GUI, chk_box_marker = 1 and the user-selected markers are collected by this variable

	``rb_val : str``
	Choice of having a border for each image based on image metadata. If 'No' is chosen, no border is set for images

	``rb_rs_val : str``
	Choice to create a tSNE based on user-defined points, random coordinates or stack the images in rows

	``rb_shf_val : str``
	Choice to shuffle images ('Yes') or not ('No') while rendering the images on the static canvas
 
        ``LABELS_MARKERS : list``
        List of all marker channels in the multiplexed images. This is provided by the user in user_inputs/metadata folder as Markers.csv.
        User can still choose a subset of LABELS_MARKERS, through the GUI, for visualizing the image tSNE

        **Output**

        ``file_name_rot : str``
        file name with path where the final image with thumbnails is located

        ``tsne : float``
        2D coordinates for each image where coordinates can be random/arrnaged in rows/user defined.
        The coordinates are generated based on number of images and size (length and breadth) of the static canvas

        ``file_name_hover : str``
        file name with path to populate the 'thumbnail' entry in the Hover tool



draw_tSNE_scatter(tsne1, file_name_hover)
*******************************************

	
	Function that generates the image tSNE scatter plots for the Live canvases


	.. code_block:: python

		def draw_tSNE_scatter(tsne1, file_name_hover):
	             # refer main.py on Github
		     return ([p1,p2,p3,p4, source])

	**Parameters**

	``tsne1 : float``
        2D coordinates for each image where coordinates can be randomly generated/arranged in rows/user defined.
        The coordinates are generated based on number of images and size (length and breadth) of the static canvas

        ``file_name_hover : str``
        file name with path to populate the 'thumbnail' entry in the Hover tool

	**Output**	
	
	``p1, p2, p3, p4 : figure``
        Live canvas with tSNE scatter plots for each of the image metadata

        ``source : ColumnDataSource, dictionary``
        Dictionary of metadata and associated variables (like colour, thumbnail location) for each image which is maintained and
        updated based on user preferences for each 'Run' episode
