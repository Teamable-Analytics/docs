# 2. forms folder

## Top level files
* <font color=#099>__init__.py</font>
* <font color=#099>base.py</font> - a template form used for other forms in this forms folder.
* <font color=#099>generate_team.py</font> - forms used to generate new teams    
  (1) GeneratedGroupSetSetupForm - used to generate teams on the Teams page in the List of Team Sets section (step 1/2). Form seen after pressing the button Generate Teams.  
  (2) NewTeamSizeOptionForm - used to generate teams (step 2/2) with details on tweaking the algorithm chosen from the previous step.  
  (3) NewBlacklistOptionForm - used to generate teams (step 2/2) with details about including Enemies Preference into the algorithm chosen from the previous step.  
  (4) NewWeightOptionForm - used to generate teams (step 2/2) with details about the weights depending on the algorithm chosen.  
  (5) NewDiversityOptionForm - used to generate teams (step 2/2) with details on tweaking the chosen algorithm (weight algorithm & social algorithm).  
  (6) NewPeerEvaluationOptionForm - Not in use.  
  (7) NewPriorityOptionForm - used to generate teams (step 2/2) with details on tweaking the chosen algorithm (priority algorithm).  
  (8) RegenerateGroupsForm - used to take the input of a list of teams that the user may lock for regenerating groups.

* <font color=#099>gradebook_graph.py</font> - Not in use.
* <font color=#099>label_value.py</font> - responsible for taking in peer evaluation attributes.
  Form is used in (step 2/2) after clicking button Create New Peer Evaluation Attribute on the Peer Evaluation page and .
  (step 2/2) of creating a new attribute in the Attribute page.
* <font color=#099>new_answer_group.py</font> - the section where a newly created answer group is asked within Create New Attribute step 2/2.
* <font color=#099>new_question.py</font> - represents the questions asked for Create New Attribute step 2/2.
* <font color=#099>new_section.py</font> - used to ask the name of a new section within Create New Section or Edit section.
* <font color=#099>peer_eval.py</font> - used to create new peer evaluations. Access form by the Create New Peer Evaluation on the Peer Evaluation page.
* <font color=#099>peer_eval_vector.py</font> - forms related to peer evaluation attributes.  
  (1) PeerEvalVectorJunctionForm - the last section to create new peer evaluations. Access form by the Create New Peer Evaluation on the Peer Evaluation page.  
  (2) SelectPeerEvalVectorForm - Not in use.  
  (3) PeerEvalVectorForm - used to create new peer evaluation attributes. Access form by the button Create New Peer Evaluation Attribute in step 2/2.  
  (4) PeerEvalMultipleChoiceVectorForm - maps to the PeerEvalMultipleChoiceVector model.   
  (5) PeerEvalCheckboxVectorForm - maps to the PeerEvalCheckboxVector model.  
  (6) PeerEvalTextInputVectorForm - maps to the PeerEvalTextInputVector model.
* <font color=#099>project.py</font>
* (1) ProjectSetForm - used to create new project sets. Accessed by the button Create New Project Set.
* (2) ProjectForm - used to create new project. Accessed by the button Edit on selected project set and the button to Add New Project.
* (3) ProjectRequirementForm - used to create new project. Accessed by the button Edit on selected project set and the button to Add New Project.
* (4) ProjectDuplicateForm - used to ask how many projects the user would like to duplicate from a selected project. Accessed by the button Duplicate on a selected project (Edit on a selected project set).

* <font color=#099>survey.py</font> - used to create new surveys.
* <font color=#099>vector.py</font> - related to creating surveys and attributes.
  (1) SelectSurveyVectorForm - Not in use.  
  (2) SurveyVectorJunctionForm - used to create new surveys.    
  (3) SurveyVectorForm - a template form used for other forms in this file.    
  (4) SurveyPreferenceVectorForm - used to define VECTOR_TYPES (attriubte types). Form accessed by step 1/2 of creating a new attribute.  
  (5) SurveyBlacklistVectorForm - used to define VECTOR_TYPES (attriubte types). Form accessed by step 1/2 of creating a new attribute.    
  (6) SurveyComplexMultipartVectorForm - used to define VECTOR_TYPES (attriubte types). Form accessed by step 1/2 of creating a new attribute.  
  (7) SurveyMultipleChoiceVectorForm - used to define VECTOR_TYPES (attriubte types). Form accessed by step 1/2 of creating a new attribute.  
  (8) SurveyCheckboxVectorForm - used to define VECTOR_TYPES (attriubte types). Form accessed by step 1/2 of creating a new attribute.

## forms: fields
* <font color=#099>__init__.py</font>
* <font color=#099>custom_form_field.py</font> - form field templates used in other files in the form folder.

## forms: formsets
* <font color=#099>__init__.py</font>
* <font color=#099>peer_eval_vector.py</font> - customize forsets for peer evaluation attribute forms.
* <font color=#099>project.py</font> - customize forsets for project forms.
* <font color=#099>util.py</font> - a formset template used in other files in the folder.
* <font color=#099>vector.py</font> - customize forsets for attribute forms.

## forms: widgets
* <font color=#099>__init__.py</font>
* <font color=#099>integer_select.py</font> - customize widgets.