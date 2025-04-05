# 🧠 Data Mining Project – Steps Overview

---

## 1️⃣ Import Libraries

```python
import pandas as pd  
import numpy as np  
import matplotlib.pyplot as plt  
import seaborn as sns  
from sklearn.linear_model import LinearRegression  
from sklearn.model_selection import train_test_split  
from sklearn.metrics import mean_squared_error, r2_score  
from sklearn.pipeline import make_pipeline  
from sklearn.compose import ColumnTransformer  
from sklearn.preprocessing import OneHotEncoder  
from sklearn.tree import DecisionTreeRegressor  
from nameparser import HumanName
```

---

## 2️⃣ Load & Display the Dataset

📂 Load the dataset using:

```python
df = pd.read_csv("your_dataset.csv")
df.head()
```

---

## 3️⃣ Clean the Data 🧼

- Check for duplicates: `df.duplicated().sum()`
- Remove duplicates: `df = df.drop_duplicates()`
- Check for missing values: `df.isnull().sum()`
- Remove negative values if not logical.

---

## 4️⃣ Add Gender Attribute 🚻

- Use `HumanName` to extract first names.
- Predict gender based on names (using a name list or a gender prediction library).
- Convert gender to numeric (e.g., Male = 1, Female = 0).

```python
from nameparser import HumanName

def predict_gender(name):
    # Your prediction logic here
    return "Male" or "Female"

df['Gender'] = df['EmployeeName'].apply(lambda name: predict_gender(HumanName(name).first))
df['Gender'] = df['Gender'].map({'Male': 1, 'Female': 0})
```

---

## 5️⃣ Quick Data Summary 🧾

Use:

```python
df.head()
df.describe()
df.info()
```

---

## 6️⃣ Data Analysis 🧮

- 📊 `BasePay` Mean: `df['BasePay'].mean()`
- 💰 Max `OvertimePay`: `df['OvertimePay'].max()`
- 👤 Employee with most `OvertimePay`
- 👥 Employees with highest `OvertimePay`
- 📌 Job title for top overtime employees
- 💸 `TotalPayBenefits` top values
- 🧍‍♂️ Person with most/least `TotalPayBenefits`
- 📆 Average pay per year
- 🧾 Number of job titles: `df['JobTitle'].nunique()`
- 🧍 Person with most `OtherPay`
- 📈 Top 10 jobs by median `BasePay`:
  ```python
  df.groupby('JobTitle')['BasePay'].median().nlargest(10).plot(kind='barh')
  ```
- 📉 Bottom 10 jobs by median `BasePay`
- 💲 Top 10 jobs by `OvertimePay`
- 💼 Top 10 jobs by `Benefits`
- 💰 Top 10 jobs by `TotalPay`
- 🏆 Top 10 by `TotalPayBenefits`
- 🔟 Most common jobs: `df['JobTitle'].value_counts().head(10)`
- 👮 Count of jobs with 'officer':
  ```python
  def officerWordCount(title):
      return 'officer' in title.lower()
  officer_count = df['JobTitle'].apply(officerWordCount).sum()
  ```

---

## 7️⃣ Visualization 📊

- 🍕 Pie chart of crime counts
- 🔵 Scatterplot: `OvertimePay` vs. `JobTitle`
- 🧱 `FacetGrid` for year-wise `TotalPay`
- 🔥 Heatmap of correlation:
  ```python
  sns.heatmap(df.corr(), annot=True)
  ```
- 📊 Barplot for top 30 jobs
- 🚒 Compare `BasePay` in Fire Department jobs:
  ```python
  fire_jobs = ['Chief, Fire Department','Asst Chf of Dept (Fire Dept)','Firefighter']
  df[df['JobTitle'].isin(fire_jobs)].groupby('JobTitle')['BasePay'].mean().plot(kind='bar')
  ```
- 🔥 Experience of Firefighters by counting occurrences of names

---

## 8️⃣ Linear Regression Model 📈

- 📊 `df.corr()` to check correlations
- 🎯 Target: `TotalPay`, Features: `JobTitle`, `Gender`
- 🔠 One-hot encode `JobTitle`
- ✂️ Split data: `train_test_split()`
- 🤖 Create & train model: `LinearRegression()`
- 📈 Predict and evaluate with `r2_score`
- 📏 Add diagonal reference line in the plot

---

## 9️⃣ Decision Tree Regression 🌳

- 🎯 Target: `TotalPay`, Features: `JobTitle`, `Gender`
- 🔠 Encode `JobTitle`
- ✂️ Split data
- 🌲 Train using `DecisionTreeRegressor()`
- 📈 Predict and evaluate with `r2_score`
- 📏 Diagonal line for reference in visualization

---

## 🔟 Assistant Chief of Department Analysis 🔍

- Filter: `df[df['JobTitle'] == "Asst Chf of Dept (Fire Dept)"]`
- Count employee names
- Add column: `experience = df.groupby('EmployeeName').transform('count')`
- Sort by experience
