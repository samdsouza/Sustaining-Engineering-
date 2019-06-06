Definitions 
==================================

Escalations 
^^^^^^^^^^^

* An Escalation is an active incident raised by Support on behalf of a customer that needs investigation by CPE. The CPE engineer owns the escalation and is responsible for communicating to Support, troubleshooting, providing support, creating a defect case if neccesary, and representing the defect in Sustaining Bugcourt until there is a target release for it. 

Defects/Bugs
^^^^^^^^^^^^

* A Bug is an issue that documents a product defect and that may require product changes (code, documentation, etc). 
* CPE Support creates a Defect case and hands off to CPE Engineering after a full triage of the intial escalation. 

Enhancements 
^^^^^^^^^^^^

* If an enhancement is requested it can be handled in a couple different ways: 

    * Development Product Enhancement 
	* This should be submitted to the appropriate JIRA project, and the appropriate Product Manager notified. 

    * Sustaining Enhancement 
	* Can be added to the CBD project in Atlassian, or the SUSTENG project after migration to nGage. 

* After an Enhancement has been filled, contact a Sustaining Manager or the appropriate Product Owner to see if any followup is neccesary.  


Triage
^^^^^^

**Triage:** Triage or triaging an escalation, is the intial check for completeness of an escalation sent from Support to Sustaining. The triage engineer must check the case makes sense, the problem description is complete, the customer impact is complete, the timeline of the issue is included in the escalation and log files are complete, accurate, and have been given read and write access. More information can be found on the **`Escalation-Traige-Responsabilites`** page. 


Epic
^^^^

**Epic:** An epic is the overall goal of the D-patch / feature implementation. It contains a summary of the issue being solved and specific test criteria that must be met in order for the feature to be implemented. It is usally a twelve week project broken up into six, two week sprints, otherwise known as stories. These stories help break up the feature implementation into more manageable sub criteria. 

Story
^^^^^

**Story:** A story is a two week sprint that focuses on implementing a sub feature of the overarching goal of an Epic. When creating a story on JIRA, be sure to link the story to the Epic that encompasses the story. 

Enabler
^^^^^^^

**Enabler:** An enabler is infastructer that aids in the development of  stories or epics. Enabler's can be utilized as a one time use or continuously throughout the development of an Epic. Examples of enablers include, applications to parse log files, applications to analyze core dump files, a cluster performance analyzation tool, etc...

Manifest
^^^^^^^^

**Manifest:** A manifest is documentation that details how to implement / install a D-patch. It contians step by step instructions for how support can implement the D-patch to solve the customer issue. Additionally, it lists the acceptable versions of the product the D-patch can be implemented on, as well as the risks associated with those added implementations. 

DU/DL/DC
^^^^^^^^

* **DU** - Data Unavailable 
* **DL** - Data Loss
* **DC** - Data Corruption 



