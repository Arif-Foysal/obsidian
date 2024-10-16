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

### Johnson's rule
**Johnson's Rule** is a method used to minimize the total time to complete a set of jobs that must go through two workstations (or machines) in the same sequence. It helps in determining the optimal job sequence to reduce the overall makespan (total completion time) and idle time of the machines.

**Example:**
Sequence the following jobs using Johnson’s rule and draw a [[Gantt chart]] and find the idle time for both machines.

| Job | Work Center(1) | Work Cernter(2) |
| --- | -------------- | --------------- |
| A   | 7              | 2               |
| B   | 9              | 4               |
| C   | 3              | 5               |
| D   | 1              | 2               |
| E   | 5              | 8               |
**Sequence:**
//sorting in terms of wc1

|  D  |  C  |  E  |  B  |  A  |
| :-: | :-: | :-: | :-: | :-: |
**Gantt Chart:**
![[scheduling-problem-2024-10-14 23.15.26.excalidraw|{width=50%}]]


**Idle Time:**
**WC1:** 2
**WC2:** 1 + 1 + 1 + 3 = 6

Total idle time: 2+6 = 8

### Critical Ratio

#### **Problem 01:**
Sequence the following jobs using Critical ratio method and determine average completion time, Utilization, average number of jobs in the system and average job lateness. Is it possible to apply Johnson’s rule here?(Explain)

| Job | Processing Time | Due Date |
| :-: | :-------------: | :------: |
|  A  |        6        |    8     |
|  B  |        2        |    6     |
|  C  |        8        |    18    |
|  D  |        3        |    15    |
|  E  |        9        |    23    |
**Solution:**
>[!Tip]
>Lower critical ratio is better

$$\text{Critical Ratio}=\frac{\text{Due date -}\sum{\text{Processing time of completed jobs}}}{\text{Processing time}}$$

| Job | Processing Time | Due Date | CR 1            | CR 2            |                 |                   |
| :-: | :-------------: | :------: | --------------- | --------------- | --------------- | ----------------- |
|  A  |        6        |    8     | (8-0)/6 = 1.33  |                 |                 |                   |
|  B  |        2        |    6     | (6-0)/2 = 3     | (6-6)/2 = 0     |                 |                   |
|  C  |        8        |    18    | (18-0)/8 = 2.25 | (18-6)/8 = 1.5  | (18-8)/8 = 1.25 |                   |
|  D  |        3        |    15    | (15-0)/3 = 5    | (15-6)/3 = 3    | (15-8)/3 = 2.33 | (15-16)/3 = -0.33 |
|  E  |        9        |    23    | (23-0)/9 = 2.55 | (23-6)/9 = 1.88 | (23-8)/9 = 1.66 | (23-16)/9 = 0.77  |
**Sequence:** A - B - C - D -E

| Job | Processing Time | Due Date | Flow Time | Joblateness |
| :-: | :-------------: | :------: | :-------: | :---------: |
|  A  |        6        |    8     |     6     |      0      |
|  B  |        2        |    6     |     8     |      2      |
|  C  |        8        |    18    |    16     |      0      |
|  D  |        3        |    15    |    19     |      4      |
|  E  |        9        |    23    |    28     |      5      |
**Average completion time or flow time:** 
$$\text{Average Flow Time} = \frac{\text{Total Flow Time}}{\text{Number of Jobs}} = \frac{6 + 8 + 16 + 19 + 28}{5} = \frac{77}{5} = 15.4$$

**Utilization:**
$$\text{Utilization} = \frac{\text{Total Processing Time}}{\text{Total Flow Time}} = \frac{28}{77} \approx 36.36\%$$

**Average number of jobs:**
$$\text{Average Number of Jobs} = \frac{\text{Total Flow Time}}{\text{Total Processing Time}} = \frac{77}{28} \approx 2.75$$


**Average Job lateness:**
$$\text{Average Job Lateness} = \frac{\text{Total Job Lateness}}{\text{Number of Jobs}} = \frac{11}{5} = 2.2$$

**Johnson’s Rule Applicability:**
Johnson’s Rule is specifically used for sequencing jobs that need to pass through two stages or workstations. Here we are dealing only with job processing times and due dates for single-stage processing; therefore, Johnson’s Rule is not applicable to this situation.


