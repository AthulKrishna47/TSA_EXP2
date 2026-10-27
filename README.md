# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
Date: 27/10/2026
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### PROGRAM:
A - LINEAR TREND ESTIMATION
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

df = pd.read_csv('Electric_Production.csv')
df.columns = ['Date', 'Production']
df['Date'] = pd.to_datetime(df['Date'])
df = df.sort_values('Date').reset_index(drop=True)

x = np.arange(len(df))
y = df['Production'].values

linear_coeffs = np.polyfit(x, y, 1)
linear_trend = np.polyval(linear_coeffs, x)

print(f"Linear Equation: y = {linear_coeffs[0]:.4f}x + {linear_coeffs[1]:.4f}")

plt.figure(figsize=(10, 5))
plt.plot(df['Date'], y, color='gray', alpha=0.6, label='Actual Data')
plt.plot(df['Date'], linear_trend, color='blue', linewidth=2, label='Linear Trend')
plt.title('Linear Trend Estimation')
plt.xlabel('Date')
plt.ylabel('Production')
plt.legend()
plt.grid(True, linestyle=':', alpha=0.6)
plt.show()
```
B- POLYNOMIAL TREND ESTIMATION
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

df = pd.read_csv('Electric_Production.csv')
df.columns = ['Date', 'Production']
df['Date'] = pd.to_datetime(df['Date'])
df = df.sort_values('Date').reset_index(drop=True)

x = np.arange(len(df))
y = df['Production'].values

poly_coeffs = np.polyfit(x, y, 2)
poly_trend = np.polyval(poly_coeffs, x)

print(f"Polynomial Equation: y = {poly_coeffs[0]:.6f}x² + {poly_coeffs[1]:.4f}x + {poly_coeffs[2]:.4f}")

plt.figure(figsize=(10, 5))
plt.plot(df['Date'], y, color='gray', alpha=0.6, label='Actual Data')
plt.plot(df['Date'], poly_trend, color='red', linewidth=2, label='Polynomial Trend (Degree 2)')
plt.title('Polynomial Trend Estimation')
plt.xlabel('Date')
plt.ylabel('Production')
plt.legend()
plt.grid(True, linestyle=':', alpha=0.6)
plt.show()
```
### OUTPUT
A - LINEAR TREND ESTIMATION
<img width="1061" height="610" alt="image" src="https://github.com/user-attachments/assets/231db689-2cb7-4ae4-8352-ddbda2eaf948" />

B- POLYNOMIAL TREND ESTIMATION
<img width="1063" height="602" alt="image" src="https://github.com/user-attachments/assets/a870295f-13e7-4bd6-9758-cbe97ffaf340" />

### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
