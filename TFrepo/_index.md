Files and Folders in app
=============
This documentation explains the file structure in relation to the major processes in the team formation project.

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

# 7. team_generator folder (bowen to do)
This folder contains all the team algorithm details.
See files (team_generator_files.md)
See [Files](team_generator_files.md)

# 8. templates folder
Templates in Django are views for displaying content on a webpage.

This folder has a file called <font color=#099>home.html</font> which is the
homepage for the app before the user logs in. This page does not show up when
the app is integrated with Canvas.

The rest of this folder has subfolders for each tab in the app. There are also
additional subfolders that support the functionality of each tab (like
helpers). The ones that correspond to a tab will be explained first, and then
helper subfolders will be explained where appropriate.

## templates: sections
* <font color=#099>landing.html</font> - basic functions & allows to import data if data does not exist yet
* <font color=#099>section.html</font> - show the list of sections of the course (e.g. lab sections)

## templates: students
* <font color=#099>students.html</font> - show the list of students enrolled in the course

## templates: vector
Corresponds to the attribute page (renamed vector to attribute on the interface)
* <font color=#099>landing.html</font> - show the list of attributes created & imported by the instructor & a list of available attributes for the instructor to import 
* <font color=#099>new_vector.html</font> - show a list of attribute types the instructor can create a new attributes from (step 1/2 of creating a new attribute)
* <font color=#099>new_vector_type.html</font> - where the instructor defines the answers for a new attribute (step 2/2 of creating a new attribute)
* <font color=#099>view.html</font> - where the instructor edits the answers for each of the attributes in the list of attributes
* <font color=#099>view_vector_bank_modal_content.html</font> - where the instructor views the details of each attribute from the list of available attributes to import
* <font color=#099>view_vector_modal_content.html</font> - where the instructor views the details of each attribute from the list of attributes

## templates: project
* <font color=#099>duplicate.html</font> - ask for the number of a selected project's duplications
* <font color=#099>landing.html</font> - show the list of project sets
* <font color=#099>new_project.html</font> - where the instructor create or edit a selected project
* <font color=#099>new_project_set.html</font> - where the instructor create or edit a selected project set

## templates: survey
* <font color=#099>landing.html</font> - show the list of surveys
* <font color=#099>new.html</font> - where the instructor create or edit a survey
* <font color=#099>survey_publish.html</font> - publishes the survey to Canvas

## templates: teams
* <font color=#099>generate_teamset.html</font> - where the user selects the students and which algorithm to use
* <font color=#099>landing.html</font> - show the list of team sets
* <font color=#099>monitor.html</font> - visualizing teams analytics in a specific team set
* <font color=#099>new_generating.html</font> - shows the partial for waiting to generate teams and displays success or failure when done 
* <font color=#099>regenerate_team_modal_content.html</font> - shows a modal that displays the list of teams that the user may lock (i.e. prevent from changing) in the regeneration step
* <font color=#099>view.html</font> - the view that appears after teams have been generated, shows team generation settings used, allow user to see the visualizations for team monitoring (generate team step 2/2)
### templates: teams: algorithm_types folder
Each file lets the user set the parameters required for each algorithm as part of the generate team step.
* <font color=#099>algorithm_options_base.html</font> - set parameters for the random algorithm  
* <font color=#099>algorithm_options_priority.html</font> - set parameters for the priority algorithm
* <font color=#099>algorithm_options_social.html</font> - set parameters for the social algorithm
* <font color=#099>algorithm_options_weight.html</font> - set parameters for the weight algorithm

## templates: peer_eval
* <font color=#099>instructor_vector_result.html</font> - list all results & feedback of a specific student (instructor view)
* <font color=#099>landing.html</font> - shows list of peer evaluations, list of peer evaluation attributes, and preview peer evaluation 
* <font color=#099>new.html</font> - creates or edits peer evaluations (instructor view)
* <font color=#099>peer_eval_certain_student_view.html</font>
* <font color=#099>peer_eval_results.html</font> - shows the result of specific Peer Evaluations from the List of Peer Evaluations (instructor view)
### templates: peer_eval: peer_eval_questions folder
The below files are the students' view on either types of peer evaluations (create peer evaluation attribute step 2/2)
* <font color=#099>checkbox_vector.html</font> - when creating a new peer eval attribute, once checkbox type is selected, the page that lets you define the question text and answer group for that attribute
* <font color=#099>multiple_choice_vector.html</font> - when creating a new peer eval attribute, once multiple choice type is selected, the page that lets you define the question text and answer group for that attribute 
* <font color=#099>text_input.html</font> - when creating a new peer eval attribute, once text input type is selected, the page that lets you define the question text
### templates: peer_eval: peer_eval_vector folder
* <font color=#099>new.html</font> - where the instructor defines a New Peer Evaluation Attribute (creates peer evaluation attributes step 2/2)
* <font color=#099>select.html</font> - list peer evaluation attribute types to choose from (creates peer evaluation attributes step 1/2)
* <font color=#099>view.html</font> - where the instructor edits an existing Peer Evaluation Attribute 

## templates: admin
* <font color=#FFC0CB>stats.html</font> 

## templates: course
* <font color=#FFC0CB>landing.html</font> 
* <font color=#099>list.html</font> - list of courses are that the user has
  access to on Canvas
* <font color=#FFC0CB>wait_for_import.html</font> 

## templates: canvas
* <font color=#099>blacklist.html</font> - displays a dropdown list of students for the friends/enemies question
* <font color=#099>dropdown_question.html</font> - a dropdown list template for the other 3 files in this folder
* <font color=#099>multiple_dropdown_question.html</font> - displays a dropdown list of attributes for the multipart question (combining different attributes into one attribute)
* <font color=#099>preference_question.html</font> - displays a dropdown list of projects for the project preference question template

## templates: global
### templates: global: partial
* <font color=#FFC0CB>menu.html</font>
* <font color=#099>nav.html</font>
* <font color=#099>onboard.html</font>
* <font color=#099>step_details.html</font>
* <font color=#099>student_menu.html</font>
* <font color=#099>wait_for_task.html</font>
#### templates: global: partial: nav_partials
* <font color=#FFC0CB>admin.html</font>
* <font color=#099>attributes.html</font>
* <font color=#099>peer_eval.html</font>
* <font color=#099>project.html</font>
* <font color=#099>sections.html</font>
* <font color=#099>student_view.html</font>
* <font color=#099>student.html</font>
* <font color=#099>surveys.html</font>
* <font color=#099>teams.html</font>


## templates: student_view
* <font color=#FFC0CB>complete_peer_eval.html</font>
* <font color=#099>select_peer_eval.html</font>
* <font color=#099>select_peer_target.html</font>
* <font color=#099>student_result.html</font>
## templates: partial
* <font color=#FFC0CB>pagination.html</font>
* <font color=#099>sections.html</font> - lists all sections together or each of the defined sections individually in the course
## templates: question
* <font color=#099>new_answer_group.html</font> - the partial for defining a new answer group embedded under <font color=#099>new_question.html</font>
* <font color=#099>new_question.html</font> - where the user defines the question parts of an attribute 

# 9. templatetags
This folder contains all the util functions for UI (templates).

# 10. tests
unit tests  

# 11. utils
This folder contains all the util functions to handle general website logic (in order to keep the models and views clean).

# 12. views
Views in Django are akin to controllers for handling what gets displayed in the templates.  

There is one view per tab on the app: Section (sections.py), Students
(students.py), Attributes (vector.py), Projects (projects.py), Surveys
(survey), Teams (teams.py), Peer Evaluations (peer_evaluation.py).
There are additional files too, which are: 

* <font color=#FFC0CB>__init__.py</font>
* <font color=#099>admin.py</font> - specific to the admin interface
* <font color=#099>course.py</font> - for page that lists courses available to the logged in user (this view is skipped when integrated directly on Canvas)
* <font color=#099>peer_eval_vector.py</font> - creating attributes specific to peer evaluations
* <font color=#FFC0CB>peer_evaluation.py</font>
* <font color=#099>projects.py</font>
* <font color=#099>question.py</font> - handling question form and associating the answer group for the attribute
* <font color=#099>sections.py</font>
* <font color=#099>student.py</font>
* <font color=#099>survey.py</font>
* <font color=#099>teams.py</font>
* <font color=#099>vector.py</font>


