#software-engineering #projectManagement

Critical Path Method (CPM) is a method used in project planning, generally for **project scheduling** for the on-time completion of the project. It helps in the determination of the earliest time by which the whole project can be completed. There are two main concepts in this method namely critical task and critical path.
There are two main concepts in this method namely-
- [[critical task]]
- [[critical path]]

## Critical task
![[critical task]]

## Critical path
![[critical path]]

## Benifits of using critical path method(CPM)

- Show the project schedule visually.
- Highlight important tasks with CPM.
- Use CPM to find and handle risks.
- CPM helps the project team communicate better.
## How to find the critical path in a project****:****

- ****Step 1: Identify all tasks required to complete the project****
- ****Step 2: Determine the sequence of tasks****
- ****Step 3: Estimate the duration of each task****
- ****Step 4: Draw a network diagram****
- ****Step 5: Identify the critical path****
- ****Step 6: Calculate the float****
- ****Step 7: Monitor the critical path****

## **Major steps to find critical path in a project**
1. Identifying the activities
2. Construct the project network
3. Perform the time estimation using forward and backward pass
4. Identify the critical path

## **Rules for Designing the Activity-on-Node network diagram:**

- A project network should have only one start node
- A project network should have only one end node
- A node has a duration
- Links normally have no duration
- “Precedents” are the immediate preceding activities
- Time moves from left to right in the project network
- A network should not contain loops
- A network should not contain [[dangles]]

## Node representation

![[Pasted image 20240318163432.png]]

- ****Activity label**** is the name of the activity represented by that node.
- ****Earliest Start**** is the date or time at which the activity can be started at the earliest.
- ****Earliest Finish**** is the date or time at which the activity can be completed at the earliest.
- ****Latest Start**** is the date or time at which the activity can be started at the latest.
- ****The latest Finish**** is the date or time at which the activity can be finished at the latest.
- ****Float**** is equal to the difference between the earliest start and latest start or earliest finish and latest finish.

## Examples

<iframe width=100% height="315" src="https://www.youtube.com/embed/Us5YtgvfomQ?si=V7PDQfC0KuUTLkMW" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
## Example 1
The table given below contains the activity label, its respective duration (in weeks), and its precedents. We will use the critical path method to find the critical path and activities of this project.

| **Activity** | **Duration (in weeks)** | **Precedents** |
| ------------ | ----------------------- | -------------- |
| A            | 6                       | –              |
| B            | 4                       | –              |
| C            | 3                       | A              |
| D            | 4                       | B              |
| E            | 3                       | B              |
| F            | 10                      | –              |
| G            | 3                       | E,F            |
| H            | 2                       | C,D            |

### Activity on-node diagram

![[Pasted image 20240318163950.png]]

### Forward Pass in Critical path in project management:

The forward pass is carried out to calculate the earliest dates on which each activity may be started and completed.

1. Activity A may start immediately. Hence, the earliest date for its start is zero i.e. ES(A) = 0. It takes 6 weeks to complete its execution. Hence, earliest it can finish is week 6 i.e. EF(A) = 6.
2. Activity B may start immediately. Hence, the earliest date for its start is zero i.e. ES(B) = 0. It takes 4 weeks to complete its execution. Hence, the earliest it can finish is week 4 i.e. EF(B) = 4.
3. Activity F may start immediately. Hence, the earliest date for its start is zero i.e. ES(F) = 0. It takes 10 weeks to complete its execution. Hence, the earliest it can finish is week 10 i.e. EF(F) = 10.
4. Activity C starts as soon as Activity A completes its execution. Hence, the earliest week it can start its execution is week 6 i.e. ES(C) = 6. It takes 3 weeks to complete its execution. Hence, the earliest it can finish is week 9 i.e. EF(C) = 9.
5. Activity D starts as soon as Activity B completes its execution. Hence, the earliest week it can start its execution is week 4 i.e. ES(D) = 4. It takes 4 weeks to complete its execution. Hence, the earliest it can finish is week 8 i.e. EF(D) = 8.
6. Activity E starts as soon as Activity B completes its execution. Hence, the earliest week it can start its execution is week 4 i.e. ES(E) = 4. It takes 3 weeks to complete its execution. Hence, the earliest it can finish is week 7 i.e. EF(E) = 7.
7. Activity G starts as soon as activity E and activity F completes their execution. Since the activity requires the completion of both for starting its execution, we would consider the MAX(ES(E), ES(F)). Hence, the earliest week it can start its execution is week 10 i.e. ES(G) = 10. It takes 3 weeks to complete its execution. Hence, the earliest it can finish is week 13 i.e. EF(G) = 13.
8. Activity H starts as soon as activity C and activity D completes their execution. Since the activity requires the completion of both for starting its execution, we would consider the MAX(ES(C), ES(D)). Hence, the earliest week it can start its execution is week 9 i.e. ES(H) = 9. It takes 2 weeks to complete its execution. Hence, the earliest it can finish is week 11 i.e. EF(H) = 11.
![[Pasted image 20240318174304.png]]

### Backward Pass in Critical path in project management:

The backward pass is carried out to calculate the latest dates on which each activity may be started and finished without delaying the end date of the project. Assumption: Latest finish date = Earliest Finish date (of project).

- Activity G’s latest finish date is equal to the earliest finish date of the precedent activity of finish according to the assumption i.e. LF(G) = 13. It takes 3 weeks to complete its execution. Hence, the latest it can start is week 10 i.e. LS(G) = 10.
- Activity H’s latest finish date is equal to the earliest finish date of the precedent activity of finish according to the assumption i.e. LF(H) = 13. It takes 2 weeks to complete its execution. Hence, the latest it can start is week 11 i.e. LS(H) = 11.
- The latest end date for activity C would be the latest start date of H i.e. LF(C) = 11. It takes 3 weeks to complete its execution. Hence, the latest it can start is week 8 i.e. LS(C) = 8.
- The latest end date for activity D would be the latest start date of H i.e. LF(D) = 11. It takes 4 weeks to complete its execution. Hence, the latest it can start is week 7 i.e. LS(D) = 7.
- The latest end date for activity E would be the latest start date of G i.e. LF(G) = 10. It takes 3 weeks to complete its execution. Hence, the latest it can start is week 7 i.e. LS(E) = 7.
- The latest end date for activity F would be the latest start date of G i.e. LF(G) = 10. It takes 10 weeks to complete its execution. Hence, the latest it can start is week 0 i.e. LS(F) = 0.
- The latest end date for activity A would be the latest start date of C i.e. LF(A) = 8. It takes 6 weeks to complete its execution. Hence, the latest it can start is week 2 i.e. LS(A) = 2.
- The latest end date for activity B would be the earliest of the latest start date of D and E i.e. LF(B) = 7. It takes 4 weeks to complete its execution. Hence, the latest it can start is week 3 i.e. LS(B) = 3.
![[Pasted image 20240318174335.png]]

### Identifying Critical Path:
The critical path is the path that gives us or helps us estimate the earliest time in which the whole project can be completed. Any delay to an activity on this critical path will lead to a delay in the completion of the entire project. To identify the critical path, we need to calculate the activity float for each activity. Activity float is the difference between an activity’s Earliest start and its latest start date or the difference between the activity’s Earliest finish and its latest finish date, and it indicates how much the activity can be delayed without delaying the completion of the entire project. If the float of an activity is zero, then the activity is critical and must be added to the critical path of the project network. In this example, activities F and G have zero float and hence, are critical activities.
![[Pasted image 20240318174640.png]]

## Example 2

| Activiry | Precedents | Duration(in weeks) |
| -------- | ---------- | ------------------ |
| A        | _          | 5                  |
| B        | A          | 4                  |
| C        | A          | 5                  |
| D        | B          | 6                  |
| E        | C          | 3                  |
| F        | D,E        | 4                  |

#todo 
- [ ] Do on your own

## Example 3

![[Pasted image 20240427135733.png]]

**Ans:** It is not possible to add more entries, as it will form a loop.


#todo #A !!!
- [ ] Learn how to solve this.


**ref:** https://www.geeksforgeeks.org/software-engineering-critical-path-method/

