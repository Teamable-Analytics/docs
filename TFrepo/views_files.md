# 12. views
In this folder, each file has python functions that takes http requests, load a template from the template folder
, and returns http response with the result of the rendered template.


* <font color=#099>__init__.py</font>
* <font color=#099>admin.py</font> - specific to the admin interface
* <font color=#099>course.py</font> - for page that lists courses available to the logged in user (this view is skipped when integrated directly on Canvas)
* <font color=#099>peer_eval_vector.py</font> - creating attributes specific to peer evaluations
* <font color=#099>peer_evaluation.py</font> - handles functions related to the peer evaluations page. Including creation, view, deletion of peer evaluations etc.
* <font color=#099>projects.py</font> - handles http requests made on the Project page and displays the Project page.
* <font color=#099>question.py</font> - handling http requests and displays forms and associating the answer group for an attribute.
* <font color=#099>sections.py</font> - handles http requests made on the Section page and displays the Sections page.
* <font color=#099>student.py</font> - handles http requests made on the Student page and displays the Student page.
* <font color=#099>survey.py</font> - handles http requests made on the Survey page and displays the Survey page.
* <font color=#099>teams.py</font> - handles http requests made on the Teams page and displays the Team page.
* <font color=#099>vector.py</font> - handles http requests made on the Attribute page and displays the Attribute page.

