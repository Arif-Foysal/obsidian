### What is quality?
Quality refers to the characteristics of a product or service that defines it's ability to consistently meet or exceed customer's expectations.

**Quality revolution** started in [[Japan]] after [[World War II]].

### Commonly considered quality aspects

- **Performance-appropriate functionality**: Refers to how well the product or service performs its intended function and meets user expectations.
    
- **Conformance-products response to specifications**: Measures whether the product or service conforms to the predefined standards and specifications.
    
- **Reliability-probability of performance**: Relates to the likelihood that the product or service will perform its function consistently over time.
    
- **Durability-longevity**: Focuses on the product's or service’s ability to last over time without deteriorating.
    
- **Innovative feature-more than normal need**: Looks at whether the product or service offers features that go beyond standard needs or expectations, adding extra value.
    
- **Service after sale-customer care**: Emphasizes the quality of customer service and support provided after a purchase is made.
    
- **Maintenance and serviceability-self maintenance**: Assesses how easy it is to maintain the product or service and whether users can perform maintenance themselves.
    
- **Ease of use**: Considers how simple and intuitive the product or service is to use.
    
- **Aesthetics**: Involves the visual appeal or design of the product or service.
    
- **Others**: Any additional aspects that may not fall under the above categories but still contribute to the quality of the product or service.

### Cost of quality
Cost of quality is the total cost to ensure quality in products or services.

![[Drawing 2024-10-15 13.25.04.excalidraw|{width:100vw}]]

- **Cost of control (Conformance)**: These are the costs associated with ensuring that the product or service conforms to quality standards. This includes:
    
    - **Prevention**: Costs incurred to prevent defects before they happen. Examples include training, process improvements, documentation, monitoring, good machinaries and quality planning.
    - **Appraisal**: Costs related to inspecting and testing products to ensure they meet quality standards. This includes activities like inspections, detecting defects in its products, audits, and testing.
- **Cost of failure to control (Nonconformance)**: These are the costs that occur when quality standards are not met, leading to defects. This includes:
    
    - **Internal failure**: Costs related to defects found before the product or service reaches the customer. Examples include rework, scrap, and downtime.
    - **External failure**: Costs that arise when defects are found after the product or service has reached the customer. This includes warranty claims, returns, and reputation damage.

### QA vs QC

| Criteria           | Quality Assurance (QA)                                                                 | Quality Control (QC)                                                                 |
|--------------------|----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| **Definition**      | QA is a set of activities for ensuring quality in the processes by which products are developed. | QC is a set of activities for ensuring quality in products. The activities focus on identifying defects in the actual products produced. |
| **Type of action**  | Proactive                                                                              | Reactive                                                                              |
| **Responsibility**  | Everyone on the team involved in developing the product is responsible for quality assurance. | Quality control is usually the responsibility of a specific team that tests the product for defects. |
| **As a tool**       | QA is a managerial tool                                                                | QC is a corrective tool                                                               |

### Total Quality Management(TQM)
**Total Quality Management (TQM)** is a holistic approach to long-term success through improving quality and customer satisfaction. It involves the active participation of all members of an organization in the continuous improvement of processes, products, services, and the overall organizational culture.

**Tools of TQM:**
1. Pareto Analysis.
2. Cause-Effect Diagram.
3. Control Chart.

### Pareto Analysis
**Pareto analysis** is a decision-making technique used to identify the most important factors in a given situation. Based on the 80/20 rule (also known as the Pareto Principle), it suggests that roughly 80% of effects come from 20% of causes.

**Example:**

| Defect Time     | Frequency |
| --------------- | --------- |
| Wrong dimension | 55        |
| Wrong material  | 100       |
| Scratch         | 30        |
| Shrinkage       | 70        |
| Wear            | 10        |
| Others          | 25        |

Sol:

>[!Tip]
>Sort by frequency in descending order

| Defect Time     | Frequency | % of frequency        | Cumulative % |
| --------------- | --------- | --------------------- | ------------ |
| Wrong material  | 100       | (100/290)100 = 34.48% | 34.48        |
| Shrinkage       | 70        | (70/290)100 = 24.13%  | 58.62        |
| Wrong dimension | 55        | (55/290)100 = 18.96%  | 77.59        |
| Scratch         | 30        | (30/290)100 = 10.34%  | 87.93        |
| Others          | 25        | (25/290)100 = 8.62%   | 96.55        |
| Wear            | 10        | (10/290)100 = 3.44%   | 100.00       |
| **Total:**      | **290**   | 100%                  |              |


**Plotting pareto chart:**

![[Drawing 2024-10-15 20.38.40.excalidraw|{width:50%}]]


### Cause Effect Diagram (Fish Bone Diagram)
A **Cause and Effect Diagram**, also known as a **Fishbone Diagram** or **Ishikawa Diagram**, is a tool used to systematically identify root causes of a problem or effect. It is called a "fishbone" because its shape resembles the skeleton of a fish. The problem (or effect) is placed at the "head," and the various causes are listed along the "bones" of the diagram

#### The 6 M's of the Fishbone Diagram
In manufacturing and process improvement, the 6 M's represent common categories of causes that might lead to defects or problems:

1. **Manpower**: Human factors, including lack of training, skill, or human error.
2. **Machines**: Equipment and tools used in production, such as faulty machines, improper maintenance, or wear and tear.
3. **Materials**: Raw materials or supplies, including issues with quality, availability, or incorrect materials.
4. **Methods**: Processes and procedures, including inefficiencies, outdated practices, or lack of standardization.
5. **Measurements**: Accuracy and precision of measurements, including incorrect data collection or flawed testing methods.
6. **Mother Nature (Environment)**: External conditions, including environmental factors such as temperature, humidity, or physical workspace.

**Example:**
In **BSRM Steel Mill**, they face a problem called **"Roof Leakage."** They identified some causes that may be the reasons behind the problem. Those are:

1. **3 persons** were needed to operate the process, but only **2 persons** were available.
2. There was a lot of **dust in the raw material**.
3. **Electricity was off** due to a thunderstorm.
4. The **highest temperature** of molten metal should have been **1670°C**, but it was **1750°C**.
5. The **machine hose pipe** was **loose**.
6. The operators had only **3 months of experience** in the steel sector.
7. The **raw material needed hard pressing** after discharging, but it was **not done properly**.

![[Fish-bone-example-2024-10-15 21.52.34.excalidraw|{width:90vw}]]

### Control Chart
A **Control Chart** is a graph used to monitor how a process performs over time. It shows whether the process stays consistent or if there are unexpected changes. The chart has:

- A center-line for the average performance.
- Upper and lower limits that show the acceptable range of variation.

![[Pasted image 20241015221648.png]]


#### Types of Control Charts:

- **Variable Control Charts**: Used for data that can be measured on a continuous scale, such as weight, length, or temperature. Examples include:
    - X-bar Chart: Monitors the mean of a process.
    - R-chart (Range chart): Tracks the variation within a sample.
- **Attribute Control Charts**: Used for data that is counted, like defects or pass/fail outcomes. Examples include:
    - p-chart: Monitors the proportion of defective items in a sample.
    - c-chart: Tracks the number of defects in a single unit.

### Taguchi Loss Function
- **Purpose**: It calculates the **cost** or **negative impact** when a product or process deviates from its ideal target, even if it stays within acceptable limits.
- **Formula**: The function uses a mathematical expression to measure how much the deviation from the target affects the overall cost.
- **Focus on Consistency**: Unlike traditional methods that focus on staying within tolerance limits, the Taguchi method seeks to minimize variations to improve quality and reduce costs over time.

### **Loss Function Formula**

The formula is given as:  
**L(x) = k(x – T)²**

- **L(x)**: The loss or cost due to deviation from the target value.
- **k**: A constant that determines the sensitivity of the loss (how much a deviation costs).
- **x**: The actual value, which could deviate from the target.
- **T**: The target or ideal value.
#### **Example: Software Response Time Optimization**

- **Problem**: A company sets a target response time of 2 seconds for its e-commerce platform, but during peak hours, the response time increases to 3 seconds. The task is to find the loss using the Taguchi Loss Function, with a constant **k = 100**.
    
    **Solution**:
    
    - **Target (T)**: 2 seconds
    - **Actual Value (x)**: 3 seconds
    - **Constant (k)**: 100
    
    Using the formula:  
    **L(x) = k(x – T)²**  
    **L(x) = 100(3 – 2)² = 100 × 1² = 100 dollars**
    
    Therefore, the loss due to the deviation in response time is 100 dollars.

### Kaizen
(Continuous Improvement)
[[Kaizen]]

![[Pasted image 20241015223936.png]]



