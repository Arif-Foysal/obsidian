### Reliability
Reliability is the ability of a system or product to perform it's required function under a specific condition for a defined period of time.
#### **Types of System**

- **Series System**:
    
    - All components are arranged in series. For the system to work, every component must function correctly.
    - **Key Characteristic**: If one component fails, the entire system fails.
- **Parallel System**:
    
    - In contrast to a series system, a parallel system will only fail if all components fail.
    - **Key Characteristic**: This configuration allows for redundancy, increasing the system's overall reliability.
- **Combination System**:
    
    - This system contains elements of both series and parallel systems. Some components are in series while others are replicated in parallel, allowing for a more complex and resilient system.

#### Reliability in a Series System
![[Pasted image 20241016112611.png]]
**Example:**
A simple computer consists of a processor, a bus and a memory. The computer will work only  if all three are functioning properly. The probability that the processor is functioning is 0.99, that the bus is functioning 0.95 and the memory is functioning is 0.99. Find out the reliability of the system.

**Solution:**

Reliability of the series system:
0.99 x 0.95 x 0.99 = 0.93

So, system is 93% reliable.


#### Reliability in a Parallel System
![[Pasted image 20241016112638.png]]

**Example**
![[Pasted image 20241016120058.png]]

**Sol:**
Reliability of the parallel system:
$$1 - (1 - 0.97)^5 = 99.99\%$$

#### Reliability in combination system
![[Pasted image 20241016120836.png]]






### Six Sigma
Six Sigma is a set of techniques and tools for process improvement.

**Objective**: The goal of Six Sigma is to improve the quality of processes by identifying and removing the causes of defects and **minimizing variability** in manufacturing and business processes.

#### Six sigma defective rates

The chart here explains the defect rates at different sigma levels:

- **±3 sigma**: 0.27% defects or 2700 defects per million (ppm).
- **±4 sigma**: 63 ppm.
- **±6 sigma**: Only 0.002 ppm, which translates to 3.4 defects per million opportunities, representing the ultimate goal of Six Sigma—near-zero defects.
![[Pasted image 20241016110812.png]]


![[Pasted image 20241016110950.png]]

#### Lean Six Sigma
**Lean Six Sigma** combines the strategies of **Lean** (which focuses on **reducing waste** and **improving process speed**) and **Six Sigma** (which focuses on **reducing variability** and defects and improving process quality).





