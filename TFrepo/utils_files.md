# 11. utils folder

## Top level files
* <font color=#099>__init__.py</font>
* <font color=#099>admin.py</font> - functions to form the json files asked on the admin page. Including stats for project set, survey, and team generation.
* <font color=#099>course_onboard_data.py</font> - includes the text instructions for the setup of each tab of the app(aka: sections, students, attributes, projects, surveys, teams, peer evaluations) as a json file
* <font color=#099>course_onboard_script.py</font> - functions to grab specific text (setup instructions) from the <font color=#099>course_onboard_data.py</font>
* <font color=#099>peer_eval.py</font>  - get-functions used for the peer evaluation page. Includes functions to determine true/false of certain condtions, to return the number or the dictionary of attributes, students, completed peer evaluation, etc. in a specified list of peer evaluations
* <font color=#099>survey.py</font> - functions to publish to, un-publish to, pull from, update the surveys to Canvas. Includes a functions to generate fake response data.
* <font color=#099>util.py</font> - functions related to naming attribute and model instance

## utils: peer_eval_vector
* <font color=#099>__init__.py</font>
* <font color=#099>export_results.py</font> - functions related to generating the csv of Results & Feedback (under List of Peer Evaluation > view result of View Results by Questions). Function: _get_peer_eval_vector_csv_export_data: produces the csv
* <font color=#099>util.py</font> - includes details of attribute type (multiple choice, checkbox, text input) of peer evaluation and attribute info used in the Results & Feedback page

## utils: team
* <font color=#099>__init__.py</font>
* <font color=#099>algorithm.py</font> - includes text descriptions of algorithm options  (weight, priority, social, random)  used to generate team and a function to grab that info
* <font color=#099>data_for_graphs.py</font> - functions related to generating graphs of a specific team sets. (Graph accessed by: Team> Monitor Teams icon)
* <font color=#099>evaluation.py</font> - functions to produce Overall Satisfaction of teams. (Overall Satisfaction accessed by: Team > View or Edit Teams)
* <font color=#099>util.py</font> - functions handling Canvas API to push/update groups to Canvas

## utils: vector
* <font color=#FFC0CB>__init__.py</font>
* <font color=#099>bank.py</font> - includes a class and a list in json.
  Class BankVector is used to store vector(attribute) information to db, so that instructors can import/save a selected vector to the course if they choose to do so.  The list is a detail List of Available Attributes to Import in json
* <font color=#099>bank_answer_groups.py</font> - includes (1) functions to create and get answer group for a new attribute. (2) few example answer groups in jsons used as the answer group for the attributes in List of Available Attributes to Import.
* <font color=#099>util.py</font> - includes (1) details of attribute options (Multiple choice, include Friends/Exclude Enemies, Project Preferencetext) as a json and functions to get them.
  (2) a function to save answer group of an attribute used both for attributes and peer eval attributes 
