**1. What is VIX**   
Definition:    
The VIX Index (CBOE Volatility Index) measures the market's expectation of 30-day implied volatility for the S&P 500 Index. It is calculated from a weighted strip of out-of-the-money (OTM) SPX options.    

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

**Step-by-Step Calculation Process**  
Step 1: Select Expiration Dates
        → Use near-term and next-term SPX options (23-37 days to expiry)

Step 2: Identify OTM Options
        → Puts with strikes below forward price
        → Calls with strikes above forward price

Step 3: Calculate Variance for Each Expiration
        → Apply the 1/K² weighted formula

Step 4: Interpolate to Exactly 30 Days
        → Linear interpolation in VARIANCE (not volatility!)

Step 5: Take Square Root
        → VIX = 100 × √(σ²_30d)
