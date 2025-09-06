# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA

### Date: 
### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
```python
data=pd.read_csv('/content/international-airline-passengers.csv')
```
```python
x=data['Month']
y=data['International airline passengers: monthly totals in thousands. Jan 49 ? Dec 60']
plt.xlabel('Month')
plt.ylabel('International airline passengers: monthly totals in thousands.')
plt.plot(x,y)
```
```python
data3=data
data3['diff']=data3['International airline passengers: monthly totals in thousands. Jan 49 ? Dec 60'].diff(periods=1)
data3=data3.dropna()
x=data3['Month']
y=data3['diff']
plt.xlabel('Month')
plt.ylabel('International airline passengers: monthly totals in thousands.')
plt.plot(x,y)
```
```python
data2=data
data2['log']=np.log(data2['diff']).dropna()
data2=data2.dropna()
x=data2['Month']
y=data2['log']
plt.xlabel('Month')
plt.ylabel('International airline passengers: monthly totals in thousands.')
# plt.figure(figsize=(8, 6)) 
plt.plot(x,y)
```

### OUTPUT:

## REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/07b5b3b9-84cf-4bab-a724-cdab9659085e)

## SEASONAL ADJUSTMENT:
![image](https://github.com/user-attachments/assets/e859db81-321b-43ab-9507-159b6d951488)

## LOG TRANSFORMATION:
![image](https://github.com/user-attachments/assets/c49e2561-098f-4b1c-973a-d7012a487039)

### RESULT:
Thus, the python code for the conversion of non stationary to stationary data on international airline passenger data is implemented successfully.
