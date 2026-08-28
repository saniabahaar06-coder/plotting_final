# # Exp 6 Analysis and Visualization of COVID-19 Dataset using Python

**Date:29-08-2026**

## AIM:

To analyse a large real-world COVID-19 dataset using Python and visualize key trends and relationships using multiple types of graphs for meaningful insights.

## DESIGN STEPS:

### Step 1:

Clone the repository from GitHub.

### Step 2:

Create a Python project in the preferred IDE (VS Code/PyCharm/Jupyter Notebook).

### Step 3:

Create the Python program for analysing and visualizing the COVID-19 dataset using **Pandas** and **Matplotlib** libraries.

### Step 4:

Load the **`covid_cases.csv`** dataset using Pandas and explore the dataset by displaying its shape and column names.

### Step 5:

Check and handle missing values in the dataset, if any.

### Step 6:

Perform basic data exploration by finding the total number of records and generating the statistical summary using the `describe()` function.

### Step 7:

Use Matplotlib to create different visualizations:

* **Line Graph:** Trend of confirmed cases over time globally.
* **Bar Chart:** Top 10 countries by total confirmed cases.
* **Pie Chart:** Case distribution of the top 5 affected countries.
* **Scatter Plot:** Relationship between confirmed cases and deaths.
* **Histogram:** Distribution of active cases.

### Step 8:

Add appropriate titles, axis labels, legends, and other necessary labels to the graphs.

### Step 9:

Execute the program and analyze the generated visualizations to identify meaningful trends and relationships in the COVID-19 dataset.

## PROGRAM:

```
import pandas as pd
import matplotlib.pyplot as plt

# Load the COVID-19 dataset
df = pd.read_csv("covid_case.csv")

# Display first 5 records
print("First 5 Records:")
print(df.head())

# Dataset information
print("\nDataset Information:")
print(df.info())

# Check missing values
print("\nMissing Values:")
print(df.isnull().sum())

# Basic statistical analysis
print("\nStatistical Summary:")
print(df.describe())

# Total COVID-19 cases by country
country_cases = df.groupby("Country")["Confirmed"].sum().sort_values(ascending=False)

print("\nTotal Confirmed Cases by Country:")
print(country_cases)

# Total deaths by country
country_deaths = df.groupby("Country")["Deaths"].sum().sort_values(ascending=False)

print("\nTotal Deaths by Country:")
print(country_deaths)

# Total recovered cases by country
country_recovered = df.groupby("Country")["Recovered"].sum().sort_values(ascending=False)

print("\nTotal Recovered Cases by Country:")
print(country_recovered)

# ---------------- Visualization ----------------

# 1. Confirmed cases by country
plt.figure(figsize=(8, 5))
country_cases.plot(kind="bar")
plt.title("Total Confirmed COVID-19 Cases by Country")
plt.xlabel("Country")
plt.ylabel("Confirmed Cases")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# 2. Deaths by country
plt.figure(figsize=(8, 5))
country_deaths.plot(kind="bar")
plt.title("Total COVID-19 Deaths by Country")
plt.xlabel("Country")
plt.ylabel("Deaths")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# 3. Recovered cases by country
plt.figure(figsize=(8, 5))
country_recovered.plot(kind="bar")
plt.title("Total Recovered COVID-19 Cases by Country")
plt.xlabel("Country")
plt.ylabel("Recovered Cases")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# 4. COVID-19 trend over time
df["Date"] = pd.to_datetime(df["Date"])

daily_cases = df.groupby("Date")["Confirmed"].sum()

plt.figure(figsize=(10, 5))
daily_cases.plot(kind="line")
plt.title("COVID-19 Confirmed Cases Over Time")
plt.xlabel("Date")
plt.ylabel("Confirmed Cases")
plt.grid()
plt.tight_layout()
plt.show()

# 5. Active cases by country
active_cases = df.groupby("Country")["Active"].sum().sort_values(ascending=False)

plt.figure(figsize=(8, 5))
active_cases.plot(kind="bar")
plt.title("Active COVID-19 Cases by Country")
plt.xlabel("Country")
plt.ylabel("Active Cases")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

```
## OUTPUT:
<img width="863" height="945" alt="Screenshot 2026-08-28 105102" src="https://github.com/user-attachments/assets/58a04815-4366-450b-8567-caf463787506" />

<img width="647" height="753" alt="Screenshot 2026-08-28 105241" src="https://github.com/user-attachments/assets/550da10a-4eca-4690-a4b0-f15b09732f5b" />

<img width="581" height="470" alt="Screenshot 2026-08-28 105305" src="https://github.com/user-attachments/assets/d72a0ad6-c564-4c02-a4ef-a3b715f0ca2e" />
<img width="1137" height="696" alt="Screenshot 2026-08-28 105330" src="https://github.com/user-attachments/assets/96f4ae3e-a527-44fc-8eae-d55a0b9e6ce1" />
<img width="1127" height="687" alt="Screenshot 2026-08-28 105344" src="https://github.com/user-attachments/assets/781fe05d-edab-455e-a0e8-789911d54ba4" />
<img width="1137" height="560" alt="Screenshot 2026-08-28 105407" src="https://github.com/user-attachments/assets/c2db7035-ad75-464d-a8e2-0e77df9a9e50" />
<img width="1137" height="685" alt="Screenshot 2026-08-28 105430" src="https://github.com/user-attachments/assets/72570faa-b436-4941-ab9f-6d0bb3d7f745" />




## RESULT:

The COVID-19 dataset was successfully analysed using Python. The dataset was explored using Pandas, and meaningful trends and relationships were visualized using different types of graphs such as line graph, bar chart, pie chart, scatter plot, and histogram using Matplotlib.
