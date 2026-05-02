# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
#### Date: 02/05/2026 
### NAME : SANJAY C
### REG NO : 212223240150
### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
# REQUIREMENTS:
```
1.DATASET : APPLE STOCK PRICE
2.TECHNOLOGY USED : GOOGLE COLLAB
```
### ALGORITHM:
```
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
```
### PROGRAM:
```py
import numpy as np
import matplotlib.pyplot as plt

series_for_acf = df_data['Volume'].values

N = len(series_for_acf)
lags = range(35)

mean_val = np.mean(series_for_acf)
var_val = np.var(series_for_acf)

acf_values = []

for lag in lags:
    if lag == 0:
        acf_values.append(1)
    else:

        if lag < N:
            cov = np.sum((series_for_acf[:-lag] - mean_val) * (series_for_acf[lag:] - mean_val)) / N
            acf_values.append(cov / var_val)
        else:
            acf_values.append(0)

plt.figure(figsize=(10, 5))
plt.stem(lags, acf_values)

plt.title("Autocorrelation Function (ACF) of Volume from apple.csv")
plt.xlabel("Lag")
plt.ylabel("Autocorrelation")
plt.grid(True)

plt.show()
```
### OUTPUT:
<img width="1047" height="539" alt="image" src="https://github.com/user-attachments/assets/a8b2872b-121e-459c-a946-d46f04924538" />

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
