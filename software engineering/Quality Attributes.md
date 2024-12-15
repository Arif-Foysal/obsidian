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
- 



# What is Functionality?
Functionality refers to a system's ability to perform the task it was designed for.

>[!Fact]
>Of all the requirements, functionality has the strongest relationship to architecture.



