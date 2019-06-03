Working D-patches (aka Hotfixes) 
=================================

Definition of a D-patch
^^^^^^^^^^^^^^^^^^^^^^^

A D-patch is defined as any change to a customers cluster; this includes new binaries, changes, additions to configurations. It also includes constant changes, diagnostic changes, etc. The Sustaining Engineer in conjunction with the Support Engineer can request a D-patch. Typically these are per customer per issue but in some more systemic conditions, can be made available to all customers. 

Creating a D-Patch Request 
^^^^^^^^^^^^^^^^^^^^^^^^^^

D-patches are worked in the Sustaining Project (SUST). To request a d-patch, create an Epic under the project describing the ask for the d-patch. This Epic will then be put on the backlog for prioritization. 

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

 

Process Guide for the Developer and Test 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* (Dev) Take ownership of the development story or stories you are working on and set the status to Construction. 
* (Dev) Developer builds the d-patch
	* If the d-patch is a new binary (sfapp replacement or other Element based code), please review the `Building a Hotfix <https://docs.google.com/document/d/1mSdiqnXXvtz2-FvZ8iBEn6G5HkT0eqpOTvZxBeeuOVI/edit#heading=h.8ntaok2dtyx3>`_ document **before** starting your d-patch. The kiln repositories that are used to create d-patches are setup on the first request for a patch for a specific version of Element. If the version you need is not there work with B&R to get the repository/branch created. Once the GA repository is created you can simply create your patch branch from that repository. Currently, the following GA release repositories are created : 

	* `Fluorine-ga <https://solidfire.kilnhg.com/Auth/LogOn?ReturnUrl=/Code/Repositories/SolidFire/fluorine-ga&nr=>`_ 
	* `Neon-ga <https://solidfire.kilnhg.com/Auth/LogOn?ReturnUrl=/Code/Repositories/SolidFire/neon-ga&nr=>`_
		* `neon-patch1-ga <https://solidfire.kilnhg.com/Auth/LogOn?ReturnUrl=/Code/Repositories/SolidFire/neon-patch1-ga&nr=>`_ 


	* Once the d-patch and manifest are developed, reviewed, and declared ready for test, the files need to be loaded on bdr-jenkins using your LDAP login. 
		* Login to bdr-jenkins using your LDAP login. 
		* Change to the /repo/primary/sf-archive/support/hotfixes directory. 
		* Create a directory named after the bug that is being patched (e.g. EOS-1235, PE-567, etc.). If the issue does not have a bug or feature request, and the d-patch is simply for diagnostic purposes, create a ticket under the D-Patch CSD number. 
		* Ensure that permissions of the new directory are correctly set to 0755 (drwxr-xr-x). 


* (Test) While the development work is being done, the test team can pick up the test stories and work any test development that needs to be done. 
		* Examples of test development are: test plan development, test framework, automated testing, etc. 
		* While this work is being done, the stories associated with the test work should be in the construction phase. 
* (Dev) Once the development work is done move the stories to integration and initiate a pull request or other code review process. 
* (Dev) Once code review is complete, notify the test team that the code is ready by updating the Test Story with the location of the manifest and D-Patch files, including the md5 and sha256 checksums of the review. 


* (Test) Once the test story locations for the manifest and D-Patch are provided, testing can begin. 
	* Test Stories should now be in the integration phase as well. 
	* If bugs are found
		* (Test) Create a defect in the Sustaining (SUST) project and link it to the Epic. This linkage can be directly under the Epic as a parent, or if the D-Patch Epic is complete, then simply link the defect as an issue. 
		* If the defect is blocking continued testing, please be sure to put stories that are blocked in the blocked status. 
		* As defects are fixed, continue testing.
	* If no bugs are found or all defects found are fixed: 
		* Complete the test work, and set the test story to Done. 
		* Assign the test story back to the test engineer for acceptance. 
	* HANDOFF: Will be done via the Standup and Communication between the Development and Test Product Owners. 
 

D-Patch Manifest (the documentation for a D-Patch) 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The Manifest can be created as part of the development work on the D-Patch, and should be sent out for review at the same time that the code is sent out for review. 

	* (Dev) As part of the deliverables for a d-patch, we create a Manifest document to describe the following: 
		* What the purpose of the D-Patch is, including the defect being d-patched, as well as the customer impact. 
		* Risk associated with the d-patch and any mitigation for those risks 
		* The contents of the D-Patch. 
		* Installation, Execution, Back-Out process and/or Uninstall 
	* Start with the D-Patch Manifest Template located `here <https://docs.google.com/document/d/1oCzqxnF68P6kDQiNJpEDS99W5WT0gjoswQSNNFbX5ks/edit>`_ . 
		* Click on File -> Make a copy and create a manifest with the name of D-Patch Manifest <Defect Identifier> (e.g. D-Patch Manifest EOS-1234). If you check the "Copy comments and suggestions" you can easily resolve the helper comments for each of the portions that need to be filled out. 
		* Fill out the copy with the information required. 
	* (Dev) Once the D-Patch Manifest has been reviewed and all conerns addressed create the SBR (Build & Release) ticket to start the process for publishing the D-Patch. 
		* When creating the SBR ticket link it back to the D-Patch Epic. 
		* Intially if testing is not complete, only add the Manifest Link to the SBR ticket so that the taxonomy can be created ahead of time. 
		* Once testing is complete, add the link to the D-Patch files and add a comment that the D-Patch is ready for posting. 


Test Execution 
^^^^^^^^^^^^^^

	* (Test) review the manifest and start the test effort design and documentation process. 
		* The Sustaining Test engineer uses the Manifest and the files that are given to Build and Release to publish. NOTE: *A build or script directly from the Developers workstation should not be used for validation.* 
		* Sustaining will use the `SFGSUST-D-Patch-Release-Qualification-Plan(JIRA-XXXX) <https://netapp-my.sharepoint.com/:w:/p/htad/EVy4bFV5rqdJnklPHqygPNQBrwnLLcFbb8_7fOPVk9YizA?rtime=MBUJGqvj1kg>`_ template to outline the test/validation effort. This includes environment prerequistes, test and validation minimum standard of care, additionally called out validation efforts and any custom post validation. 
			* A review of the test plan should be done between the test engineer and the development engineer to satisfy any testing that may be missed. 
		* The `CPE AT2 Frame work parent task <https://confluence.ngage.netapp.com/display/CPE/%5BCPE%5D+AT2+Framework>`_ will be leveraged or Valence to set the CPE minimum standard of care for all validations. 
			* CPE will enter the AT2 task options used during the D-Patch validation effort in the `[CPE] Test frameWork B-x.x (Functional Description)V2 <https://docs.google.com/spreadsheets/d/1EgbIkgUmzUrbN5hWeS46xCM8LH9a_tH8O78t_Kzq8pI/edit#gid=37442893>`_ . The tester will clone this sheet and configure specifically for the test effort. 
		* The `SFGSUST-D-Patch-Release-Qualification-Plan(JIRA-XXXX) <https://netapp-my.sharepoint.com/:w:/p/htad/EVy4bFV5rqdJnklPHqygPNQBrwnLLcFbb8_7fOPVk9YizA?rtime=jZUrQqzj1kg>`_ will be completed prior to the hand-off to Dev. 
	* (Test) if Sustaining Test finds a defect, 
		* Create a defect and link it to the Epic using the Epic link in the defect creation page. 
		* If the defect is found after the d-patch is released and the Epic has been closed, do NOT re-open the Epic, but create a defect and link it to the Epic as it relates to.



Working Defects found against a D-Patch during testing
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

	* (Dev) Developer moves the 'Defect' issue to 'Construction'
	* (Dev) Work on fixing the defect as you would any other defect. 
		* Create the fix (defect status is Construction) 
		* Submit for code review (defect status is integration) 
		* Make sure all checksums are updated on both bdr-jenkins as well as in the manifest. 
		* Update the manifest version. 
		* Re-publish the changes to bdr-jenkins following the same process above. 
		* Move the defect to Done state and re-assign to the perosn that filled defect. 
	* (Test) Once the defect has been moved to Done, and re-assigned for acceptance. 
	* (Test) Re-test and ensure that the defect is fixed. 
		* If not re-assign to the developer, and set status to Construction. 
		* If fixed, set the status to Accepted, and remove any blocked status for the test story. 


Final Release Steps 
^^^^^^^^^^^^^^^^^^^

An SBR ticket should have been created once the Manifest taxonomy (top portion describing the D-Patch) is complete to give the Build & Release team a heads up so they can start planning for the D-Patch release. If this ticket was not created earlier create the ticket in the SBR project. 

	* (Dev) Update or Submit a SF Build and Release Service Request (SBR) nGage ticket using the following template. The answers below are typical answers in most cases. 

		* Product: Element D-Patch 
		* Build Version or Branch: DPatch for Case xxxxxx (JIRA Case Number) 
		* Required When: Please give B&R at least 8 hours to perform the posting, unless a earlier time has been agreed to
		* Supporting Documentation to include in Release Announcement: Link to Manifest doc - This should be a link to the final google doc if releasing to NSS. 
		* Comments: Describe any nuances about this DPatch posting.
		* What are the file names to be posted?: List the deliverables for this DPatch, including the md5 and sha256 checksum file, Manifest PDF and the DPatch executables.
		* These should be the same location that was given to the test team. 



  
