Working D-patches (aka Hotfixes) 
=================================

Definition of a D-patch
^^^^^^^^^^^^^^^^^^^^^^^

A D-patch is defined as any change to a customers cluster this includes new binaries, changes, additions to configurations. It also includes constant changes, diagnostic changes, etc. The Sustaining Engineer in conjunction with the support engineer can request a D-patch. Typically these are per customer per issue but in some more systemic conditions can be made available to all customers. 

Creating a D-Patch Request 
^^^^^^^^^^^^^^^^^^^^^^^^^^

D-patches are worked in the Sustaining project (SUST). To request a d-patch, create an Epic under the project describing the ask for the d-patch. This Epic will then be put on the backlog for prioritization. 

Ensure the following items are filled in. 

	1. Fix Version/s - Set this to D-Patch

	2. Linked Issues - Set this to the defect that the D-Patch is resolving. Use the "is caused by" Linked Issues selection. 

Once the Epic is prioritized or it is determined that the work will be done, at a minimum two stories will be created. 

	1. Story for the development work for the d-patch. If this work is extensive please break it down into multiple stories. 

	2. Story for the Test Plan. 

Set the acceptance criteria to a minimum of: 

	1. D-Patch code is complete and patches the system accordingly. 

	2. D-Patch manifest is properly documented and reviewed. 

	3. D-Patch testing is complete and all defects found in testing are either resolved or mitigated via documentation in the manifest. 

		a. Set Component to DPatch-Test 

Test Plan Story Acceptance Criteria 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

	* Test Plan 
		
		* Plan will be done under the Test Story that is created with Epic. 

			* If additional stories are needed then create them as stories under the DPatch Epic. 

	* Test Plan document is approved by Developer and Test Lead 

	* Story or Stories for the the test development and execution

 


