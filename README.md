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
 # -*- coding: utf-8 -*-
"""EXNO:05 Data visualization Using Matplotlib"""

# Importing required libraries
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy.interpolate import make_interp_spline

# --------------------------------------------------------------------
# **LINE GRAPH**
# --------------------------------------------------------------------

# Basic Line Graph
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

plt.figure(figsize=(6,4))
plt.plot(x, y, label='Line 1', color='blue', marker='o')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Simple Line Graph')
plt.legend()
plt.grid(True)
plt.show()

# Two Lines in Same Graph
x1 = [1, 2, 3]
y1 = [2, 4, 1]
x2 = [1, 2, 3]
y2 = [4, 1, 3]

plt.figure(figsize=(6,4))
plt.plot(x1, y1, label='Line 1', color='red', marker='o')
plt.plot(x2, y2, label='Line 2', color='green', marker='x')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Two Line Graphs')
plt.legend()
plt.grid(True)
plt.show()

# --------------------------------------------------------------------
# **FILL BETWEEN (Area Graph)**
# --------------------------------------------------------------------
x_values = [0,1,2,3,4,5]
y_values = [0,1,4,9,16,25]

plt.figure(figsize=(6,4))
plt.plot(x_values, y_values, color='blue', label='x^2')
plt.fill_between(x_values, y_values, color='skyblue', alpha=0.4)
plt.xlabel("X values")
plt.ylabel("Y values")
plt.title("Line Graph with Fill Between")
plt.legend()
plt.show()

# --------------------------------------------------------------------
# **CUBIC SPLINE INTERPOLATION**
# --------------------------------------------------------------------
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y = np.array([2, 4, 5, 7, 8, 8, 9, 10, 11, 12])

# Smooth line using cubic spline
X_Y_Spline = make_interp_spline(x, y)
X_ = np.linspace(x.min(), x.max(), 500)
Y_ = X_Y_Spline(X_)

plt.figure(figsize=(6,4))
plt.plot(X_, Y_, color='purple', label="Cubic Spline Curve")
plt.scatter(x, y, color='orange', label="Data Points")
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Cubic Spline Interpolation')
plt.legend()
plt.show()

# --------------------------------------------------------------------
# **BAR GRAPH**
# --------------------------------------------------------------------
values = [5, 6, 3, 7, 2]
names  = ["A", "B", "C", "D", "E"]

plt.figure(figsize=(6,4))
plt.bar(names, values, color='teal')
plt.xlabel('Categories')
plt.ylabel('Values')
plt.title('Simple Bar Graph')
plt.show()

# Stacked Bar Graph using seaborn tips dataset
df = sns.load_dataset("tips")

avg_total_bill = df.groupby('day')['total_bill'].mean()
avg_tip = df.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
plt.show()

# --------------------------------------------------------------------
# **SCATTER PLOT**
# --------------------------------------------------------------------
x_values = [0,1,2,3,4,5]
y_values = [0,1,4,9,16,25]

plt.figure(figsize=(6,4))
plt.scatter(x_values, y_values, color='blue', label='x vs y')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Basic Scatter Plot')
plt.legend()
plt.show()

# Custom Scatter Plot with parameters
x = [1,2,3,4,5,6,7,8,9,10]
y = [2,4,5,7,6,8,9,11,12,12]

plt.figure(figsize=(6,4))
plt.scatter(x, y, label="stars", color="green", marker="*", s=80)
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('Scatter Plot with Custom Markers')
plt.legend()
plt.grid(True)
plt.show()

# --------------------------------------------------------------------
# **PIE CHART**
# --------------------------------------------------------------------
activities = ['eat', 'sleep', 'work', 'play']
slices = [3, 7, 8, 6]
colors = ['r', 'y', 'g', 'b']

plt.figure(figsize=(6,6))
plt.pie(slices, labels=activities, colors=colors, startangle=90, shadow=True, autopct='%1.1f%%')
plt.title('Pie Chart Representation of Daily Activities')
plt.show()


# Result:
 ![alt text](<Screenshot 2025-10-08 160229.png>)
 ![alt text](<Screenshot 2025-10-08 161036.png>)
 ![alt text](<WhatsApp Image 2025-10-08 at 16.24.45_1f645f6b.jpg>)
 ![alt text](<WhatsApp Image 2025-10-08 at 16.24.45_4cb04394.jpg>)
 ![alt text](<WhatsApp Image 2025-10-08 at 16.24.45_6593d4f2.jpg>)