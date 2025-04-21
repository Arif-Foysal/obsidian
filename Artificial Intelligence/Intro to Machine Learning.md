## Computational Engineering

Also called **Soft Computing**
It focuses on designing mining algorithms and systems that **learn from big data** and make **intelligent decisions**

- **Knowledge engineering:** Knowledge engineering is a field of artificial intelligence (AI) that tries to emulate the judgment and behavior of a human expert in a given field.

- **Artificial Intelligence**
	- The broader concept of machines being able to **carry out tasks in a "smart" way**
- **Machine Learning**
	- Algorithms that allow computers to learn from examples without being explicitly programmed.
- **Artificial Neural Networks**
	- Brain inspired machine learning models.
- **Deep Learning**
	- A subset of ML which uses deep artificial neural networks as models and automatically builds a hierarchy of data representations.


![[Pasted image 20250410133727.png]]

![[Pasted image 20250410133815.png]]


## The DIKW Hierarchy

- **Data**: Raw facts (e.g., numbers, text without meaning)
    
- **Information**: Processed data (answers "who, what, where, when")
    
- **Knowledge**: Insight from information (answers "how, why")
    
- **Wisdom**: Using knowledge to make good decisions

#### **Example**:

| Raw Data    | →   | "Student scored 80 in Math"                        |
| ----------- | --- | -------------------------------------------------- |
| Information | →   | "Student's Math scores increased over months"      |
| Knowledge   | →   | "Extra practice improved the scores"               |
| Wisdom      | →   | "Recommend consistent practice to future students" |
![[Pasted image 20250410134438.png]]

## Big data and data science
#### **Big Data** – Defined by the 3 V’s:

- **Volume**: Massive amounts
    
- **Variety**: Different types (text, images, etc.)
    
- **Velocity**: Speed of generation  
    (_Others: Variability, Veracity, Value, Visualization_)
    

#### **Data Science**: 
Combines AI, ML, and data analysis to extract knowledge from structured and unstructured big data.

## Data analysis vs data mining

**Data analysis**
Data Analysis involves extraction, cleaning, transformation, modeling and visualization of data with an objective to extract important and helpful information which can be additional helpful in deriving conclusions and make choices. The main purpose of data analysis is to search out some important information in raw data so the derived knowledge is often used to create vital choices.

**Data Mining**
Data mining could be called as a subset of Data Analysis. It is the exploration and analysis of huge knowledge to find important patterns and rules.

**Types of data**
- Unstructured data: Unstructured data have no rigid structure, e.g. images, video, natural language text, and speech etc.
- Structured data: Structured data is like a table.
![[Pasted image 20250410144614.png]]



## Machine Learning

Allowing Machines to learn from **past data (training data)** to make **predictions or decisions**

ML is made up of 3 parts:

- **The computational algorithm at the core of making determinations.**
    
- **Variables and features that make up the decision.**
    
- **Known output for training**

#### **Input/Output in ML**:

- Input: Features (e.g., study hours, attendance)
    
- Output: Label (e.g., pass/fail)

## Types of Machine Learning

![[Pasted image 20250410150252.png]]

| Type                | Description                           | Example                              |
| ------------------- | ------------------------------------- | ------------------------------------ |
| **Supervised**      | Labeled data (input + correct output) | Classify emails as spam/not          |
| **Unsupervised**    | No labels; find hidden patterns       | Customer segmentation                |
| **Semi-supervised** | Mix of labeled and unlabeled data     | Tagging some emails, predicting rest |
| **Reinforcement**   | Learn by trial/error with rewards     | Teaching AI to play a game           |

### Supervised Learning
Supervised learning means the model is trained on a dataset that already has **input features** and **correct output labels**.

**Examples:**
- [[Artificial Neural Network]]
- [[Bayes Net]]
- [[Support Vector Machine]]
- [[Hidden Markov Model]]
- [[Decision Tree Training]]

#### **Classification**
Classification is about **predicting a category**.

##### 🧪 Example:

You want to **predict whether a student will pass or fail**.

You use input features like:

- Study hours
    
- Sleep hours
    
- Attendance
    
- Previous scores
    

The model learns from past examples and then predicts:  
➡️ **"Pass"** or **"Fail"**

This is a **classification task** because the output is a **category**, not a number.


##### **Types of Classification Problems:**
- **Binary-class**: Only **two classes**  
    → e.g., Pass or Fail, Yes or No, Spam or Not Spam
- **Multi-class**: More than two **mutually exclusive** classes  
    → e.g., Grade: A, B, C, D, F    
- **Multi-label**: Each item can belong to **multiple classes at the same time**  
    → e.g., A news article tagged with: Politics, Education, and Technology
#### Regression
Regression is about **predicting a number** — something **continuous**, **real-valued**, and **measurable**.

### 🧪 Example:

You want to **predict the price of a house**.

You use features like:

- Square footage
- Number of bedrooms
- Number of bathrooms
- Age of the house

The model learns from data and predicts:  
➡️ **A price like $250,000**

This is a **regression task** because the output is a **numeric value**, not a category.

### Unsupervised Learning

- Data has **no labels**.
- The machine learns to **find patterns or groups** in the data on its own.

**Examples:**
- [[K-Means Clustering]]
- [[Modified K-Means Clustering]]
- [[Hierarchical Clustering]]
- [[Fuzzy-C-Mean Clustering]]
#### ✨ Example: **Clustering**

- Grouping customers based on behavior
- Techniques:
    - **K-Means** (groups data into K clusters)
    - **Hierarchical Clustering** (builds a tree of clusters)

### Semi-Supervised Learning

- A **mix** of labeled and unlabeled data.
- The model uses the **labeled data to learn**, then applies that learning to **label the rest**.

#### ✨ Example:
- You have 1000 emails, but only 100 are labeled as “spam” or “not spam”.
- You train the model on those 100 labeled emails.
- The model predicts labels for the remaining 900.
- You now have a bigger labeled dataset without manually labeling all.

> ✅ Saves time and cost in labeling large datasets.

### Reinforcement Learning (RL)

- The model (called an **agent**) learns by **interacting** with its environment.
- It takes actions, gets **rewards or punishments**, and **learns from feedback**.

![[Pasted image 20250410152236.png]]

### ✨ Example: Tic-Tac-Toe

- The agent plays the game.
    
- It learns **which moves lead to winning** and **which lead to losing**.
    
- Over time, it becomes better at playing by maximizing rewards (wins).

> 🎯 Focus is on **learning the best strategy** over time.



### Transfer Learning

- Instead of training a model from scratch, you **reuse a pre-trained model**.
    
- Useful when you have **little data** for your own task.
### ✨ Example:

- Use a model trained on millions of images (like from ImageNet).
    
- Fine-tune it to detect cracks in walls using only 200 labeled images.
    

> 🧠 The model already “knows” basic things like edges, shapes, etc. — you just adapt it.

### Active Learning

- You have a mix of labeled and unlabeled data.
    
- Instead of labeling all, you **select the most important/unusual data points to label**.
    
- Then train the model with labeled + newly labeled data points.

>🧠 Smart labeling to reduce effort and increase model quality.


### Data collection

Before you collect data, you should ask these key questions:

- **What problem are we trying to solve?**
    
    - Helps decide what type of data you need.
        
- **What data sources already exist?**
    
    - Can we use public data or do we need to create new datasets?
        
- **What privacy concerns are there?**
    
    - Especially important if dealing with user info, medical data, etc.
        
- **Is the data public or private?**
    
    - Public data is easier to access but may not always match your needs.
        
- **Where should we store the data?**
    
    - Local, cloud (AWS, Google Cloud), databases, etc

### Data Preparation
The goal is to **turn raw data into clean, structured, and machine-learnable data**.

#### **2.1 Data Cleaning**

- Fixes errors, fills in gaps, and removes noise.
    
- Includes:
    
    - **Imputing missing values** (e.g., using mean or median)
        
    - **Smoothing** noisy data (e.g., outlier removal)
        
    - **Resolving inconsistencies** (e.g., "Male", "male", "M" all mean the same)
#### 🔗 **2.2 Data Integration**

- Combine data from **multiple sources** like:
    - Two databases
    - Different tables or files

📌 _Example_: Joining a “Student_Info” table with a “Test_Scores” table using a student ID.

---

#### 🔁 **2.3 Data Transformation**

Make data machine-learnable. Includes:

##### a) **Encoding**

- Convert **categorical data** (like "Color: Red, Blue") into numbers.
    
- 📌 _One-Hot Encoding Example_:  
    "Red", "Green", "Blue" → `[1 0 0]`, `[0 1 0]`, `[0 0 1]`
    

##### b) **Normalization**

- Rescale values to a **common range** (like 0 to 1)
    
- 📌 _Example_: Min-Max Scaling  
    Age 18 → 0.0, Age 60 → 1.0
    

##### c) **Aggregation**

- Combine multiple values into summaries
    
- 📌 _Example_: Get a student's **total and average score** across subjects
    

---

#### 🔽 **2.4 Data Reduction**

Reduce data size without losing valuable info.

- **Feature Selection**: Keep only useful columns
    
- **PCA (Principal Component Analysis)**: Combine related features into fewer ones
    
- **Clustering**: Group similar data points

---

#### 📊 **2.5 Data Discretisation**

Convert **continuous values** into **categories/bins**.

📌 _Example_:

- Ages: 23, 45, 31, 50, 27
    
- After discretization:
    
    - 23 → Young Adult
        
    - 45 → Middle-aged
        
    - 31 → Adult
        
    - 50 → Senior

---

### 📂 **3. Data Splitting**

Split the dataset into 3 parts:

#### 1. **Training Set**

- Used to **train the model**.
    
- Model learns patterns from this data.
    

#### 2. **Validation Set**

- Used to **tune the model** during training.
    
- Helps avoid **overfitting**.
    

#### 3. **Test Set**

- Used only at the end to **evaluate model performance** on unseen data.
    

---

### 🔀 Splitting Strategies:

|Type|Use Case|
|---|---|
|**Random Splitting**|Basic, for general datasets|
|**Stratified Splitting**|Maintains class balance (good for classification)|
|**Time Series Splitting**|For time-based data, respects order|
|**K-Fold Cross-Validation**|Data is split into K parts, each used for testing once|
|**Leave-One-Out**|Each sample is tested one at a time (very detailed, slow)|

---

### 🔁 Summary:

|Step|Goal|
|---|---|
|**Data Cleaning**|Fix errors and fill in missing values|
|**Integration**|Merge multiple data sources|
|**Transformation**|Convert and scale data|
|**Reduction**|Make data smaller, simpler|
|**Discretisation**|Turn numbers into categories|
|**Splitting**|Train, tune, and test your model fairly|

