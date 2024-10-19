#projectManagement 

## What is review?
Review is a technique in which a work product is distributed among reviewers who examine it and give feedback.

## Major objectives of review techniques

- **Identifying and eliminating defects** in work products early to avoid costly fixes later in the project.
- **Gaining consensus** among team members about the accuracy and completeness of a document.
- **Securing approval** from stakeholders for project deliverables.
- **Aiding in professional development** by allowing team members to learn from one another’s feedback and perspectives

## Different review techniques
- Inspections
- Deskchecks
- Walkthroughs
- Code reviews
- Pair programming

### Inspections
The goal of the inspection is for all of the inspectors to reach consensus on a work product and approve it for use in the project.

#### Course of events
1. Preparation. The moderator distributes a printed version of the work product (with line numbers) to each inspector, along with a checklist to aid in the review. Each inspector reads the work product and identifies any defects to be brought up at the meeting.
2. Overview. The inspection meeting begins. The moderator verifies that each team member is prepared.

3. Page-by-page review. The moderator runs through the work product page by page. Inspectors indicate where there are defects. Each defect is either resolved or left as an open issue. The moderator adds each defect to the inspection log.
4. Rework. The author repairs the defects identified in the inspection meeting.
5. Follow-up. Inspection team members verify that the defects were repaired.
6. Approval. The inspection team approves the work product.
#### Alternative path
1. During Step 2, if any team member has not read the work product, then the inspection is halted. The meeting is rescheduled and the script returns to step 1.
2. During Step 4, if an inspection team member discovers additional defects in the work product, then the moderator calls another meeting and the process returns to step 1.


### Deskchecks

- **Purpose**: An informal review where the document is sent to one or more reviewers for feedback.
- **Process**: The author distributes the work product to selected team members, who review it independently and send feedback via email or other methods.
- **Application**: Useful when formal inspections aren’t necessary, such as for internal documents or minor deliverables.
- **Flexibility**: Desk-checks are quicker and less structured, helping to prevent defects without needing consensus or formal approval

**When to use deskcheck:**
- When time or resources are limited, and full formal inspection is neither necessary nor useful.
- When the author needs **feedback from peers** but does not need a formal review process.
- When a **quick review** is sufficient, such as for documents with minimal risk or complexity.
### Walkthrough

- **Purpose**: An informal way of presenting a technical document in a meeting.
- **Process**: The author organizes and runs the meeting, explains the document in a manner that makes sense to everyone in the meeting, even the non-technical people, and solicits feedback.
- **Audience**: Involves technical and non-technical stakeholders, making it useful for gaining feedback from a wider audience.
- **Usage**: Common for reviewing design specifications and use cases​.


**Guidelines for successful walkthrough:**
- Verify that **everyone present** understands the purpose of the walkthrough meeting and how the material is going to be presented.
- **Describe each section** of the material to be covered by the walkthrough.
- Present the material in each section, **ensuring that  everyone present understands** the material being presented.
- Lead **a discussion** to identify any **missing sections** or material.
- **Document all issues** that are raised by walkthrough attendees.


**When to Use Walkthroughs:**:
- When the author needs to **present and explain** a document to a broad audience, including both technical and non-technical stakeholders (e.g., use cases, design specifications).
- To **get feedback** from people who may not have the technical knowledge to review the document in detail but whose input is still valuable.
- When a project is in the **early stages**, and feedback is needed on high-level concepts and understanding.

### Code reviews
- **Purpose**: A focused review of software code to detect coding errors, improve quality, and ensure adherence to coding standards.
- **Process**: A team of developers examines the code, looks for bugs, and suggests improvements.
- **Benefits**: Helps ensure that the code functions correctly, adheres to the project’s design, and fosters knowledge-sharing among developers​

**When to Use**:
- For reviewing **completed code** to find bugs, ensure coding standards are followed, and improve the quality of the code.
- When cross-training developers or helping **junior developers** learn programming techniques.
- To ensure the code aligns with the project’s requirements and is optimized for performance, maintainability, and readability.

### Pair Programming
- **Purpose**: A type of real-time code review where two programmers work together at one workstation.
- **Process**: One writes the code while the other reviews it in real time, switching roles periodically.
- **Benefits**: Immediate feedback and continuous review lead to fewer defects and better code quality. It also fosters collaboration and learning.

**When to Use Pair Programming**:
- For **real-time, continuous feedback** during the coding process.
- When collaboration and knowledge sharing between developers are a priority, especially in **agile development environments**.
- For **highly complex or critical coding tasks** that benefit from immediate problem-solving and defect detection.
