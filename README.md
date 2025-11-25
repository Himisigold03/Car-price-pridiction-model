# Car-price-pridiction-model
This is a model built to predict how much a car will be sold base on various factors contained in the dataset

---

# Car Dataset Cleaning and Exploration

This repository contains code for loading, inspecting, cleaning, and analyzing a car dataset stored in an Excel file. The project demonstrates essential data-wrangling steps using Python, Pandas, and NumPy.

For questions or collaboration, contact: **[aishatadeniyi418@gmail.com](mailto:aishatadeniyi418@gmail.com)**

---

## Project Overview

The dataset contains car listings with features such as:

* Location
* Maker
* Model
* Year
* Colour
* Amount (in million Nigerian Naira)
* Type
* Distance travelled (in kilometers)

The goal of this project is to:

1. Load and examine the dataset
2. Understand its structure and summary statistics
3. Handle missing values
4. Inspect unique categorical values
5. Prepare the dataset for further analysis or modeling

---

## Code Used

```python
import pandas as pd
import numpy as np

df = pd.read_excel('data/Car.xlsx')

df.head()
```

---

## Dataset Information

The dataset structure can be inspected using:

```python
df.info()
```

Example output:

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 4487 entries, 0 to 4486
Data columns (total 8 columns):
 #   Column              Non-Null Count  Dtype  
---  ------              --------------  -----  
 0   Location            4487 non-null   object 
 1   Maker               4487 non-null   object 
 2   Model               4487 non-null   object 
 3   Year                4487 non-null   int64  
 4   Colour              4487 non-null   object 
 5   Amount (Million ₦)  4487 non-null   float64
 6   Type                4487 non-null   object 
 7   Distance_Km         2932 non-null   float64
```

Dataset shape:

```python
df.shape
```

---

## Summary Statistics

```python
df.describe()
```

Example output shows:

* Year: 1982 to 2022
* Amount: 0.42M to 454M
* Distance_Km: 1 km to over 1.7 million km

---

## Handling Missing Values

Distance_Km contains missing values. Since missing values are less than 70 percent, they were replaced with the mean:

```python
mean_value = df["Distance_Km"].mean()
df['Distance_Km'] = df['Distance_Km'].fillna(mean_value)
df.isnull().sum()
```

---

## Exploring Categorical Features

The following categorical features were inspected:

```python
cat_features = {
    "Location",
    "Model",
    "Maker",
    "Year",
    "Colour",
    "Type",
}

for value in cat_features:
    print(value, df[value].unique(), sep=":")
    print("*"*70)


This helps identify inconsistent naming, special cases, or values requiring recoding.


## Key Steps Performed

* Loaded dataset from Excel
* Displayed data samples
* Inspected info, shape, and descriptive statistics
* Checked missing values
* Filled missing Distance_Km values with mean
* Examined unique categorical values
* Identified potential data-cleaning opportunities (renaming, type correction, standardization)


## Contact

For questions, suggestions, or collaboration, email:

**[aishatadeniyi418@gmail.com](mailto:aishatadeniyi418@gmail.com)**
