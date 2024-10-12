<div class="container">
<div class="cover">
<h1>
Industrial and Operational Management
</h1>
<h2>
Assignment 02
</h2>
<p>
Name: MD. Arif Faysal Nayem
<p>ID: 011201194</p>
<p>Course: IPE401</p>
Section: A
</div>
</div>

### 1.

Given:
- The effective annual rate when compounded weekly is ( 19.47% ).

The formula for the effective annual rate ( r ) when compounded ( n ) times per year is: $$ r = \left(1 + \frac{i}{n}\right)^n - 1 $$ where ( i ) is the nominal annual interest rate. For weekly compounding (( n = 52 )): $$ 0.1947 = \left(1 + \frac{i}{52}\right)^{52} - 1 $$ Let's solve for ( i ): 
$$1.1947 = \left(1 + \frac{i}{52}\right)^{52}$$ Taking the natural logarithm on both sides: 
$$\ln(1.1947) = 52 \ln\left(1 + \frac{i}{52}\right)$$ $$\frac{\ln(1.1947)}{52} = \ln\left(1 + \frac{i}{52}\right)$$ $$1 + \frac{i}{52} = e^{\frac{\ln(1.1947)}{52}}$$ $$\frac{i}{52} = e^{\frac{\ln(1.1947)}{52}} - 1$$
$$i = 52 \left(e^{\frac{\ln(1.1947)}{52}} - 1\right)$$
$$i=0.17812$$
Now, we need to convert this nominal annual rate ( i ) to the effective annual rate when compounded quarterly (( n = 4 )): $$r_{\text{quarterly}} = \left(1 + \frac{i}{4}\right)^4 - 1$$
$$r_{\text{quarterly}}=0.044$$
**Future value:**
Given:
- Future value ( FV = $65,123 )
- Time ( t = 6 ) years
- Compounded quarterly
The formula for the future value is: $$FV = PV \left(1 + \frac{r_{\text{quarterly}}}{4}\right)^{4t}$$
Rearranging to solve for the present value ( PV ): $$PV = \frac{FV}{\left(1 + \frac{r_{\text{quarterly}}}{4}\right)^{4t}}$$
$$PV=50084.88$$

**Determine the Time to Reach $1,000,000:**

Now, we need to find out how long it will take for Ayaka to reach `$1,000,000` with the same initial investment ( PV ). The formula for the future value is:
$$FV=PV \left(1 + \frac{r_{\text{quarterly}}}{4}\right)^{4t}$$ ( t ) when ( FV = $1,000,000 ): 
$$1,000,000 = PV \left(1 + \frac{r_{\text{quarterly}}}{4}\right)^{4t}$$
$$\left(1 + \frac{r_{\text{quarterly}}}{4}\right)^{4t} = \frac{1,000,000}{PV}$$ Taking the natural logarithm on both sides: 
$$4t \ln\left(1 + \frac{r_{\text{quarterly}}}{4}\right) = \ln\left(\frac{1,000,000}{PV}\right)$$ $$t = \frac{\ln\left(\frac{1,000,000}{PV}\right)}{4 \ln\left(1 + \frac{r_{\text{quarterly}}}{4}\right)}$$
$$t= 68.419 years$$
### 2. 
Given data:
- Usage of raw material “Carbon”: 3900 bags for 13 days
- Factory open: 252 days
- Order cost: $30 per order
- Holding cost: 60%
- Discount schedule available

**Calculate the Annual Demand**:

Per day usage =
$$\frac{3900 \text{ bags}}{13 \text{ days}} = 300 \text{ bags/day}$$
So, annual usage:
$$300 \text{ bags/day} \times 252 \text{ days} = 75,600 \text{ bags/year}$$
**Calculate the discount prices**:

- No discount: $30 per bag.

 16% discount:
$$\text{Discount price} = \$30 \times (1 - 0.16) = \$30 \times 0.84 = \$25.20$$
 19% discount:
$$\text{Discount price} = \$30 \times (1 - 0.19) = \$30 \times 0.81 = \$24.30$$
**Calculate the Economic Order Quantity (EOQ) for each price tier**:
$$EOQ = \sqrt{\frac{2 \times D \times S}{H}}$$

where,

D  is the annual demand (75,600 bags).
S  is the order cost ($30).
H  is the holding cost, calculated as 60% of the unit price.

For no discount (price = $30):
$$EOQ_1 = \sqrt{\frac{2 \times 75600 \times 30}{18}} = \sqrt{\frac{4536000}{18}} = \sqrt{252000} \approx 502$$
For 16% discount (price = $25.20):
$$H = 0.60 \times 25.20 = \$15.12$$
$$EOQ_2 = \sqrt{\frac{2 \times 75600 \times 30}{15.12}} = \sqrt{\frac{4536000}{15.12}} = \sqrt{299206.35} \approx 547$$

For 19% discount (price = $24.30):
$$H = 0.60 \times 24.30 = \$14.58$$
$$EOQ_3 = \sqrt{\frac{2 \times 75600 \times 30}{14.58}} = \sqrt{\frac{4536000}{14.58}} = \sqrt{311144.58} \approx 558$$

**Determining the total cost for each order quantity**:

Total Cost (TC) formula:
$$TC = \left(\frac{D}{Q}\right)S + \left(\frac{Q}{2}\right)H + PD$$
where  is the price per unit.

- For no discount:
$$C_1 = \frac{75,600}{502} \times 30 + \frac{502}{2} \times 18 + 30 \times 75,600$$
$$= 4515.74 \times 30 + 251 \times 18 + 2,268,000$$\
$$= 135472.23 + 4518 + 2,268,000 \approx 2,407,990.23$$
- For 16% discount:
$$C_2 = \frac{75,600}{547} \times 30 + \frac{547}{2} \times 15.12 + 25.20 \times 75,600$$
$$= 138.2 \times 30 + 273.5 \times 15.12 + 1,904,112$$
$$= 4146 + 4133.64 + 1,904,112 \approx 1,912,391.64$$
- For 19% discount:
$$C_3 = \frac{75,600}{558} \times 30 + \frac{558}{2} \times 14.58 + 24.30 \times 75,600$$
$$= 135.47 \times 30 + 279 \times 14.58 + 1,838,280$$
$$= 4064.1 + 4068.62 + 1,838,280 \approx 1,846,412.72$$
**Determine the Optimal Order Quantity:**
Comparing costs:
$$\begin{aligned}
C_1 &\approx 2,404,888.23 \\
C_2 &\approx 1,912,391.64 \\
C_3 &\approx 1,846,412.72 \\
\end{aligned}$$
The lowest total cost is with the 19% discount (price = $24.30) at EOQ of 558.

**Optimal Order Quantity: 558 packages**

**Total Cost associated with the optimal order quantity: $1,843,770.36**

So, the optimal order quantity is 558 packages, with the associated total cost being approximately $1,846,412.72.

### 3.

### Calculating the Internal Rate of Return (IRR):

To solve this problem using the IRR method, we need to find the discount rate that will set the Net Present Value (NPV) of each project to zero. 

Given:
- Project R: Initial Investment = -\$15,754
- Project L: Initial Investment = -\$10,785

The IRR is the rate \(r\) that solves the NPV equation:

$$
0 = \sum_{t=0}^{n} \frac{\text{Cash Flow}_t}{(1 + r)^t}
$$

### For Project R:

We need to solve for \(r\) in the following equation:

$$
-15754 + \frac{3042}{(1 + r)^1} + \frac{8975}{(1 + r)^2} + \frac{9516}{(1 + r)^3} + \frac{7538}{(1 + r)^4} + \frac{8680}{(1 + r)^5} = 0
$$

Using the trial and error method (or more commonly using a financial calculator or Excel), we approximate the IRR. Here are some key calculations:

Guess \(r = 10\%\):


$$\begin{align*}
NPV &= -15754 + \frac{3042}{(1 + 0.10)^1} + \frac{8975}{(1 + 0.10)^2} + \frac{9516}{(1 + 0.10)^3} + \frac{7538}{(1 + 0.10)^4} + \frac{8680}{(1 + 0.10)^5} \\
&= -15754 + 2765.45 + 7436.36 + 7141.53 + 5151.25 + 5398.89 \\
&= 14388.48 (\text{NPV is positive, so we increase the discount rate})
\end{align*}
$$

Guess \(r = 15\%\):

$$
\begin{align*}
NPV &= -15754 + \frac{3042}{(1 + 0.15)^1} + \frac{8975}{(1 + 0.15)^2} + \frac{9516}{(1 + 0.15)^3} + \frac{7538}{(1 + 0.15)^4} + \frac{8680}{(1 + 0.15)^5} \\
&= -15754 + 2643.48 + 6784 + 6255.6 + 4074.9 + 4314.76 \\
&= 0 (\text{Approximately})
\end{align*}
$$

So the IRR for Project R is approximately 15%.

### For Project L:

We need to solve for \(r\) in the following equation:

$$
-10785 + \frac{10781}{(1 + r)^1} + \frac{9937}{(1 + r)^2} + \frac{4566}{(1 + r)^3} + \frac{9512}{(1 + r)^4} + \frac{6840}{(1 + r)^5} = 0
$$

Again, using trial and error:

Guess \(r = 20\%\):

$$
\begin{align*}
NPV &= -10785 + \frac{10781}{(1 + 0.20)^1} + \frac{9937}{(1 + 0.20)^2} + \frac{4566}{(1 + 0.20)^3} + \frac{9512}{(1 + 0.20)^4} + \frac{6840}{(1 + 0.20)^5} \\
&= -10785 + 8984.17 + 6900.69 + 2637.84 + 4582.63 + 2748.44 \\
&= 4471.77 (\text{NPV is positive, so we increase the discount rate})
\end{align*}
$$

Guess \(r = 25\%\):

$$
\begin{align*}
NPV &= -10785 + \frac{10781}{(1 + 0.25)^1} + \frac{9937}{(1 + 0.25)^2} + \frac{4566}{(1 + 0.25)^3} + \frac{9512}{(1 + 0.25)^4} + \frac{6840}{(1 + 0.25)^5} \\
&= -10785 + 8624.80 + 6509.83 + 2351.81 + 3896.23 + 2233.26 \\
&= 3830.94 (\text{NPV is positive, so we increase the discount rate})
\end{align*}
$$

Guess \(r = 30\%\):

$$
\begin{align*}
NPV &= -10785 + \frac{10781}{(1 + 0.30)^1} + \frac{9937}{(1 + 0.30)^2} + \frac{4566}{(1 + 0.30)^3} + \frac{9512}{(1 + 0.30)^4} + \frac{6840}{(1 + 0.30)^5} \\
&= -10785 + 8291.54 + 6200.91 + 2152 + 3297.15 + 1834.52 \\
&= 4090.12 (\text{NPV is still positive, we keep raising the discount rate})
\end{align*}
$$

Guess \(r = 33\%\):

$$
\begin{align*}
NPV &= -10785 + \frac{10781}{(1 + 0.33)^1} + \frac{9937}{(1 + 0.33)^2} + \frac{4566}{(1 + 0.33)^3} + \frac{9512}{(1 + 0.33)^4} + \frac{6840}{(1 + 0.33)^5} \\
&= -10785 + 8108.50 + 5984.53 + 2009.38 + 2968.89 + 1583.53 \\
&= 2850.83 (\text{NPV is still positive, this needs more adjustment})
\end{align*}
$$

Guess \(r = 37\%\):

$$
\begin{align*}
NPV &= -10785 + \frac{10781}{(1 + 0.37)^1} + \frac{9937}{(1 + 0.37)^2} + \frac{4566}{(1 + 0.37)^3} + \frac{9512}{(1 + 0.37)^4} + \frac{6840}{(1 + 0.37)^5} \\
&= -10785 + 7867 + 5755.97 + 1862 + 2590 + 1356\\
&= -6423 \\
\end{align*}
$$

Guess \(r = 30\%\):

$$
\begin{align*}
NPV &= -10785 + \frac{10781}{(1 + 0.33)^1} + \frac{9937}{(1 + 0.33)^2} + \frac{4566}{(1 + 0.33)^3} + \frac{9512}{(1 + 0.33)^4} + \frac{6840}{(1 + 0.33)^5} \\
&= -10785 + 8608 + 6205 + 2009 + 2978 + 1583\\
&= 205900\\
Better project is R.
\end{align*}
$$
Comparitive projects:
Therefore, the IRR for Project R is approximately10%, whereas for Project L around (30%. Based on the IRR method.
To determine the better project using the IRR method with a WACC of 13% compounded daily, we need to compare the IRRs of both projects and check how they stand relative to the WACC.

### Calculating the IRR for Each Project

The IRR of a project is the discount rate that makes the NPV of the project's cash flows equal to zero. This will involve solving the NPV equation for each project to find the discount rate \(r\) that makes NPV = 0.

#### Project R

Given cash flows:
- Initial Investment: -\$15,754
- Cash Inflows: \$3,042 in Year 1, \$8,975 in Year 2, \$9,516 in Year 3, \$7,538 in Year 4, \$8,680 in Year 5

$$
0 = -15754 + \frac{3042}{(1 + r)^1} + \frac{8975}{(1 + r)^2} + \frac{9516}{(1 + r)^3} + \frac{7538}{(1 + r)^4} + \frac{8680}{(1 + r)^5}
$$

Using trial and error or a financial calculator:

- Assume \( r = 15\% \):

$$
NPV = -15754 + \frac{3042}{(1 + 0.15)^1} + \frac{8975}{(1 + 0.15)^2} + \frac{9516}{(1 + 0.15)^3} + \frac{7538}{(1 + 0.15)^4} + \frac{8680}{(1 + 0.15)^5} = 100.36 
$$

 Since the result is positive, we try a higher rate.

- Assume \( r = 16\% \):

$$
NPV = -15754 + \frac{3042}{(1 + 0.16)^1} + \frac{8975}{(1 + 0.16)^2} + \frac{9516}{(1 + 0.16)^3} + \frac{7538}{(1 + 0.16)^4} + \frac{8680}{(1 + 0.16)^5} = -102.98 
$$

Since the NPV is negative, the IRR is between 15 and 16%.

Using interpolation or a financial calculator, we find that:
$$ \text{IRR for Project R} \approx 15.49\% $$

#### Project L

Given cash flows:
- Initial Investment: -\$10,785
- Cash Inflows: \$10,781 in Year 1, \$9,937 in Year 2, \$4,566 in Year 3, \$9,512 in Year 4, \$6,840 in Year 5

$$
0 = -10785 + \frac{10781}{(1 + r)^1} + \frac{9937}{(1 + r)^2} + \frac{4566}{(1 + r)^3} + \frac{9512}{(1 + r)^4} + \frac{6840}{(1 + r)^5}
$$

Using trial and error or a financial calculator:

- Assume \( r = 29\% \):

$$
NPV = -10785 + \frac{10781}{(1 + 0.29)^1} + \frac{9937}{(1 + 0.29)^2} + \frac{4566}{(1 + 0.29)^3} + \frac{9512}{(1 + 0.29)^4} + \frac{6840}{(1 + 0.29)^5} = 144.36
$$

 Since the result is positive, we try a higher rate.

- Assume \( r = 30\% \):

$$
NPV = -10785 + \frac{10781}{(1 + 0.30)^1} + \frac{9937}{(1 + 0.30)^2} + \frac{4566}{(1 + 0.30)^3} + \frac{9512}{(1 + 0.30)^4} + \frac{6840}{(1 + 0.30)^5} = -87.23 
$$

 Since the result is nearing around 0 and is not negative.

Using interpolation or a financial calculator, we find that:
$$ \text{IRR for Project L} \approx 29.76\% $$

We have the following results:
- IRR for Project R: 15.49%
- IRR for Project L: 29.76%

Both projects have IRRs higher than the WACC of 13%, so they are both acceptable.

However, if choosing between the two, Project L is the better project in terms of IRR, given \(29.76% > 15.49%\).

Thus, according to the IRR method, we select Project L.


### 4
To select the project using the Discounted Payback Period (DPP) method, we need to discount the cash flows of each project to the present value using the given hurdle rate of 21.5% compounded quarterly and see if the payback period falls within 4.5 years. If it does, we compare the discounted payback periods of the projects and choose the one with the shorter period.

### Given:
- Hurdle rate: 21.5% compounded quarterly
- Desired payback period: within 4.5 years

### Discount Rate Calculation
First, we convert the annual rate to the quarterly rate:
$$ q = \frac{21.5\%}{4} = 5.375\% $$

Since the compounding is quarterly, we use the following quarter-to-year conversion factor:
$$ (1 + q)^4 - 1 = (1 + 0.05375)^4 - 1 \approx 23.01\% $$

### Discount Factors 
We'll be using the following formula for the present value of each annual cash flow:
$$ DF = \dfrac{1}{(1 + i)^t} $$
where \( i \) is the effective annual rate (23.01%). We convert back the hurdle rate to the effective annual rate because those cash flows are yearly.
$$
i = 23.01\% = 0.2301
$$

### Project Fire
Calculate the discounted cash flows and cumulative cash flows until the initial investment is recovered (i.e., until the sum equals zero or becomes positive).

$$ \text{Year 0: } -38070  $$
$$\text{Year 1: } \frac{6781}{(1 + 0.2301)^1} = 6781 \times 0.8123 = 5507.8 $$
$$ \text{Year 2: } \frac{17752}{(1 + 0.2301)^2} = 17752 \times 0.6606 = 11728.8 $$
$$ \text{Year 3: } \frac{14223}{(1 + 0.2301)^3} = 14223 \times 0.5367 = 7630.2 $$
$$ \text{Year 4: } \frac{16467}{(1 + 0.2301)^4} = 16467 \times 0.4364 = 7187.5 $$
$$ \text{Year 5: } \frac{23470}{(1 + 0.2301)^5} = 23470 \times 0.3547 = 8325.5 $$

Cumulative:
$$
0: -38070 \\
1: -38070 + 5507.8 = -32562.2 \\
2: -32562.2 + 11728.8 = -20833.4\\
3: -20833.4 + 7630.2 = -13203.2\\
4: -13203.2+ 7187.5 = -6015.7 \\
5: -6015.7 + 8325.5 = +2309.3\ (\text{Payback occurs in Year 5})
$$

$$
\text{Project Fire DPP} = 5 \text{ years}
$$

### Project Earth
Calculate the discounted cash flows and cumulative cash flows until the initial investment is recovered.

$$ \text{Year 0: } -38121  $$
$$\text{Year 1: } \frac{23324}{(1 + 0.2301)^1} = 23324 \times 0.8123 = 18952.09 $$
$$ \text{Year 2: } \frac{9987}{(1 + 0.2301)^2} = 9987 \times 0.6606 = 6600.5 $$
$$\text{Year 3: } \frac{18364}{(1 + 0.2301)^3} = 18364 \times 0.5367 = 9852.1 $$
$$\text{Year 4: } \frac{4800}{(1 + 0.2301)^4} = 4800 \times 0.4364 = 2094.7 $$
$$ \text{Year 5: } \frac{5319}{(1 + 0.2301)^5} = 5319 \times 0.3547 = 1885.5 $$

Cumulative:
$$0: -38121 \\
1: -38121 + 18952.09 = -19168.91 \\
2: -19168.91 + 6600.5 = -11768.41\\
3: -11768.41 + 9852.1 = -1916.31 \\
4: -1916.31+ 2094.7 = +91.18\\
5: +91.18 + 1885.5 = +979.5\ (\text{Payback occurs in Year 4})$$

$$
\text{Project Earth DPP} = 4 \text{ years}
$$

### Conclusion
Considering a hurdle rate of 21.5% compounded quarterly and the requirement for a payback period within 4.5 years, Project Earth (with a payback period of 4 years) should be selected over Project Fire (with a payback period of 5 years).

### 5.

To select the project using the Net Present Value (NPV) method, we need to determine the NPV for each project at a MARR of 14% compounded quarterly.

### Conversion of Compound Rate
First, we convert the 14% compounded quarterly rate to the annual effective rate.

Quarterly rate, $$ q = \frac{14\%}{4} = 3.5\% $$

The annual effective interest rate \( i \):
$$ (1 + q)^4 - 1 = (1 + 0.035)^4 - 1 \approx 0.1465 \text{ or } 14.65\% $$

### Calculation of NPV
NPV is calculated using the formula:
$$
NPV = \sum_{t=0}^{n} \frac{\text{Benefit}_t - \text{Cost}_t}{(1 + i)^t}
$$

where \( i = 14.65\% \)

Discount factor for year \( t \):
$$ DF = \frac{1}{(1 + 0.1465)^t} $$

### Project N Calculation

#### Benefit Calculation:
$$
\begin{aligned}
\text{Year 0: } & 500 \\
\text{Year 1: } & \frac{17000}{(1 + 0.1465)^1} = 17000 \times 0.8727 = 14835.9 \\
\text{Year 2: } & \frac{12001}{(1 + 0.1465)^2} = 12001 \times 0.7615 = 9122.9 \\
\text{Year 3: } & \frac{17509}{(1 + 0.1465)^3} = 17509 \times 0.6644 = 11633.2 \\
\text{Year 4: } & \frac{9000}{(1 + 0.1465)^4} = 9000 \times 0.5794 = 5214.6 \\
\text{Year 5: } & \frac{751}{(1 + 0.1465)^5} = 751 \times 0.5054 = 379.4 \\
\end{aligned}
$$

Total Benefits for Project N:
$$ 500 + 14835.9 + 9122.9 + 11633.2 + 5214.6 + 379.4 = 41246 $$

#### Cost Calculation:
$$
\begin{aligned}
\text{Year 0: } & 15000 \\
\text{Year 1: } & \frac{5000}{(1 + 0.1465)^1} = 5000 \times 0.8727 = 4363.5 \\
\text{Year 2: } & \frac{4500}{(1 + 0.1465)^2} = 4500 \times 0.7615 = 3426.8 \\
\text{Year 3: } & \frac{8900}{(1 + 0.1465)^3} = 8900 \times 0.6644 = 5915 \\
\text{Year 4: } & \frac{16000}{(1 + 0.1465)^4} = 16000 \times 0.5794 = 9270.4 \\
\text{Year 5: } & \frac{1700}{(1 + 0.1465)^5} = 1700 \times 0.5054 = 859.2 \\
\end{aligned}
$$

Total Costs for Project N:
$$ 15000 + 4363.5 + 3426.8 + 5915 + 9270.4 + 859.2 = 38834.9 $$

NPV for Project N:
$$ \text{NPV}_N = \text{Total Benefits} - \text{Total Costs} = 41246 - 38834.9 = 2411.1 $$

### Project M Calculation

#### Benefit Calculation:
$$
\begin{aligned}
\text{Year 0: } & 0 \\
\text{Year 1: } & \frac{13312}{(1 + 0.1465)^1} = 13312 \times 0.8727 = 11616.4 \\
\text{Year 2: } & \frac{17212}{(1 + 0.1465)^2} = 17212 \times 0.7615 = 13117.2 \\
\text{Year 3: } & \frac{11258}{(1 + 0.1465)^3} = 11258 \times 0.6644 = 7481.3 \\
\text{Year 4: } & \frac{4689}{(1 + 0.1465)^4} = 4689 \times 0.5794 = 2715.6 \\
\text{Year 5: } & \frac{598}{(1 + 0.1465)^5} = 598 \times 0.5054 = 302.1 \\
\end{aligned}
$$

Total Benefits for Project M:
$$ 0 + 11616.4 + 13117.2 + 7481.3 + 2715.6 + 302.1 = 35232.6 $$

#### Cost Calculation:
$$
\begin{aligned}
\text{Year 0: } & 10000 \\
\text{Year 1: } & \frac{4980}{(1 + 0.1465)^1} = 4980 \times 0.8727 = 4346.9 \\
\text{Year 2: } & \frac{6780}{(1 + 0.1465)^2} = 6780 \times 0.7615 = 5164.1 \\
\text{Year 3: } & \frac{9870}{(1 + 0.1465)^3} = 9870 \times 0.6644 = 6558.7 \\
\text{Year 4: } & \frac{4320}{(1 + 0.1465)^4} = 4320 \times 0.5794 = 2503 \\
\text{Year 5: } & \frac{451}{(1 + 0.1465)^5} = 451 \times 0.5054 = 227.8 \\
\end{aligned}
$$

Total Costs for Project M:
$$ 10000 + 4346.9 + 5164.1 + 6558.7 + 2503 + 227.8 = 28800.5 $$

NPV for Project M:
$$ \text{NPV}_M = \text{Total Benefits} - \text{Total Costs} = 35232.6 - 28800.5 = 6432.1 $$

### Conclusion

By comparing the NPVs of both projects:
- NPV for Project N: \$2411.1
- NPV for Project M: \$6432.1

Since Project M has a higher NPV, Project M should be selected.