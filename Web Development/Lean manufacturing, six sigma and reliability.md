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

So,
Reliability = 0.95 x 0.95 x ( 1 - (1 - 0.70)^3 ) x ( 1 - ( 1 - 0.75 )^2 ) x 0.90
		= 74.09%
#### Reliability as a function of time (Bath Tub Curve)
![[Pasted image 20241016132523.png]]

- The initial region that begins at time zero( t = 0 ) when a customer first begins to use the product is characterized by a high but rapidly decreasing failure rate. This region is known as the Early Failure Period (also referred to as Infant Mortality Period, from the actuarial origins of the first bathtub curve plots). This decreasing failure rate typically lasts several weeks to a few months.

- Next, the failure rate levels off and remains roughly constant for (hopefully) the majority of the useful life of the product. This long period of a level failure rate is known as the Intrinsic Failure Period (also called the Stable Failure Period) and the constant failure rate level is called the Intrinsic Failure Rate. Note that most systems spend most of their lifetimes operating in this flat portion of the bathtub curve.

- Finally, if units from the population remain in use long enough, the failure rate begins to increase as materials wear out and degradation failures occur at an ever increasing rate. This is the Wear out Failure Period.

**Reliability Function**
$$R(t) = e^{-\lambda t}$$
Here, 
- **R(t)** represents the probability that a system will function without failure over a time period **t**, assuming an exponential failure distribution.
- **λ** is the failure rate, **a constant** for systems with a constant hazard rate, which is typical in the useful life period of the "Bathtub Curve."

**Reliability of a series system**
$$R(t) = e^{-{\lambda(total)} * t}$$
Where, 
- **λ(total)** = (λ1 + λ2 + .....+λn) / given time

**Mean Time Between Failures (MTBF)**
$$MTBF = \frac{1}{\lambda}$$
Here,
- **MTBF** is defined as the average time between inherent failures during system operation.
- **λ** is the failure rate ( **failure per unit of time** ).
- A higher MTBF indicates that the system is expected to operate longer before experiencing a failure, making it more reliable.
**MTBF of a series system**
$$MTBF = \frac{1}{\lambda(total)}$$

**MTBF of a parallel system**
$$MTBF = \frac{1}{\lambda}(1+\frac{1}{2}+....+\frac{1}{n})$$

**Practice Problems**

1. Earlier statistics show that a component has a failure rate of 0.07 per 1000 hours. Calculate the MTBF & the probability that it will survive at least 5000 hours.
**Sol:**
- Failure rate **λ** = (0.07/1000) = 0.00007
Given,
- Time **t** = 5000 hours
So,
MTBF = 1/λ = 1/0.00007 = **14285.71 hours**

And, 
$$R(t) = e^{-\lambda t}$$
$$R(t) = e^{-0.00007 (5000)}$$
$$R(t) = 0.7046$$
So, Probability that it will last at least 5000 hours is **70.46%**

**series system**
2. A computer system has 4 components in series with failure rates (per 1000 hours) of 0.061, 0.048, 0.053, and 0.038. Find the probability that the system will survive for at least 6000 hours and the MTBF of the system.
**solution:**
Here, 
$$\lambda(total) = (0.061+0.048+0.053+0.038)/1000 = 0.0002$$

$$R(t) = e^{-{\lambda(total)} * t}$$
$$R(t) = e^{0.0002 * 6000}$$
And, 
$$MTBF = \frac{1}{\lambda(total)}$$
$$MTBF = \frac{1}{0.0002}$$

**parallel system**
3. Failure rate of a component is 0.10 per 1000 hours. Find the MTBF for:
i. The individual component
ii. When 2 of it are connected in parallel
iii. When 3 of it are connected in parallel
iv. When 4 of it are connected in parallel
Ans: 10,000 hours;15,000 hours; 18,333.33
hours; 20,833.33 hours

4. Failure rate of a component is 0.10 per1000 hours. Find
the MTBF when 4 of it are connected in parallel. Find
probability, that it will survive for 6000 hours?
Solution: MTBF= (1/ λ)\*(1+1/2+1/3+1/4)= 20,830 hours
λ_Total = 1/MTBF = 1/20,830= 4.80076\*10^-5
Probability of surviving for 6000 hours
R(6000) = e^(-λ_total\*t) = e^(-4.80076\*10^-5\*6000)
=.749=74.9\%

**Combined Systems**
5. A subassembly of a computer system consists of 3 components (A) in parallel and one component (B) in series. Reliabilities per 100 hour of A = 0.75 and B = 0.97. Find the system failure rate and MTBF. And Find the probability it will work for 300 hours.
**sol:**
The system:
![[Drawing 2024-10-16 15.14.07.excalidraw]]
For B,
$$0.97 = e^{-\lambda{b} (100)}$$
$$\ln{0.97} = \ln{e^{-\lambda{b} (100)}}$$
$$\ln{0.97} = {-\lambda{b} (100)}$$
$$\lambda{b = \frac{-\ln{0.97}}{100}} = 3.04*10^{-4}\text{ failures/hour}$$

For A, 
$$0.75 = e^{-\lambda{a} (100)}$$

$$\ln{0.75} ={-\lambda{a} (100)}$$
$$\lambda{a}=\frac{-\ln{0.75}}{100} = 2.87*10^{-3}\text{ failures/hour}$$
Finding MTBF(A),
$$MTBF(A) = \frac{1}{\lambda{a}}(1+\frac{1}{2}+\frac{1}{3})$$
$$MTBF(A) = \frac{1}{2.87*10^{-3}}(\frac{11}{6}) = 638.79 \text{ hours}$$
So,
$$\lambda {a(total)} = \frac{1}{MTBF(A)} = \frac{1}{638.79}=1.56*10^{-3}\text{ /hour}$$
Now, 
$$\lambda(total) = \lambda{a}(total) + \lambda{b}(total)$$
$$\lambda(total) = 1.56*10^{-3}+3.04*10^{-4} = 1.869*10^{-3}\text{ / hour}$$

And,
$$MTBF(system) = \frac{1}{\lambda{total}}$$
$$MTBF(system) = \frac{1}{1.869*10^{-3}\text{ / hour}} = 534.91hours$$
**probability it will work for 300 hours:**
$$R(t) = e^{-{\lambda(total)} * t}$$
$$R(300) = e^{-{1.56*10^{-3}} * 300} =62.6\% $$

![[Six sigma]]
