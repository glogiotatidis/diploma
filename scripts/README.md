# scripts
20180531

The folder consists of the following files:

- **main.py** (_The main script that controls everything in the blender file_)

- **camera_control.py** (_A script for controlling the menu items movement -more info below_)

- **cube_rotation.py** (_A simple script for the rotation of the cube at the start of the program_)

- **export.py**	(_The script that exports all the models in obj and stl format_)

- **export_obj_scipt.py** (_The script to export all the models in obj format_)

- **export_stl_scipt.py** (_The script to export all the models in obj format_)

- **info_bubble.py** (_Test script to show an info bubble over the buttons -made for an earlier version of the program, not implemented currently. TODO_)

# main.py

main.py file's structure:

### PHASE 1: INITIALIZATION

- **IMPORT** (_Importing the necessary modules._)

- **DIRECTORIES** (_Setting up the directory variables. All values are made local._)

- **GROUPS** (_Every subfolder in the "models" folder is a group of related objects. These objects will be loaded at the beginning of the file and made into selection sets for the user to use._)
    - _function_: **change_group**

- **LOAD** (_Loading the models from the individual .blend files in the program's memory for later use._)

- **VARIABLES** (_Setting up some variables._)

- **DATA** (_Create lists of items from the models. Requires a csv file in the "data directory" that describes the name and dimensions of the object. More info below._)

- **PREVIEW_MESH**
    - _function_: **preview_mesh** (_function that updates the "preview" item to the item selected from the "parts" list._)

- **DIMENSIONS** (_Setting the dimensions of the item (taken from the csv file). Needs to be a floating number to work._)

- **ROTATION** (_NOT WORKING_) The idea for this was to have the width and height dimensions switch when the object is rotated 90 degrees, but I failed horribly at it. I will try again.

- _function_: **mouse_over_button** (_Disables the creation of new blocks when the cursor is over a button or other objects that have set the "mouse over button" variable to 0 (I should probably switch the 1 and 0 values. It would make more sense._)

- _function_: **hide_bounding_box** (_Function that hides or shows the bounding box of the objects when the keyboard letter H is pressed._)

- _function_: **get_ID**

- **GRIDS**
    - **grid_patterns**
    - _function_: **clear_grid**
    - _function_: **generate_grid_pattern**

- **SEND MESSAGE**
    - _function_: **send_message**
    - _function_: **receive_message**

- **CREATE BUILDING**
    - _function_: **create_building**

- **SAVE/LOAD**
    - _function_: **save_data**
    - _function_: **load_data**

- **CREATE BUTTONS**
    - _function_: **create_buttons**

- **INFO TEXT**
    - _function_: **show_info_text**

- **WIKIPEDIA**
    - _function_: **open_wikipedia_link**

- **TEXT**
    - _function_: **fix_text_resolution**

- **CAMERA**
    - _function_: **set_camera_position**

- **SCREENSHOT**
    - _function_: **take_screenshot**

### PHASE 2: MAIN

_function_: **main** (_The main function, attached to the camera. Everything is done here._)
  - controller
  - owner
  - sensors
    - left click
    - right click
    - mouse over
  - mode
    - mode 1
    - mode 2
    - mode 3
  - if mouse over positive:
    - rayObj
    - rayNormal
    - rayPos

  - if left click positive:
    - add object
    - add object's bounding box
  - if right click positive:
    - end object (or object's bounding box)

 **NOTES**

# camera_control.py

camera_control.py is used to move the menu items (parts, buildings, grids) out of the camera's view by rotating the parent item (an empty) 90 degrees to the left

# cube_rotation.py

very simple script that rotates the cube at the beginning of the program 

# export.py

script to export all the loaded models to obj and stl files (needs work)
### export_obj_script.py
### export_stl_script.py
the scripts used to convert the models to obj and stl respectively

# info_bubble.py

script that shows an info bubble over the button when the cursor is over it. not implemented currently (was used for an older version of the program. TODO)
