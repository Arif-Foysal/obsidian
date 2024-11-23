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
A failure occurs when the system no longer delivers a service that is consistent with its specification. A fault has the potential to cause a failure.     

**Availability tactics**, in turn, are designed to enable a system to prevent or endure system faults so that the system remains **compliant** with its specifications.

![[Availability tactics response 2024-11-23 20.24.07.excalidraw]]

![[Pasted image 20241123202747.png]]


### Detect Faults
Detecting faults is a critical step in ensuring a system's availability and reliability. It involves identifying failures, errors, or [[deviation]]s from expected behavior as early as possible to initiate corrective actions.

1. **Monitor**
	- **Purpose**: Observes the state of health of the system or its components to identify issues such as failures, congestion, or anomalies.
	- **Example Use Cases**:
	    - Detecting network congestion or a denial-of-service (DoS) attack.
	    - Performing periodic self-tests to check system functionality.
	    - Identifying faulty timestamps or missed heartbeats that indicate malfunction.

2. **Ping/Echo**
	- **Mechanism**: A pair of asynchronous request/response messages exchanged between nodes.
	- **Purpose**:
    - Confirms whether a system component is reachable.
    - Measures the [[Round Trip Time(RTT)]] (latency) for messages across a network path.
	- **Example Use Case**: A server sending a "ping" request to another server to verify if it's operational.
3. **Heartbeat**
	- **Mechanism**: Periodic messages sent between a system monitor and the monitored process.
	- **Purpose**:
    - Confirms the monitored process is alive and functioning.
    - Detects failures if heartbeats are missed.
	- **Special Case**: In systems using a **watchdog timer**, the monitored process must reset the timer periodically to indicate it's still active. Failure to do so signals a fault.
	- **Example Use Case**: Clustered databases use heartbeat signals to monitor the status of nodes.
4. **Timestamp**
	- **Purpose**: Verifies the order and correctness of events in distributed systems.
	- **Use Case**: Ensures message-passing systems maintain proper sequencing of operations, preventing logical errors due to time desynchronization.
5. **Condition Monitoring**
	- **Mechanism**: Monitors device or process conditions to ensure assumptions made during design are still valid.
	- **Purpose**: Detects and prevents the system from exhibiting faulty behavior by validating operating conditions.
	- **Example Use Case**: Monitoring the temperature of a server to ensure it operates within safe limits.
6. **Sanity Checking**
	- **Purpose**: Validates the reasonableness or correctness of specific operations or outputs.
	- **Scope**: Typically applied at interfaces or critical operation points.
	- **Example Use Case**: Verifying user inputs for logical errors (e.g., a negative age value).
7. **Voting**
	- **Mechanism**: Compares outputs from multiple components performing the same computation.
	- **Purpose**:
    - Ensures reliability by choosing the majority or correct result.
    - Depends on robust logic to resolve discrepancies.
	- **Example Use Case**: Aircraft control systems use voting across multiple redundant processors.
8. **Exception Detection**
	- - **Purpose**: Detects and handles abnormal conditions that disrupt normal system execution.
	- **Refinements**:
	    - **System Exceptions**: Identifies errors in system states or operations.
	    - **Parameter Fence**: Ensures parameters passed between components are within valid ranges.
	    - **Parameter Typing**: Validates data types for inputs or parameters.
	    - **Timeout**: Triggers fault detection if an operation exceeds a predefined duration.
9. **Self-Test**
	- **Mechanism**: Components test their own functionality, either periodically or on demand.
	- **Purpose**: Identifies and resolves faults proactively before affecting the overall system.
	- **Example Use Case**: A hard drive running a built-in self-test (BIST) during boot-up to detect sector errors.

### Recover From Faults

#### Preparation and repair
1. **Redundant Spare**
	- **Description**: A backup component or set of components is kept on standby to take over if the primary one fails.
	- **Purpose**: Ensures availability through redundancy.
	- **Example Use Case**: Hot standby servers in cloud systems that automatically take over when the primary server fails.
2. **Rollback**
	- **Description**: Restores the system to a previously known good state when a failure is detected.
	- **Purpose**: Provides a safe fallback to recover from errors.
	- **Example Use Case**: Database systems use transaction rollback to maintain data consistency.
3. **Exception Handling**
	- **Description**: Detects an exception and manages it to prevent the system from crashing.
	- **Purpose**: Maintains system stability and allows graceful recovery.
	- **Example Use Case**: A web application catching invalid user input and prompting for correction instead of crashing.
4. **Software Upgrade**
	- **Description**: Enables in-service updates to the software without affecting operations.
	- **Strategies**:
	    - **Function Patch**: Updates a specific function or module.
	    - **Class Patch**: Updates a class or collection of related code.
	    - **Hitless In-Service Software Upgrade (ISSU)**: Ensures seamless updates without any downtime.
	- **Example Use Case**: Rolling updates in Kubernetes clusters.
5. **Retry**
	- **Description**: Reattempts the operation under the assumption that the failure was temporary.
	- **Purpose**: Leverages the transient nature of some failures to recover without major intervention.
	- **Example Use Case**: Retrying a failed network request in a REST API.

---

6. **Ignore Faulty Behavior**
	- **Description**: Disregards messages or actions from a faulty source to prevent further issues.
	- **Purpose**: Isolates the fault to protect the rest of the system.
	- **Example Use Case**: Ignoring corrupted packets in a network protocol.
7. **Graceful Degradation**
	- **Description**: Maintains critical functions while allowing less critical ones to fail in the presence of faults.
	- **Purpose**: Ensures essential services remain operational during partial system failures.
	- **Example Use Case**: A video streaming service reducing video quality when server resources are constrained.
8. **Reconfiguration**
	- **Description**: Adjusts responsibilities among components to recover functionality.
	- **Purpose**: Maximizes system usability despite restricted resources.
	- **Example Use Case**: Load balancers redirecting traffic from a failed server to others in the cluster.
#### Reintroduction
1. **Shadow Mode**
	- **Description**: Runs a previously failed or upgraded component in a "shadow mode" (inactive yet functional) for monitoring before making it active again.
	- **Purpose**: Ensures reliability by validating components before fully reintegrating them.
	- **Example Use Case**: A database node being tested for correctness after repairs before rejoining the active cluster.
2. **State Resynchronization**
	- **Description**: Synchronizes the state of standby components with the active ones, ensuring they are ready to take over seamlessly.
	- **Purpose**: Avoids discrepancies in active and standby components during failover.
	- **Example Use Case**: RAID systems synchronizing disks for data redundancy.
3. **Nonstop Forwarding**
	- **Description**: Allows continued operation while recovering or validating routing information.
	- **Purpose**: Prevents service interruptions during component failures.
	- **Example Use Case**: Routers forwarding packets while recovering from a failed supervisor module.
4. **Escalating Restart**
	- **Description**: Restarts system components at varying levels of granularity to minimize service disruption.
	- **Purpose**: Optimizes recovery by starting with the smallest affected components and escalating if necessary.
	- **Example Use Case**: Restarting only the failing microservice in a distributed application before considering a full system reboot.
### Prevent Faults
1. **Removal From Service**
	- **Description**: Temporarily placing a system component in an **out-of-service** state to mitigate potential failures or prevent their propagation. 
	- **Purpose**: Allows maintenance or recovery of a component without affecting overall system stability.
	- **Example Use Case**: In cloud environments, a server is marked as "out of service" to apply updates or address detected issues without impacting user traffic.
2. **Transactions**
	- **Description**: Ensures that operations performed between distributed components are atomic, consistent, isolated, and durable (ACID properties). These properties ensure that the system remains in a valid state even when faults occur.
	- **Purpose**: Guarantees data integrity and consistency during and after faults.
	- **Example Use Case**: Banking systems use transactions to ensure money is either fully transferred or not transferred at all, preventing partial transfers in case of failure.
3. **Predictive Model**
	- **Description**: Uses monitored performance metrics and predictive algorithms to anticipate faults before they occur, allowing corrective action.
	- **Purpose**: Proactively avoids system failures by predicting and addressing them preemptively.
	- **Example Use Case**: Machine learning models analyzing server logs to predict when a hard drive is likely to fail, enabling preventive replacement.
4. **Exception Prevention**
	- **Description**: Implements techniques to prevent exceptions from occurring during system operation, reducing fault occurrences.
	- **Purpose**: Enhances system reliability by avoiding known error states and maintaining smooth execution.
	- **Example Use Case**: Input validation in web applications prevents SQL injection attacks, avoiding exceptions caused by malformed queries.
5. **Increase Competence Set**
	- **Description**: Expands the set of scenarios and states that a component can handle gracefully as part of its normal operation, instead of raising exceptions.
	- **Purpose**: Reduces the likelihood of faults by increasing a component’s ability to manage complex or unexpected states.
	- **Example Use Case**: A division algorithm that handles division by zero by returning a predefined value instead of throwing an exception.

## Tactics based questionnaire for availability
![[Pasted image 20241123223317.png]]

## Patterns for Availability
Availability patterns are strategies for maintaining system functionality in the presence of faults. Here's an explanation of the listed patterns:

1.  **Active Redundancy (Hot Spare)**
	- **Description**:  
	    All nodes in a protection group process identical inputs in parallel. Redundant spares maintain a synchronous state with the active node(s), allowing near-instant failover (milliseconds).
	- **Benefit**:  
	    Enables the fastest recovery time, as the spare is always up-to-date and ready to take over.
	- **Trade-offs**:
	    - High cost due to maintaining active spares.
	    - Increased system complexity.
	- **Example Use Case**: Critical systems like flight control systems or financial transaction systems.
2. **Passive Redundancy (Warm Spare)**
	- **Description**:  
	    Active nodes handle input traffic and periodically update redundant spares with their state. The spare is loosely synchronized and requires some delay to catch up during failover.
	- **Benefit**:  
	    Provides a balance between cost and recovery time.
	- **Trade-offs**:
	    - Slower recovery time compared to hot spares.
	    - Costs less than maintaining hot spares but still incurs synchronization overhead.
	- **Example Use Case**: Backup databases in enterprise systems.
3. **Cold Spare**
	- **Description**:  
	    Redundant spares remain powered down or inactive until a failover occurs. Upon activation, the spare undergoes a power-on reset before taking over.
	- **Benefit**:  
	    Least expensive redundancy option.
	- **Trade-offs**:
	    - Recovery time is significantly longer.
	    - Spares may require more time for initialization.
	- **Example Use Case**: Disaster recovery setups in data centers
4. **Triple Modular Redundancy (TMR)**
	- **Description**:  
	    Three components process identical inputs, and their outputs are forwarded to voting logic. The voting mechanism detects inconsistencies and reports faults.
	- **Benefit**:
	    - Simple to understand and implement.
	    - High reliability; the likelihood of multiple simultaneous failures is very low.
	- **Trade-offs**:
	    - Cost increases with replication.
	    - Sweet spot between cost and availability is typically at three components.
	- **Example Use Case**: Aerospace systems or critical hardware like CPU fault detection.
5. **Circuit Breaker**
	- **Description**:  
	    Stops retry attempts after repeated failures to prevent overloading the system. It "trips" and prevents further calls until the service is deemed operational again.
	- **Benefit**:
	    - Prevents endless retries, which could degrade overall system performance.
	    - Centralizes retry logic and recovery policies.
	- **Trade-offs**:
	    - Choosing appropriate timeout and retry values is critical.
	    - Overly sensitive circuit breakers may reduce availability due to false positives.
	- **Example Use Case**: Microservice architectures where service calls may fail due to dependency issues or temporary network failures.
## Other Commonly Used Availability Patterns

1.  **Process Pairs**
	- **Description**:  
	    This pattern involves pairing a primary process with a backup process. The backup process continually checkpoints (records its state) and, if necessary, rolls back to a safe state.
	    - In case of failure, the backup process takes over seamlessly with minimal disruption.
	- **Key Mechanism**:
	    - **Checkpointing**: Regularly saves the state of the system.
	    - **Rollback**: Reverts to the most recent safe state if an error occurs.
	- **Benefit**:
	    - Minimizes downtime and preserves system continuity.
	    - Reduces the risk of data loss by maintaining up-to-date checkpoints.
	- **Trade-offs**:
	    - Overhead of frequent checkpointing.
	    - Complexity of maintaining synchronization between processes.
	- **Example Use Case**: High-availability systems in telecommunications and banking.

2.  **Forward Error Recovery**
	- **Description**:  
	    Unlike rollback recovery (which reverts to a prior safe state), this pattern resolves errors by advancing to a new, desirable state that is free from faults.
	    - Relies on mechanisms like data redundancy or error-correcting codes to correct issues and resume operation.
	- **Key Mechanism**:
	    - **Built-in Error-Correction**: Automatically detects and corrects errors.
	    - **Safe State Transition**: Moves the system to a functional state even if it is slightly degraded.
	- **Benefit**:
	    - Avoids the delays associated with falling back to a previous state or retrying operations.
	    - Ensures the system keeps progressing, even if in a reduced capacity.
	- **Trade-offs**:
	    - Additional complexity in designing robust error-correction mechanisms.
	    - May incur some degradation in system performance or functionality during recovery.
	- **Example Use Case**: RAID systems that use parity to recover from disk errors without requiring a rollback.