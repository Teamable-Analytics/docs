Files and Folders in app
=============
This documentation explains the file structure in relation to the major processes in the team formation project.

All the <font color=#099>__init__.py</font> in every directory allows packages to be automatically found and import.

# Top level files
__init__.py  
admin.py  
canvas_api.py  
rules.py  
urls.py

# 1. fixtures folder
This folder has files that relates to the fake data made for testing purposes. Fixtures are probably not a good long term approach for testing, so we should revisit this at a later time if we want to do more serious testing.

# 2. forms folder
All the forms on the website that requires any UI or logic customization.

# 3. management folder
When you want to make a terminal command, the files are done here. All of these commands can only be run with system administrator access.

# 4. migrations folder
These are migration files for the database that are auto-generated via command line DB migrations and maybe additionally manually edited.

# 5. models folder
All the database model files.

# 6. tasks folder
The files in this folder pertain to any asynchronous data processing tasks needed on the site where we do not want to keep the user waiting.  

See [files](tasks_files.md).

# 7. team_generator folder (bowen to do)
This folder contains all the team algorithm details.

See [files](team_generator_files.md).

# 8. templates folder
Templates in Django are views for displaying content on a webpage.

This folder has a file called <font color=#099>home.html</font> which is the
homepage for the app before the user logs in. This page does not show up when
the app is integrated with Canvas.

The rest of this folder has subfolders for each tab in the app. There are also
additional subfolders that support the functionality of each tab (like
helpers). The ones that correspond to a tab will be explained first, and then
helper subfolders will be explained where appropriate.

See [files](templates_files.md).

# 9. templatetags
This folder contains all the util functions for UI (templates).  

See [files](templatetages_files.md).

# 10. tests
unit tests  

# 11. utils
This folder contains all the util functions to handle general website logic (in order to keep the models and views clean).

See [files](utils_files.md).

# 12. views
Views in Django are akin to controllers for handling what gets displayed in the templates.  

See [files](views_files.md).
