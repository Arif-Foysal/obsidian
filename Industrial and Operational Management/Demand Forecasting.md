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


