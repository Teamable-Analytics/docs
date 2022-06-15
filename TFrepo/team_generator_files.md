## team_generator: algorithm

The following files are stored in this folder:
* <font color=#099>__init__.py</font> - 
* <font color=#099>data_loader.py</font> - 
* <font color=#099>student.py</font> - 
* <font color=#099>team.py</font> - 
* <font color=#099>team_generator.py</font> - handles how the algorithm works
  in the backend
* <font color=#099>teamset.py</font> - 
* <font color=#099>validation.py</font> - 

More needs to be said about <font color=#099>team_generator.py</font>.
This is the main file that controls how the front-end interacts with the
algorithm on the back-end.

This file defines all the parameters common to each algorithm, such as team
size.

<font color=#099>get_algorithm()</font> is the function that returns which
algorithm has been selected and therefore will be used. If a new algorithm
becomes available, that option needs to be added here.


### team_generator: algorithm: priority_algorithm

### team_generator: algorithm: social_algorithm

### team_generator: algorithm: utility (weight_algorithm)
The files in this folder defines the 4 subutility functions for the weight
algorithm. These files are:
* <font color=#099> __init__.py</font>
* <font color=#099> requirement_utility.py</font> - handles project
  requirements based on what was defined by the instructor
* <font color=#099> preference_utility.py</font> - handles project
  preferences based on what students indicate in their survey
* <font color=#099> social_utility.py</font> - handles social preferences
  that students have regarding their friends and enemies, assuming this info
  was elicited in the survey
* <font color=#099> social_network.py</font> - helper file that contains the
  graph that models the stated social preferences
* <font color=#099> diversity_utility.py</font> - handles instructor criteria
  for either diversifying or concentrating on one or more attributes
