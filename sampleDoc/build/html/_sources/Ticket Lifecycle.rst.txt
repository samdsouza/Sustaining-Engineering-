
Ticket LifeCycle 
=======================



Escalations, DU/DL/DC and Help Tickets 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The following statuses may exist for an escalation of the type: CPE DU/DL/DC, CPE Escalation, CPE Help: 

.. figure:: needTriage.png 
   :alt: Need Triage 

   Need Triage: New cases which haven't been triaged yet. 

.. figure:: inQueue.png 
   :alt: In Queue 

   In Queue: Escalations that have been triaged but with no one assigned to them (yet) 

.. figure:: fixInProgress.png 
   :alt: Fix in Progress 

   In Progress: Escalations being worked by a CPE Engineer. **Escalations that require code changes shall stay in this status until the changes have been committed to a branch. After that, they can be moved to 'Waiting for Release' until the release in which changes are applied has been made available to Support.**

.. figure:: needMoreInfo.png 
   :alt: Need More Info 

   Need More Information: Escalations waiting on information from Support of the customer. 

.. figure:: waitingRelease.png 
   :alt: Waiting For Release 

   **If code changes are required to solve the issue, once the changes have been submitted to a branch the case shall remain in 'Waiting for Release' until the release is available for Support.** 

.. figure:: escalationManagement.png 
   :alt: Escalation Management 

   Escalation Management: Issues being worked by an escalation manager. 

.. figure:: resolved.png 
   :alt: Resolved 

   Resolved: Issues that have been resolved 


.. figure:: reopen.png 
   :alt: Reopen 

   Reopened: Issues that were resolved and that have been reopened. 


Below, the escalation ticket managment cycle is shown, 

.. image:: flowChart.png 





Solved DU/DL/DC
^^^^^^^^^^^^^^^

The following statuses may exist for an escalation of the type: Solved DU/DL/DC: 


.. figure:: inQueue.png
   :alt: In Queue 

   In Queue: In the case of Solved DU/DL/DC cases, In Queue means that no one has looked into it yet. 


.. figure:: resolved.png 
   :alt: Resolved 

   Resolved: Issues that have been processed from the quality metrics perspective. 


.. figure:: reopen.png 
   :alt: Reopened 

   Reopened: Issues that need to be revisted for whatever reason. 







Test Request 
^^^^^^^^^^^^

.. figure:: inQueue.png 
   :alt: In Queue 

   In Queue: New ticket with no one assigned to it yet. 


.. figure:: testDesign.png
   :alt: Test Design 

   Test in the design phase. 


.. figure:: execution.png 
   :alt: Test Execution 

   Test in the execution phase. 

.. figure:: completing.png
   :alt: Test Completed 

   Test completed. 

.. figure:: resolved.png 
   :alt: Resolved 

   Ticket has been closed 


.. figure:: waiting.png 
   :alt: Waiting 

   Test can't continue for whatever reason 



Hotfix/IDR/D-patches
^^^^^^^^^^^^^^^^^^^^

.. figure:: approval.png
   :alt: Pending Approval 

   Hotfix is in the queue and needs to be approved before starting work on it.


.. figure:: fixInProgress.png 
   :alt: Fix in Progress 

   Hotfix is being worked. 

.. figure:: testing.png 
   :alt: Testing 

   Renamed as 'Dev complete'. Hotfix in the testing/validation phase before it gets released to customers. 

.. figure:: finalize.png 
   :alt: Finalize 

   This status includes build and push to brickftp actions. 


.. figure:: resolved.png 
   :alt: Resolved 

   Hotfix has been delivered to the customer(s).





CPE Defects 
^^^^^^^^^^^

.. figure:: inQueue.png 
   :alt: In Queue 

   New defects have been opened. No work has been done on it yet. 

.. figure:: fixInProgress.png 
   :alt: Fix In Progress 

   Defet is being worked by development 

.. figure:: verify.png
   :alt: Verify Fixed 

   CPE test is verifying the fix. 


.. figure:: failure.png 
   :alt: Test Failure 

   Testing on the d-patch fix failed. 

.. figure:: waiting.png 
   :alt: Waiting 

   The defect is in waiting status (maybe blocked) 

.. figure:: resolved.png 
   :alt: Resolved

   Defect has been resolved. 


