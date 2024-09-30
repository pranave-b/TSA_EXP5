# NAME: Pranave B
# REG NO: 212221240040
# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the dataset
df = pd.read_csv('WMT.csv')

# Convert 'Date' to datetime format and set as index
df['Date'] = pd.to_datetime(df['Date'])
df.set_index('Date', inplace=True)

# Use 'Adj Close' for time series analysis
adj_close_series = df['Adj Close']

# Perform time series decomposition
# Assuming daily data, use a yearly period for decomposition (365 days)
decomposition = seasonal_decompose(adj_close_series, model='additive', period=365)

# Extract the components
trend = decomposition.trend
seasonal = decomposition.seasonal
residual = decomposition.resid

# Plot the original time series and its decomposition
plt.figure(figsize=(12, 10))

# Original time series
plt.subplot(4, 1, 1)
plt.plot(adj_close_series, label='Original', color='b')
plt.legend(loc='upper left')
plt.title('Original Time Series')

# Trend component
plt.subplot(4, 1, 2)
plt.plot(trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Component')

# Seasonal component
plt.subplot(4, 1, 3)
plt.plot(seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonal Component')

# Residual component
plt.subplot(4, 1, 4)
plt.plot(residual, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Component')

plt.tight_layout()
plt.show()
```

### OUTPUT:
# Original Time Series
![image](https://github.com/user-attachments/assets/db7c49d4-8df9-449a-b72a-5665dbd0180a)
# Trend Component
![image](https://github.com/user-attachments/assets/69e32470-2ece-4f85-8359-a54d6817458a)
# Seasonal Component
![image](https://github.com/user-attachments/assets/b354e4a4-aa12-443a-80d8-dfbb264bfa9d)
# Residual Component
![image](https://github.com/user-attachments/assets/d8244af5-432d-42b6-9a91-dd33bb1a897a)




### RESULT:
Thus, the python code for the time series analysis and decomposition.
