### **Objective of Scheduling**

- Balances conflicting goals: efficient use of resources (staff, equipment, facilities), minimizing customer waiting times, reducing inventory and processing times.

### **Job Sequencing and Priority Rules**

Sequencing is the order in which jobs should be completed at work centers. Four common priority rules:
1. **First Come, First Served (FCFS)**: Jobs are completed in the order they arrive.
2. **Shortest Processing Time (SPT)**: Jobs with the shortest processing times go first.
3. **Earliest Due Date (EDD)**: Jobs with the earliest deadlines are prioritized.
4. **Longest Processing Time (LPT)**: Jobs with the longest processing times are handled first.

**Example:**
Apply the four popular sequencing rules to these five jobs in order to find:
i. Average Completion time (or average flow time)
ii. Utilization
Iii. Average number of jobs in the system
iv. Average job lateness (or average tardiness)

| Job | Processing Time | Due Date |
| --- | --------------- | -------- |
| A   | 6               | 8        |
| B   | 2               | 6        |
| C   | 8               | 18       |
| D   | 3               | 15       |
| E   | 9               | 23       |

**Solution:**

**FCFS:**
**Sequence:** A-B-C-D-E


**SPT:**
**Sequence:** B-D-A-C-E

| Job        | Processing Time | Due Date | Flow Time | Joblateness |
| ---------- | --------------- | -------- | --------- | ----------- |
| B          | 2               | 6        | 2         | 0           |
| D          | 3               | 15       | 5         | 0           |
| A          | 6               | 8        | 11        | 3           |
| C          | 8               | 18       | 19        | 1           |
| E          | 9               | 23       | 28        | 5           |
| **Toral:** | 28              |          | 65        | 9           |

Average completion (flow time): 65/5 = 13

Utilization:
$$\frac{\text{Total processing time}}{\text{Total flow time}}=\frac{28}{65} = 0.4307 = 43.07\%$$

Average number of jobs:
$$\frac{\text{Total flow time}}{\text{Total processing time}}=\frac{65}{28} = 2.321$$
Average joblateness: 9/5 = 1.8

**EDD:**
**Sequence:** B-A-D-C-E



**LPT:**
**Sequence:** E-C-A-D-B