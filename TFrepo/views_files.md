There is one file per that handles the logic for each tab on the app: Section (sections.py), Students (students.py), Attributes (vector.py), Projects (projects.py), Surveys (survey), Teams (teams.py), Peer Evaluations (peer_evaluation.py).

There are additional files too, which are: 

* <font color=#099>__init__.py</font>
* <font color=#099>admin.py</font> - specific to the admin interface
* <font color=#099>course.py</font> - for page that lists courses available to the logged in user (this view is skipped when integrated directly on Canvas)
* <font color=#099>peer_eval_vector.py</font> - creating attributes specific to peer evaluations
* <font color=#099>peer_evaluation.py</font> - handles functions related to the peer evaluations page. Including creation, view, deletion of peer evaluations etc.
* <font color=#099>projects.py</font> - handles functions related to the project page.
* <font color=#099>question.py</font> - handling question form and associating the answer group for the attribute
* <font color=#099>sections.py</font> - handles functions related to the sections page.
* <font color=#099>student.py</font> - handles functions related to the student page.
* <font color=#099>survey.py</font> - handles functions related to the survey page.
* <font color=#099>teams.py</font> - handles functions related to the team page.
* <font color=#099>vector.py</font> - handles functions related to the vector page.

