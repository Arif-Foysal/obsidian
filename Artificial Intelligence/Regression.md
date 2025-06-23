#Machine-Learning #artificial-intellegence 

## 📈 **What is Regression?**

- **Regression** helps us **understand relationships** between **independent variables** (inputs/features) and a **dependent variable** (output).
    
- It’s used when the **output is a continuous numerical value**.
    
- It’s part of **supervised learning** because we work with **labeled data** (we know the actual outputs).

### 🎯 **Example: Predicting House Prices**

Let’s say we want to predict the **price of a house**.

🔢 **Features (inputs)**:

- Square footage
    
- Number of bedrooms
    
- Number of bathrooms
    
- Age of the house
    

💰 **Target/output**:

- Price of the house (a number like $250,000)

The regression model will **learn patterns** from past data and then **predict** prices of new houses.

![[Pasted image 20250501094307.png]]
## **Types of Linear Regression**

### 1️⃣ **Simple Linear Regression**

- **One input** (independent variable), one output
- 📌 _Example_: Predict house price **only** based on square footage
- Formula:
    y=mx+b
    y=w0 + w1x
    where:
- y = predicted value (dependent variable)
- x = input feature (independent variable)
- m = slope (how much y changes with x)
- b = y-intercept (value of y when x = 0)
### 2️⃣ **Multiple Linear Regression**

- **Multiple inputs**, one output
    Multiple Linear Regression is used when you want to predict a **single output** using **two or more inputs**.
- 📌 _Example_: Predict house price based on square footage, bedrooms, and bathrooms
- Formula:
$$y=b0​+b1​x1​+b2​x2​+⋯+bn​xn​$$
Where:
- yyy = predicted value
- x1,x2,...,xn​ = input features
- b0 = intercept
- b1,b2,...,bn​ = coefficients for each featur
### 🎓 **Example**:

Predicting **house price** based on:

- Square footage
- Number of bedrooms
- Number of bathrooms

The model will learn how much each feature contributes to the price.
### Multivariate Linear Regression

Multivariate Linear Regression is used when you want to predict **more than one output** using **one or more inputs**.
Formula:
$$Y=XB+E$$

Where:

- Y = matrix of outputs (e.g., price, tax, rent)
- X = matrix of input features (e.g., size, age, location)
- B = coefficients
- E = error term
#### 🎓 **Example**:

Predicting:

- House **price**
- Monthly **rent**
- Property **tax**
From:
- Size
- Age
- Location