#projectManagement 

## What is change control?
**Change control** is a process in project management used to evaluate and manage proposed changes to a project. It ensures that only necessary and beneficial changes are implemented, while avoiding costly or unnecessary changes that could derail the project. 
The process involves assessing the potential impact of each change, conducting a cost-benefit analysis, and updating the project plan if the change is approved.

## The change control board (CCB)
There are certain people in the organization who have the power to change the scope of the project. For change control to be effective, these people must be part of the CCB.

CCB should contain people from the project team:
- The **project manager**
- An important **stakeholder or user** (or someone who understands and advocates the team’s perspective)
- Someone who understands the effort involved in making the change (usually, this is a representative from the **programming** team)
- Someone who understands the engineering decisions that the team makes over the course of the project (**a design team member**, requirements analyst, or, if neither is available, a programmer who participated in the design of the software).
- Someone who is familiar with the expected functionality of the software and with the behavior being discussed for each individual change (typically a **tester**)

## Basic course of events

1. A CCB member (typically a tester) who is familiar with the expected functionality of the software reads and understands the issue report, which describes the requested change.
2. The CCB member familiar with the change meets with the project manager to explain its scope and significance. Together, they identify all project team members who will be impacted by the change, and work with them to evaluate its impact. The project manager updates the issue report to reflect the result of that evaluation.
3. At the next CCB meeting, the project manager presents the scope and significance of the change, along with its expected impact. The CCB discusses the change, and performs a cost-benefit analysis to determine if its benefits are worth the cost. The CCB approves the change.
4. The project manager updates the issue report to indicate that the change has been approved, and then updates the project plan to reflect the change. The team members begin implementing the change.
## Alternative paths 
1. In Step 1, if the CCB member does not understand the change, it can be returned to the submitter for further explanation. The submitter may choose to either update the issue report to clarify the change (in which case, the script returns to step 1) or drop it entirely (in which case, the change control process ends).
2. In Step 3, if the CCB determines that the benefits of the change are not worth the cost, it can reject it. The change control process ends, and no changes are made to the project. The project manager updates the issue report to reflect the fact that it was rejected.
