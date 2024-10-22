#projectManagement #software-engineering 

[[CMMI]]

COCOMO is a model used for estimating the cost, effort, and development time for software projects. It categorizes projects into three types based on their complexity:
- **Organic:** Small, simple projects with small teams and well-understood requirements. Good experienced team.
- **Semi-Detached:** Medium-sized projects with more complex requirements and larger teams.
- **Embedded:** Large, highly complex projects involving real-time systems, hardware-software integration, and stringent requirements.
### Effort and Development Time

**Effort (in person-months)**:

$$\text{Effort (PM)}= a×(KLOC)^b$$
where:
- KLOC is the number of thousands of lines of code.
- a and b are constants based on the project type.

**Development time (in months)**
$$Time (TDEV)=c×(Effort)^d$$

where:

- ccc and ddd are constants based on the project type.
**Average staff size**
$$floor(\frac{Effort}{Time})$$

### **COCOMO Constants Based on Project Type**

| **Project Type** | **a** | **b** | **c** | **d** |
| ---------------- | ----- | ----- | ----- | ----- |
| Organic          | 2.4   | 1.05  | 2.5   | 0.38  |
| Semi-detached    | 3.0   | 1.12  | 2.5   | 0.35  |
| Embedded         | 3.6   | 1.20  | 2.5   | 0.32  |
## Function point

<div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe 
        src="https://www.youtube.com/embed/TfgNgD9K-bA?si=cvbsneUdvOpvIqZ-" 
        title="YouTube video player" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
        allowfullscreen
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;">
    </iframe>
</div>

## Practice problems:

![[Pasted image 20241001233526.png]]
**Question:** Justify the complexity category according to COCOMO of the project described in the above scenario. If you want to develop the above project in the C language where the average lines of code needed per function point is 128, then find all the COCOMO parameters (Use the function point from Question 1).

### **Scenario Summary**:

You are leading a project to develop a **Medical Management System** for healthcare professionals. The system handles patient records, medical inventory, and generates various reports. It interfaces with external systems, like government health databases and a telemedicine platform. Assume moderate complexity for inputs, outputs, inquiries, and high complexity for external files.

### **Step 1: Calculate the Count Total (CT) using 5 information domains**

We identify the 5 information domains as follows:

1. **Number of User Inputs**: Adding new patient records, updating records, adding medical items.
    - Estimated: 3 inputs.
2. **Number of User Outputs**: Generating patient summary, medical inventory report, and transaction receipts.
    - Estimated: 3 outputs.
3. **Number of User Inquiries**: Inquiring about patient history, checking medical item availability.
    - Estimated: 2 inquiries.
4. **Number of Files**: Patient records, medical items, transaction tracking.
    - Estimated: 3 files.
5. **Number of External Interfaces**: Interfacing with a government health database and a telemedicine platform.
    - Estimated: 2 interfaces.

Thus, the **Count Total (CT)** is:

| **Parameter**            | **Count** |     | **Simple**<br>[ ] | **Average**<br>[x] | **Complex**<br>[ ] | Total |
| ------------------------ | --------- | --- | ----------------- | ------------------ | ------------------ | ----- |
| # of user inputs         | 3         | x   | 3                 | 4                  | 6                  | 12    |
| # of user outputs        | 3         | x   | 4                 | 5                  | 7                  | 15    |
| # of user inquaries      | 2         | x   | 3                 | 4                  | 6                  | 8     |
| # of Files               | 3         | x   | 7                 | 10                 | 15                 | 30    |
| # of external interfaces | 2         | x   | 5                 | 7                  | 10                 | 14    |
**Total:** (12+15+8+30+14) = 79

>[!Note]
>The table is called **Function point table**. The values for simple, average and complex are called **weighing factor**, and they are fixed.

### Step 2: Assign Complexity and Calculate Function Points (FP)

Using the formula for Function Points:

![[Pasted image 20241002011637.png]]
**F** is based on 14 questionaries. These questionaries can be ansewer in range 0 to 5. here, 
![[Pasted image 20241002011820.png]]

For example, here the summation of F is 29

### Step 3: Convert Function Points to Lines of Code (LOC)
Given that we are developing in **C language** with an average of **128 LOC per function point**, calculate the total **Kilo Lines of Code (KLOC)**:

LOC = 29\*128 = 3712
KLOC = 3712/1000 = 3.712

### Step 4: Apply the COCOMO Model

Since this is a **Semi-Detached** project (moderate complexity, mixed experience team), use the Semi-Detached model constants:

- a=3.0,  b=1.12
- c=2.5, d=0.35

**Effort Calculation:**

E = 3 x (3.712)^1.12 = 13.034 person-months

**Development Time Calculation:**

D = 2.5 x (13.034)^0.35 = 6.140 months


