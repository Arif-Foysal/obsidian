#projectManagement #software-architecture  #software-engineering 

# What are Quality Attributes?
Quality attributes are measurable or testable properties of a system that is used to indicate how well the system satisfies stakeholders need beyond it's basic functionality.

**Example:** availability, performance, security, usability, modifiability, and testability.

## Problem with defining quality attribute
1. Definitions are often ambiguous or context-dependent (e.g., "modifiability").	
2. Attributes overlap across categories (e.g., denial-of-service attacks relate to availability, performance, security, and usability).
3. Different communities use inconsistent terminology for similar concepts.
- **Solution**: Use **quality attribute scenarios** to characterize and unify quality attributes.

## Quality attribute scenarios
Quality attribute scenarios are structures descriptions that clarify the quality requirements of a system. They consists of 6 parts:

- **Stimulus**: The event triggering a system response.
- **Stimulus Source**: The entity generating the stimulus (e.g., a user, system, or external factor).
- **Environment**: The context in which the event occurs.
- **Artifact**: The component of the system responding to the stimulus.
- **Response**: The system's behavior when handling the stimulus.
- **Response Measure**: How the response's effectiveness is evaluated (e.g., time, success rate).

## Achieving quality attributes through architectural patterns and tactics
### What is a tactic?
**Tactics**: Design decisions that influence specific quality attribute responses.
**For example**: Redundancy tactics can improve availability, while caching can enhance performance.

**Architectural Patterns:** A group of tactics that solve recurring design problems.

## Designing with tactics
A system design consists of a collection of decisions. Some of these decisions help control the quality attribute responses, others ensure the achievement of system functionality.

![[Availability tactics response 2024-11-23 20.24.07.excalidraw]]

### Why do we need tactics
1. Extending existing patterns to meet specific needs.
2. Designing systems when no suitable patterns exist.
3. Systematically analyzing the impact of design decisions.

## Analyzing Quality Attribute Design Decisions: Tactics-Based Questionnaires
[[Tactics based questionnaires]] are used to evaluate:

- Whether the tactic is supported by the systems's architecture.
- Risks associated with chosen tactics.
- The design rationale and implementation of tactics.



# What is Functionality?
Functionality refers to a system's ability to perform the task it was designed for.

>[!Fact]
>Of all the requirements, functionality has the strongest relationship to architecture.



# Practice problems
## Summer 24
Software Project Scenario: The BabyCare project revolves around a humanoid robot. The humanoid robot will take care of a baby’s every need by itself; any kind of assistance from or presence of a human should be unnecessary. Each robot is tasked with taking care of a child until the child reaches three years of age. The robot is nuclear-powered with the following key features. Potential threat identification (PTI): The robot will protect the child from all types of dangers, including animals, insects, and even evil humans. It identifies potential dangers through the use of multiple cameras, an infrared sensor, and a vibration sensor. It has an electric shock generator for incapacitating potential dangers, firearms for actually killing evil beings, and a water cannon for keeping threats away. Singing ability: The robot has a soothing voice generated from its five-speaker system, and it can sing all types of lullabies. Feeding ability: The robot feeds the child, and for that purpose, it has a knapsack to keep the necessary items - milk, water, sweet potatoes, apples, etc. The robot can detect if the food is stale. It has a built-in water purification system. Reset: Once the child reaches three years of age, the robot will hand over the responsibility of the child to someone else and reset its memory to handle the next child from scratch. Rejuvenating: The robot has all the knowledge needed to repair itself, restock food, create guns, ammo, etc. Initial backdoor: The first batch of robots will have a backdoor to handle updates. The robot won’t know about this. This feature will be phased out in the next batches. 

Now answer the following questions: 
1. From the given requirements, how will you gather ASR Explain briefly. 
2. Create a minimalist utility tree for the scenario above, focusing on Security, Maintainability, and Performance quality attributes. Each quality attribute should have only one refinement, and each refinement should have a single scenario.
### Sol:
2. Ans:

```
Root: Utility
├── Security
│   └── Backdoor Protection
│       └── Scenario: When a hacker attempts to access the  |            robot via the initial backdoor, the robot must |            deny access, alert authorities, and log the    |            event within 1 second.
├── Maintainability
│   └── Self-Repair
│       └── Scenario: When the robot’s infrared sensor      |           malfunctions, it should detect the issue and    |           repair it autonomously within 5 minutes.
└── Performance
|   └── Threat Response
|       └── Scenario: When a potential threat (e.g., a      |           predator) is detected, the robot should         |           identify and neutralize the threat within 2     |           seconds.
```


## Fall 23
![[Pasted image 20241216151726.png]]
Show a Tabular form of the Utility Tree for any system you have chosen. You need to show Quality Attribute, Attribute Refinement and ASR Scenario columns on the table.

| **Quality Attribute** | **Attribute Refinement**         | **ASR Scenario**                                                                                                                                              |
| --------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security**          | Authentication and Authorization | When a user attempts to control an appliance, the system ensures secure login via username, password, and two-factor authentication.                          |
|                       |                                  | If an unauthorized access attempt is detected, the system locks the account and notifies the user within 1 second.                                            |
| **Availability**      | Fault Recovery                   | If the centralized server goes down, a backup server takes over within 5 seconds to ensure no interruption in appliance control.                              |
| **Performance**       | Real-Time Control                | When a user sends a command (e.g., turn on a light), the appliance responds within 1 second, whether the user is connected via home Wi-Fi or mobile network.  |
| **Maintainability**   | Easy Configuration               | When a new appliance is added, the system allows configuration and registration through the app in less than 2 minutes without requiring technical expertise. |
| **Usability**         | Intuitive Interface              | The app provides a user-friendly interface that displays all appliances on a single dashboard, allowing quick toggling of devices with minimal navigation.    |

## Spring 23

**Scenario:** Smart Campus Surveillance-Based Guidance System, is designed to help universities to have access to an advanced surveillance system to guide students to their classes accordingly. It will help in monitoring students wandering in and around the campus and assist them in their respective classrooms. System Description: The system comprises 1 major module with their sub-modules as follows: Admin System: ● Login The admin can log in using their credentials. ● Manage Class - The admin can add, update and view classes. - They can add class details, including wings, floors and directions to the class. - They can also add class & break timings. ● Manage Student - The admin can add, update, delete and view students in the system. - They need to add photos of the students. - They can assign classes to students accordingly. ● Manage Camera - The admin can add, update, delete and view camera details. - They also need to add camera placement details, including the wing or floor on which they are placed. ● Start Surveillance - To start surveillance, the admin has to choose the camera they want to check. - If the camera recognizes a student's face, the system will verify their class details. If they are not on the same floor or wing as their class, the system will ask them to return to their class by reading out directions to them through the mobile speaker. - If the student is on the same floor or wing as their class, the system will check the class & break timings of the student and will ask them to return to their class with directions through the mobile speaker or ignore them. 
**Logs** -

The admin can view student's log from their surveillance system.

**Question:**
Show a Tabular form of the Utility Tree for the scenario given below. You need to show Quality Attribute, Attribute Refinement and ASR Scenario columns on the table. You need to focus on the following quality attributes: Performance, Usability, Deployability, Maintainability, Security and Availability.


**Ans:**

| **Quality Attribute** | **Attribute Refinement**    | **ASR Scenario**                                                                                                                                                         |
| --------------------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Performance**       | Real-Time Face Recognition  | When a camera detects a student’s face, the system verifies their identity and class location within 2 seconds to provide immediate guidance.                            |
| **Usability**         | Intuitive Admin Interface   | The admin dashboard should allow adding, updating, or deleting student, class, or camera details in less than 5 clicks, minimizing cognitive load and navigation effort. |
| **Deployability**     | Scalable Camera Integration | The system should support the integration of additional cameras, with each new camera being configured and operational within 10 minutes.                                |
| **Maintainability**   | Simplified Data Updates     | Admins can update student or class details through a user-friendly form, ensuring no data inconsistency, with changes reflected system-wide within 30 seconds.           |
| **Security**          | Secure Access Control       | Only authorized admins can log in to the system using multi-factor authentication, and unauthorized login attempts lock the account and notify the security team.        |
| **Availability**      | Surveillance Uptime         | The system automatically switches to a backup server if the main server fails, ensuring surveillance remains operational within 5 seconds of a failure event.            |
