# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
## Date: 

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```py
import matplotlib.pyplot as plt

data = [3, 16, 156, 47, 246, 176, 233, 140, 130, 101, 166, 201, 200, 116, 118, 247, 209, 52, 153, 232, 128, 27, 192, 168, 208, 187, 228, 86, 30, 151, 18, 254, 76, 112, 67, 244, 179, 150, 89, 49, 83, 147, 90, 33, 6, 158, 80, 35, 186, 127]


def autocorrelation(series, lag):
    n = len(series)
    mean = sum(series) / n
    
    numerator = sum((series[i] - mean) * (series[i + lag] - mean) for i in range(n - lag))
    denominator = sum((series[i] - mean)**2 for i in range(n))
    
    return numerator / denominator  
lags = 35
acf = [autocorrelation(data, lag) for lag in range(lags + 1)]

plt.figure(figsize=(12, 6))
plt.bar(range(lags + 1), acf)
plt.title('AutoCorrelation Function')
plt.xlabel('Lag')
plt.ylabel('ACF Value')
plt.show()
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/c960d903-255a-476f-8b7b-951c9ed5040a)


### RESULT:
Thus we have successfully implemented the auto correlation function in python.
