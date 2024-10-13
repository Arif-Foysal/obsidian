![[What is Forecasting?]]

## Forecasting Approaches

| Qualitative Methods                                                       | Quantitative Methods                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Used when situation is vague and little data exists.                      | Used when situation is stable and historical data exist                                |
| New products/new technology                                               | Existing products/current technol                                                      |
| **Methods:** Sales force Composite, delphi method, customer market surv **Methods:** Naive approach, moving average, exponential smoothing, Linear regression ng,  |


### Sales force composite
The **sales force composite** is a forecasting method where the sales team provides their estimates of future sales.
- **Person closest to the customer knows best**: Sales representatives, being on the front lines, have firsthand knowledge of customer needs, preferences, and potential buying behavior.
    
- **Combines input from each level**: Forecasts are gathered from various levels of the sales force, starting from individual representatives up through regional managers, and then combined to form an overall projection.
    
- **Sales representatives know customers' wants**: Since salespeople directly interact with customers, they are well-positioned to provide insights into future demand based on those interactions.
    
- **Involvement of different levels**:
    
    - **Retailer**: Sales teams working with retailers understand the direct purchasing patterns of end customers.
    - **Distributor**: Distributors provide feedback on bulk orders and the overall demand they are observing in the supply chain.
    - **Manufacturer**: Manufacturers rely on input from sales teams to plan production and meet future demand.

### Delphi method
The **Delphi method** is a structured forecasting approach that gathers insights and predictions from a panel of experts through multiple rounds of questionnaires.

#### Key features:
- **Iterative group process**: The process involves repeated rounds of feedback, allowing experts to refine their opinions.
- **Moderator-driven**: A moderator designs and distributes questionnaires and manages the feedback process.
- **Summarization and feedback**: After each round, the responses are summarized and new set of questionnaires provided.
#### Step by step procedure

1.Choose the experts to participate. 

2.Through a question set obtain forecasts from the participants. 

3.Summarize the results and redistribute them to the participants along with new set of question. 

4.Summarize again. 5.Repeat step 3 & 4 until consensus is reached


### Naive approach
Assumes demand in next period is similar as demand in most recent period without adjusting them considering any factor.
- e.g., If May sales were 48, then June sales will be …47/**49**

### Moving averages

$$MA=\frac{\text{Demand in previous n periods}}{n}$$

### Weighted Moving Average
![[Pasted image 20241012095105.png]]
**Solution:**

To calculate the forecast for Month 5 using the given weighted average method, we will use the provided weights:
- 40% for the most recent month (Month 4)
- 30% for two months ago (Month 3)
- 20% for three months ago (Month 2)
- 10% for four months ago (Month 1)

The actual sales values are:
- Month 1: 100
- Month 2: 90
- Month 3: 105
- Month 4: 95

The weighted average forecast for Month 5 $$( \text{Forecast}_5) $$ is calculated as follows:

$$
\text{Forecast}_5 = 0.40 \times \text{Sales}_4 + 0.30 \times \text{Sales}_3 + 0.20 \times \text{Sales}_2 + 0.10 \times \text{Sales}_1
$$

Substituting the values:

$$
\text{Forecast}_5 = 0.40 \times 95 + 0.30 \times 105 + 0.20 \times 90 + 0.10 \times 100
$$

Perform the multiplications:

$$
\text{Forecast}_5 = 0.40 \times 95 = 38
$$

$$
\text{Forecast}_5 = 0.30 \times 105 = 31.5
$$

$$
\text{Forecast}_5 = 0.20 \times 90 = 18
$$

$$
\text{Forecast}_5 = 0.10 \times 100 = 10
$$

Add these products together:

$$
\text{Forecast}_5 = 38 + 31.5 + 18 + 10 = 97.5
$$

Thus, the forecast for Month 5 is:

$$
\boxed{97.5}
$$


### Exponential Smoothing
**Exponential Smoothing** is a time series forecasting method that applies **decreasing weights** to past observations, giving more significance to recent data points while still considering older ones. Unlike the **moving average** or **weighted moving average**, where only a fixed number of past observations are used, exponential smoothing includes all past data but assigns exponentially decreasing weights to older data.

**Smoothing Factor (α)**: The weight assigned to the most recent observation is controlled by a smoothing factor (α), which is a number between 0 and 1. A higher value of α gives more weight to recent data and makes the forecast more responsive to changes.

- **α close to 1**: More weight to recent data, meaning the forecast reacts quickly to changes.
- **α close to 0**: More weight to past data, meaning the forecast is smoother and less reactive to short-term fluctuations.


#### Exponential Smoothing Equations
$$F_t = F_{t-1}+\alpha{(A_{t-1}-F_{t-1})}$$
Here, 
Ft = forecast value
At = Actual value, 
a = Smoothing constant
A(t-1) - F(t-1) = Forecast error

#### Example:
![[Pasted image 20241012145426.png]]

**Solution:**

Sure, let's apply the exponential smoothing formula step-by-step from \( F_2 \) all the way to \( F_9 \):

The exponential smoothing formula is:
$$ F_t = F_{t-1} + \alpha (A_{t-1} - F_{t-1}) $$

Given:
- Initial forecast \( F_1 = 175 \)
- Smoothing constant \( \alpha = 0.10 \)


| Quarter | Actual | Forecast                                                        |
| ------- | ------ | --------------------------------------------------------------- |
| 1       | 180    | 175                                                             |
| 2       | 168    | $$ F_2 = 175 + 0.10 (180 - 175) = 175.5$$                       |
| 3       | 159    | $$ F_3 = 175.5 + 0.10 (168 - 175.5) = 174.75$$                  |
| 4       | 175    | $$ F_4 = 174.75 + 0.10 (159 - 174.75) =173.175$$                |
| 5       | 190    | $$ F_5 = 173.175 + 0.10 (175 - 173.175) = 173.3575$$            |
| 6       | 205    | $$ F_6 = 173.3575 + 0.10 (190 - 173.3575) $$                    |
| 7       | 180    | $$ F_7 = 175.02175 + 0.10 (205 - 175.02175) = 178.0195$$        |
| 8       | 182    | $$ F_8 = 178.019575 + 0.10 (180 - 178.019575) = 178.2176175 $$  |
| 9       |        | $$ F_9 = 178.2176175 + 0.10 (182 - 178.2176175)=178.59585575 $$ |


So the forecast for the $$9^{\text{th}}$$ quarter is approximately $$\boxed{178.60}$$
### Linear Regression
#### Least squares equation

**Equation:**
$$\hat{Y}_i = a + bx_i$$
**Slope:**
$$b = \frac{\sum_{i=1}^{n} x_i y_i - n \bar{x} \bar{y}}{\sum_{i=1}^{n} x_i^2 - n (\bar{x})^2}$$
**Y-intercept:**
$$a = \bar{y} - b \bar{x}$$
#### Forecast error equations
**Mean Square Error(MSE)**
$$MSE=\frac{\sum{(A-F)^2}}{M}$$




**Practice problems:**
![[Pasted image 20241012233748.png]]


| Year       | Demand(y) | x      | x^2     | xy       |
| ---------- | --------- | ------ | ------- | -------- |
| 1997       | 74        | 1      | 1       | 74       |
| 1998       | 49        | 2      | 4       | 98       |
| 1999       | 80        | 3      | 9       | 240      |
| 2000       | 90        | 4      | 16      | 360      |
| 2001       | 105       | 5      | 25      | 525      |
| 2002       | 142       | 6      | 36      | 852      |
| 2003       | 122       | 7      | 49      | 854      |
| **Total:** | **692**   | **28** | **140** | **3063** |

So, $$\bar{x}=\frac{\sum{x}}{n} = \frac{28}{7} = 4$$
$$\bar{y} = \frac{\sum{y}}{n} = \frac{692}{7}=98.86$$
That is, 
$$b=\frac{\sum{x}{y}-n\bar{x}\bar{y}}{\sum{x^2}-n\bar{x}^2} =\frac{3063-(7)(4)(98.86)}{140-(7)(16)}$$
$$b=10.532$$
Now we can find Y-intercept:
$$a=\bar{y}-b\bar{x}$$
$$a=98.86-(10.532)(4) = 56.74$$
So, overall trend line:
$$Y=a+bx$$
$$y=56.74+10.532(x)..............(1)$$
Demand in 2004, (plugging x = 8)
$$y=56.74+10.532(8) = 140.98$$
Demand in 2005, (x = 9)
$$y=56.74+10.532(9) = 151.52$$



