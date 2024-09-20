## Developed By: DODDA JAYASRI
## Reg No: 212222240028
## Date: 

# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES

## AIM:
To implement ARMA model in python.

## ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.


## PROGRAM:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

data = pd.read_csv('Salesforcehistory.csv', nrows=200)

# Use the 'Close' price column
close_prices = data['Volume'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)

```


## OUTPUT:
## SIMULATED ARMA(1,1) PROCESS:

![image](https://github.com/user-attachments/assets/0a816d27-efcf-4418-b8d9-44810630f349)


## Partial Autocorrelation

![image](https://github.com/user-attachments/assets/e0963e5d-5873-4d9b-a595-b64bd6124d51)

## Autocorrelation

![image](https://github.com/user-attachments/assets/606fb12a-615a-48dd-bdde-4aa02051e5bd)

## SIMULATED ARMA(2,2) PROCESS:

![image](https://github.com/user-attachments/assets/fca843e1-d8f1-488c-af5b-c682ed0b13f9)

## Partial Autocorrelation

![image](https://github.com/user-attachments/assets/64e227d1-371a-4083-8f25-f5e569889f1a)

## Autocorrelation

![image](https://github.com/user-attachments/assets/c11680cc-7337-403b-96ed-87ac6bf36486)



## RESULT:
Thus, a python program is created to fir ARMA Model successfully.
