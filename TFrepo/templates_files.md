# 8. templates folder

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
* <font color=#099>stats.html</font> - an interface that displays details of all projects, surveys, and team generation algorithms. Download available as Json file.

## templates: course
* <font color=#099>landing.html</font> - the help/how does it work page. List steps to help the instructor set up.
* <font color=#099>list.html</font> - list of courses are that the user has
  access to on Canvas
* <font color=#099>wait_for_import.html</font> - redirects the user after importing students and groups

## templates: canvas
* <font color=#099>blacklist.html</font> - displays a dropdown list of students for the friends/enemies question
* <font color=#099>dropdown_question.html</font> - a dropdown list template for the other 3 files in this folder
* <font color=#099>multiple_dropdown_question.html</font> - displays a dropdown list of attributes for the multipart question (combining different attributes into one attribute)
* <font color=#099>preference_question.html</font> - displays a dropdown list of projects for the project preference question template

## templates: global
### templates: global: partial
* <font color=#099>menu.html</font> - the nav-bar used in all pages in the instructors' view, which includes sections, students, attributes, projects, surveys, teams, peer evaluations
* <font color=#099>nav.html</font> - template of another nav-bar. Used to display the current location within sections, students, attributes, projects, surveys, teams, or peer evaluations
* <font color=#099>onboard.html</font> - display which step an instructor is on in the setup if there are steps to be completed
* <font color=#099>step_details.html</font> - the template for the collapsible step info
* <font color=#099>student_menu.html</font> - the nav-bar used in all pages in the students' view, which includes course, peer evaluations
* <font color=#099>wait_for_task.html</font> - template to display the loading status
#### templates: global: partial: nav_partials
Each of the file below lists hyperlinks/locations in a specific page. All of which are used by the templates: global: partial: nav.html template
* <font color=#099>admin.html</font> - list of all hyperlinks/locations within the admin page.
* <font color=#099>attributes.html</font> - list of all hyperlinks/locations within the attribute page.
* <font color=#099>peer_eval.html</font> - list of all hyperlinks/locations within the peer evaluation page.
* <font color=#099>project.html</font> - list of all hyperlinks/locations within the project page.
* <font color=#099>sections.html</font> - list of all hyperlinks/locations within the sections page.
* <font color=#099>student_view.html</font> - list of all hyperlinks/locations within the pages that students can see.
* <font color=#099>student.html</font> - list of all hyperlinks/locations within the student page.
* <font color=#099>surveys.html</font> - list of all hyperlinks/locations within the surveys page.
* <font color=#099>teams.html</font> - list of all hyperlinks/locations within the teams page.


## templates: student_view
The pages below are within Peer Evaluation designed for students.
* <font color=#099>complete_peer_eval.html</font> - template of the peer evaluation survey to answer for each team member
* <font color=#099>select_peer_eval.html</font> - list of all peer evaluations to-do.
* <font color=#099>select_peer_target.html</font> - list of all team members in a selected peer evaluation. (Action > complete)
* <font color=#099>student_result.html</font> - displays the feedback from team members of a selected peer evaluation. (Action > view my results)

## templates: partial
* <font color=#099>pagination.html</font> - list previous, next, and number of pages of results
* <font color=#099>sections.html</font> - lists all sections together or each of the defined sections individually in the course

## templates: question
* <font color=#099>new_answer_group.html</font> - the partial for defining a new answer group embedded under <font color=#099>new_question.html</font>
* <font color=#099>new_question.html</font> - where the user defines the question parts of an attribute 
