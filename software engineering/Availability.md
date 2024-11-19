#software-architecture #software-engineering 

**Availability** in software architecture refers to a system's ability(property of a software) to be operational and ready to perform it's tasks when needed.
It builds on the concept of reliability by incorporating recovery mechanisms to restore functionality after failure.

## Expression to derive steady-state availability (which came from the world of hardware):
Related: [[Lean manufacturing, six sigma and reliability]]

$$\text{A}= \frac{\text{MTBF}}{\text{MTBF} + \text{MTTR}}$$
Where:

- **MTBF (Mean Time Between Failures)**: The average time the system operates without failure.
- **MTTR (Mean Time to Repair)**: The average time taken to repair the system and restore it to operational status.

>[!Note]
>From this formula, we can calculate probabilities and make claims like “the system exhibits 99.999 percent availability”or “there is a 0.001 percent probability that the system will not be operational when needed.”

## Availability general scenario
![[Pasted image 20241119120437.png]]![[Pasted image 20241119120516.png]]

## Tactics for Availability
