# TSAF-Ex-4-Compute-ACF-for-the-First-35-Lags

## AIM:
To compute and plot the AutoCorrelation Function (ACF) of a time-series dataset for the
first 35 lags and use the ACF pattern to identify a suitable time-series model.

## PROGRAM:

```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import acf
from statsmodels.graphics.tsaplots import plot_acf

# Step 1: Create time-series data (Sequential Stock Prices)
data = [
 250, 252, 255, 253, 258, 260, 262, 261, 265, 268, 270, 269,
 272, 275, 273, 278, 280, 282, 285, 283, 288, 290, 292, 295,
 294, 298, 300, 302, 305, 303, 308, 310, 312, 315, 314, 318,
 320, 322, 325, 323, 328, 330
]
series = pd.Series(data)

# Step 2: Plot time series
plt.figure(figsize=(10, 4))
plt.plot(series, marker='^', color='purple')
plt.title("Stock Price Trend")
plt.xlabel("Trading Days")
plt.ylabel("Price ($)")
plt.show()

# Step 3: Calculate ACF for first 35 lags
acf_values = acf(series, nlags=35)
# Step 4: Display ACF values
print("ACF Values:")
for lag, value in enumerate(acf_values):
 print("Lag", lag, ":", round(value, 4))

# Step 5: Plot ACF
plt.figure(figsize=(12, 5))
plot_acf(series, lags=35)
plt.title("ACF for First 35 Lags - Stock Prices")
plt.xlabel("Lag")
plt.ylabel("Autocorrelation")
plt.show()

```

## OUTPUT:

<img width="617" height="271" alt="image" src="https://github.com/user-attachments/assets/6addbd8c-f827-4503-beb7-841beeb132a3" />

<img width="557" height="753" alt="image" src="https://github.com/user-attachments/assets/7446c293-1594-4a0a-a4b9-8e14c63e7873" />
