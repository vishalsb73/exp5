# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
plt.figure(figsize=(8, 5))
plt.plot(x, y, label='Data Trend', marker='o', linestyle='-')
plt.xlabel('X-axis Values')
plt.ylabel('Y-axis Values')
plt.title('Simple Line Graph')
plt.legend()
plt.grid(True)
plt.show()
```
<img width="870" height="537" alt="Screenshot 2025-10-16 231541" src="https://github.com/user-attachments/assets/209226c0-3684-4bf3-99b3-29313ce2782f" />

```
x1 = [1,2,3]
y1 = [2,4,1]
x2 = [1,2,3]
y2 = [4,1,3]
plt.figure(figsize=(8, 5))
plt.plot(x1, y1, label = "Line 1", color='blue', linewidth=3, linestyle='dashed', marker='o')
plt.plot(x2, y2, label = "Line 2", color='red', linewidth=2, linestyle='-', marker='s')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Two Lines on the Same Graph')
plt.legend()
plt.grid(True)
```
<img width="866" height="523" alt="Screenshot 2025-10-16 231548" src="https://github.com/user-attachments/assets/60406b6c-81c5-4251-a8c9-79eb14d1a963" />

```
plt.scatter(x1, y1, color='blue', s=80, label='Points Line 1')
plt.scatter(x2, y2, color='red', s=80, label='Points Line 2')
plt.show()
```
<img width="748" height="485" alt="Screenshot 2025-10-16 231553" src="https://github.com/user-attachments/assets/e29d8882-2d71-4beb-91c1-4139fecf4ddb" />

```
x = [1, 2, 3, 4, 5]
y1 = [10, 12, 14, 16, 18]
y2 = [5, 7, 9, 11, 13]
y3 = [2, 4, 6, 8, 10]
x_values = [0,1,2,3,4,5]
y_values = [0,1,4,9,16,25]
plt.figure(figsize=(8, 5))
plt.plot(x_values, y_values, color='darkblue', linewidth=2, label='Y = X^2')
plt.fill_between(x_values, y_values, color='skyblue', alpha=0.5, label='Area Under Curve')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Line Graph with Fill Between (Y = X^2)')
plt.legend()
plt.grid(axis='y', linestyle='--')
plt.show()
```
<img width="863" height="522" alt="Screenshot 2025-10-16 231559" src="https://github.com/user-attachments/assets/7f17b385-0974-45a8-a703-a71bd19f3289" />

```
from scipy.interpolate import make_interp_spline
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y = np.array([2, 4, 5, 7, 8, 8, 9, 10, 11, 12])
X_Y_Spline = make_interp_spline(x, y)
X_ = np.linspace(x.min(), x.max(), 500)
Y_ = X_Y_Spline(X_)

plt.figure(figsize=(8, 5))
plt.plot(x, y, 'o', label='Original Data Points', color='red', markersize=6)
plt.plot(X_, Y_, label='Cubic Spline Interpolation', color='darkgreen', linewidth=2)
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Data Interpolation with Cubic Spline')
plt.legend()
plt.grid(True)
plt.show()
```
<img width="853" height="537" alt="Screenshot 2025-10-16 231604" src="https://github.com/user-attachments/assets/c64fb6a6-6491-4e15-805a-e69babbb9498" />

```
values = [5, 6, 3, 7, 2]
names  = ["A", "B", "C", "D", "E"]
c1 =['red', 'green']
c2 =['b', 'g']
bar_colors = ['red', 'green', 'blue', 'cyan', 'magenta'] 
plt.figure(figsize=(8, 5))
plt.bar(names, values, color=bar_colors, edgecolor='black', linewidth=1)
plt.xlabel('Categories (Names)')
plt.ylabel('Values')
plt.title('Simple Bar Graph')
plt.grid(axis='y', linestyle='--')
plt.show()
```
<img width="852" height="533" alt="Screenshot 2025-10-16 231609" src="https://github.com/user-attachments/assets/c015932c-1386-4a02-a73f-d0f5c9197304" />

```
df = sns.load_dataset("tips")
df.head()
```
<img width="414" height="199" alt="Screenshot 2025-10-16 231908" src="https://github.com/user-attachments/assets/721a2daa-fde0-4a94-baf2-170c2895cf9e" />

```
avg_total_bill = df.groupby('day')['total_bill'].mean()
avg_tip = df.groupby('day')['tip'].mean()

plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', color='skyblue')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip', color='lightcoral')
plt.xlabel('Day of the Week')
plt.ylabel('Average Amount (USD)')
plt.title('Average Total Bill and Tip by Day (Stacked Bar)')
plt.legend()
plt.grid(axis='y', linestyle=':')
plt.show()
```
<img width="887" height="618" alt="Screenshot 2025-10-16 231615" src="https://github.com/user-attachments/assets/1bd1c46e-e754-4dca-990f-ab0947d3841f" />

```
x_values = [0,1,2,3,4,5]
y_values = [0,1,4,9,16,25]
plt.figure(figsize=(8, 5))
plt.scatter(x_values, y_values, color='darkblue', marker='o', s=50)
plt.title('Simple Scatter Plot (Y = X^2)')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.grid(True)
plt.show()
```
<img width="843" height="540" alt="Screenshot 2025-10-16 231621" src="https://github.com/user-attachments/assets/dd438114-22e4-4717-87d4-2f40fa551103" />

```
x = [1,2,3,4,5,6,7,8,9,10]
y = [2,4,5,7,6,8,9,11,12,12]
plt.figure(figsize=(8, 5))
plt.scatter(x, y, label= "stars", color="green", marker="*", s=150)
```
<img width="791" height="535" alt="Screenshot 2025-10-16 231626" src="https://github.com/user-attachments/assets/deb0394d-a63f-49b5-aa85-e6df886d0b54" />

```
plt.xlabel('X Data Points')
plt.ylabel('Y Data Values')
```
<img width="706" height="540" alt="Screenshot 2025-10-16 231632" src="https://github.com/user-attachments/assets/9fc70cb8-99b8-46a8-8f88-ceb129aca969" />

```
plt.title('Scatter Plot with Star Markers')
plt.legend()
plt.grid(True)
plt.show()
```
<img width="710" height="499" alt="Screenshot 2025-10-16 231638" src="https://github.com/user-attachments/assets/8d99de38-4608-41d2-b550-afaaafc437cb" />

```
activities = ['eat', 'sleep', 'work', 'play']
slices = [3, 7, 8, 6]
colors = ['r', 'y', 'g', 'b']
plt.figure(figsize=(7, 7))
explode = (0, 0.1, 0, 0)

plt.pie(
    slices,
    labels=activities,
    colors=colors,
    startangle=90,
    shadow=True,
    explode=explode,
    autopct='%1.1f%%'
)
plt.title('Pie Chart of Daily Activities')
plt.show()
```
<img width="788" height="622" alt="Screenshot 2025-10-16 231650" src="https://github.com/user-attachments/assets/422204d9-4834-4089-a338-cd94a1c7e7a2" />


# Result:
Thus the program to Perform Data Visualization using matplot python library for the given datas is executed successfully.
