**1. What is VIX**   
Definition:    
The VIX Index (CBOE Volatility Index) measures the market's expectation of 30-day implied volatility for the S&P 500 Index. It is calculated from a weighted strip of out-of-the-money (OTM) SPX options.    
<img width="281" height="55" alt="image" src="https://github.com/user-attachments/assets/3d9cdbf1-2916-4d8c-9b57-ba12dfc8e8c0" />   


Key Characteristics   
(1) Unit  
Annualized implied volatility (percentage points)   
(2) Underlying  
S&P 500 Index (SPX) options  
(3) Horizon  
30-day forward-looking  

Interpreting VIX Levels:  
> VIX = 20 means the market expects SPX to move ±20% over one year (annualized)   

**Converting to Different Time Horizons:**  

![alt text](image.png)  
**Example:**  
VIX = 16  
Expected monthly move: 16/3.46 ≈ 4.6%  
Expected daily move = 16/16 = 1%  

**2. VIX Calculation: The CBOE Methodology**   
Formula:  
<img width="404" height="63" alt="image" src="https://github.com/user-attachments/assets/007819b7-4507-4683-af47-7a68785524da" />  
Where:  
- T = Time to expiration(30 days/ 365)
- $K_i$ = Strike price of the i-th OTM option
- $ΔK_i$ = Interval between strike prices
- $Q(K_i)$ = Midpoint of bid-ask spread for oprion with strike $K_i$
- F = Forward index level
- $K_0$ = First strike below the forward price

**Understanding the Data Structure**  

| Column    | Meaning | Example |
| -------- | ------- |-------|
| Date  | Valuation date   | 2001-06-11|
| Option Expiry | Option expiration date     | Various dates|
| Option Type    | Put/Call    | P or C|
|Strike | Strike Price | 1100,1250, etc |
|Option Price|Market price of option|Varies|
|Forward| Forward Price| 1254.45|
|Discount Rate|Risk-free Rate| Small Value|
|Implied Volatility| Backed-out IV| 0.177|
|Spot|Current Spot Price| 1254.39|   

**OTM option selection**  
Suppose forward = 1254.45  
For strikes < forward: we use OTM Put option.  
For strikes > forward: we use OTM Call option.  

<img width="715" height="115" alt="image" src="https://github.com/user-attachments/assets/0b32d9e1-846c-42be-b4d8-648947991ce9" />

**Why compare strike price with Forward Price?**  
Key reason：options payoff happens in strike date instead of today.  
When we ask, if this option is in the money or out of the money, the real question is :  
> Where will the underlying be relative to the strike at maturity?  



