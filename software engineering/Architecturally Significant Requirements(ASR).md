#software-architecture 

**Architecturally Significant Requirements(ASR)** are the requirements that if not met, may result in failure of the project.
These are the requirements that drive architectural decisions.

**Importance:** They shape the system's architecture significantly; their absence could lead to a drastically different architecture.

**Form:** These often appear as **quality attributes (QAs)** such as performance, security, modifiability, availability, and usability.

**Purpose**: Patterns and tactics are used to achieve these QAs.
- **Business Goals**:
    - Business objectives often influence ASRs, either directly or indirectly.
    - Some ASRs may not involve quality attributes but still impact the architecture.
- **Hidden in Documentation**:
    - ASRs may not always be explicitly documented in requirement documents.
    - They require careful extraction and analysis to identify.

## ASR vs. [[Quality Attributes]](QA)
ASRs often dictate QAs, but they are broader and can include aspects unrelated to quality attributes, such as external dependencies or specific hardware requirements.

### **Gathering ASRs**

1. **From Requirements Documents**:    
    - Consider aspects such as:
        - **Usage**: User roles, system modes, and language support.
        - **Time**: Timeliness and synchronization.
        - **External Elements**: Integration with external systems and devices.
        - **Networking**: Configuration and security.
        - **Security**: Permissions, roles, and authentication.
        - **Resources**: Memory, concurrency, scalability, and device usage.
        - **Project Management**: Team coordination, skills, and training.
        - **Hardware**: Processors and hardware evolution.
        - **Flexibility**: Portability and configuration.
2. **By Interviewing Stakeholders**:
    
    - Techniques:
        - Business/mission presentation.
        - Scenario brainstorming, consolidation, prioritization, and refinement.
        - Identification of architectural drivers.
3. **By Understanding Business Goals**:
    
    - **Relationship with ASRs**: Business goals often lead to quality attribute requirements or affect the architecture in other ways.
      ![[Pasted image 20241217234152.png]]

## Practice Problems

### Spring 23
Scenario: Smart Campus Surveillance-Based Guidance System, is designed to help universities to have access to an advanced surveillance system to guide students to their classes accordingly. It will help in monitoring students wandering in and around the campus and assist them in their respective classrooms. System Description: The system comprises 1 major module with their sub-modules as follows: Admin System: ● Login The admin can log in using their credentials. ● Manage Class - The admin can add, update and view classes. - They can add class details, including wings, floors and directions to the class. - They can also add class & break timings. ● Manage Student - The admin can add, update, delete and view students in the system. - They need to add photos of the students. - They can assign classes to students accordingly. ● Manage Camera - The admin can add, update, delete and view camera details. - They also need to add camera placement details, including the wing or floor on which they are placed. ● Start Surveillance - To start surveillance, the admin has to choose the camera they want to check. - If the camera recognizes a student's face, the system will verify their class details. If they are not on the same floor or wing as their class, the system will ask them to return to their class by reading out directions to them through the mobile speaker. - If the student is on the same floor or wing as their class, the system will check the class & break timings of the student and will ask them to return to their class with directions through the mobile speaker or ignore them. ● Logs -T h e a d m i n c a n v i e w s t u d e n t l o g s fr o m t h e S u r v e i l l a n c e s y s t e m.

**Question:**
Explain the steps of the Quality Attribute Workshop (QAW) to gather Architecturally Significant Requirements (ASRs) for the scenario given.









