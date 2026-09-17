import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression

# ✅ Step 1: Load the Excel file (corrected path and filename)
file_path = r"C:\Users\Saiqa\OneDrive - Kadir Has University\MS_Study\Semesters\Sem 3\Thesis\2024-10\10m_RodtoPlane_250us_Data\N_10mRP_22\ResultData_converted.csv"
df = pd.read_csv(file_path)

# ✅ Step 2: Check column names & preview data
print(df.head())
print(df.columns)

# ✅ Step 3: Select relevant columns (ensure correct column names)
df = df[['t', 'V', 'i']]  # 't' = time, 'V' = voltage, 'i' = current

# ✅ Step 4: Polynomial regression on Voltage (degree 3)
poly_v = PolynomialFeatures(degree=3)
X_poly_v = poly_v.fit_transform(df[['t']])
model_v = LinearRegression().fit(X_poly_v, df['V'])
df['V_pred'] = model_v.predict(X_poly_v)

# ✅ Step 5: Polynomial regression on Current (degree 3)
poly_i = PolynomialFeatures(degree=3)
X_poly_i = poly_i.fit_transform(df[['t']])
model_i = LinearRegression().fit(X_poly_i, df['i'])
df['i_pred'] = model_i.predict(X_poly_i)

# ✅ Step 6: Optional downsampling for plotting efficiency
df_sampled = df.iloc[::10]

# ✅ Step 7: Plot Voltage and Current vs Time
fig, ax1 = plt.subplots(figsize=(12, 6))

# Voltage plot (left axis)
ax1.scatter(df_sampled['t'], df_sampled['V'], s=5, alpha=0.4, color='blue', label="Voltage Raw")
ax1.plot(df['t'], df['V_pred'], color='red', linewidth=2, label="Voltage Fit")
ax1.set_xlabel("Time (µs)")
ax1.set_ylabel("Voltage (V)", color='blue')
ax1.tick_params(axis='y', labelcolor='blue')
ax1.legend(loc='upper left')

# Current plot (right axis)
ax2 = ax1.twinx()
ax2.scatter(df_sampled['t'], df_sampled['i'], s=5, alpha=0.4, color='green', label="Current Raw")
ax2.plot(df['t'], df['i_pred'], color='orange', linewidth=2, label="Current Fit")
ax2.set_ylabel("Current (A)", color='green')
ax2.tick_params(axis='y', labelcolor='green')
ax2.legend(loc='upper right')

# Plot title and layout
plt.title("Time vs Voltage (Left) and Time vs Current (Right) with Polynomial Regression [250us]")
plt.tight_layout()
plt.show()
