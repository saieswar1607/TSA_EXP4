# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
### Date:26/03/2024

# AIM:
To implement ARMA model in python.
# ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000 data points using the ArmaProcess class. Plot the generated time series and set the title and x-axis limits.
4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000 data points using the ArmaProcess class. Plot the generated time series and set the title and x-axis limits.
6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using plot_acf and plot_pacf.


# PROGRAM:
```
Developed by: Sai Eswar Kandukuri
Reg No: 212221240020
```
```
from pandas import read_csv
from pandas import datetime
from matplotlib import pyplot
from pandas.plotting import autocorrelation_plot
from pandas import DataFrame
from statsmodels.tsa.arima_model import ARIMA
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
from statsmodels.tsa.arima_process import ArmaProcess
import matplotlib.pyplot as plt
import numpy as np
import warnings
warnings.filterwarnings('ignore')
import matplotlib.pyplot as plt
import numpy as np

plt.rcParams['figure.figsize'] = [10, 7.5]

ar1 = np.array([1,0.33])
ma1 = np.array([1,0.9])
ARMA_1 = ArmaProcess(ar1,ma1).generate_sample(nsample = 1000)
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_1)
plot_pacf(ARMA_1)
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=10000)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
```
# OUTPUT:
# SIMULATED ARMA(1,1) PROCESS:
![1](https://github.com/saieswar1607/TSA_EXP4/assets/93427011/636d5d68-b670-475d-b07e-464294a27094)

# Partial Autocorrelation
![2](https://github.com/saieswar1607/TSA_EXP4/assets/93427011/ad64f1ee-d862-4222-a320-ec96aab2288f)

# Autocorrelation
![3](https://github.com/saieswar1607/TSA_EXP4/assets/93427011/c227d441-9892-4264-ac65-ef98ccd01602)

# SIMULATED ARMA(2,2) PROCESS:
![4](https://github.com/saieswar1607/TSA_EXP4/assets/93427011/8e158ce3-f23c-4f05-9d6d-a2cd4239a613)

# Partial Autocorrelation
![5](https://github.com/saieswar1607/TSA_EXP4/assets/93427011/c9bcdc00-e991-4992-867c-d907d5c597f4)

# Autocorrelation
![6](https://github.com/saieswar1607/TSA_EXP4/assets/93427011/7094be85-f447-4d6d-9952-91ce3ea6aa24)

# RESULT:
Thus, a python program is created to fir ARMA Model successfully.
