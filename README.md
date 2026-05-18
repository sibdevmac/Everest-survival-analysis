# Everest Survival Analysis
## Introduction
Mount Everest is one of the most ambitious challenges attempted by mountaineers across the world. Although climbing Everest offers extraordinary experiences, it also presents severe risks and life-threatening environmental conditions. Therefore, this project focuses on analyzing Everest expedition accident data to identify safer climbing routes and understand the factors contributing to fatalities. The inspiration for this project comes from the first successful Everest expedition launched on 18 May 1953. This historical milestone motivated the analysis of expedition routes, environmental conditions, and climber risks using data science techniques.

---

# Dataset

Dataset Source:  
https://www.kaggle.com/datasets/syedmuhammadbilal12/mount-everest-accident-dataset-2020-2025

The dataset contains accident records from Everest expeditions between 2020 and 2025.

---

# Assumptions

- The dataset is analyzed without bias.
- The objective is solely to identify safer expedition routes using statistical and predictive analysis.
- The available accident records are representative of expedition risks during the study period.

---

# Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Folium

---

# Aim of the Project

## Aim
This project intends to identify which Everest route gives climbers the highest probability of success with the lowest mortality risk.

---

# Research Questions

1. Which route has the highest mortality rate?
2. At what altitude do most deaths occur?
3. How do weather and season affect fatalities?
4. Does experience level affect survival risk?
5. Which route offers the safest overall expedition?
6. Can a machine learning model identify the optimal route?
7. How can the five safest routes be geographically mapped?

---

# Data Description

- Total Rows: 500
- Total Columns: 13
- Dataset Period: 2020–2025
- Data Types:
  - 11 Object Columns
  - 2 Integer Columns

## Dataset Columns

- Date
- Name
- Nationality
- Age
- Gender
- Cause_of_Death
- Altitude_meters
- Location
- Route
- Season
- Weather_Conditions
- Experience_Level
- Expedition_Company

---

# Pre-Examination of Data

The dataset was initially examined to identify:
- Null values
- Duplicate entries
- Inconsistent route naming
- Unnecessary characters

## Missing Value Check

The dataset contained no null values, allowing the analysis to proceed without data imputation.

```python
print(df.isnull().sum())
```

## Removing Duplicates

```python
df = df.drop_duplicates()
```

## Cleaning Route Names

```python
df['Route'] = df['Route'].str.strip()
```

---

# Analysis Results

# 1. Which Route Has the Highest Mortality Rate?

The analysis showed that:
- East Face
- Southwest Face
- South Col Route (Nepal)

tend to be much riskier than:
- West Ridge
- Northeast Ridge Route (Tibet)

## Interpretation

The East Face and Southwest Face are highly technical and avalanche-prone routes. In contrast, Tibet-side routes have fewer icefall risks and comparatively stable climbing sections.

---

# 2. At What Altitude Do Most Deaths Occur?

The majority of fatalities occur above the 8000-meter zone, commonly referred to as the "Death Zone."

## Key Findings

- Around 5400m → fewer fatalities
- 6000–6400m → avalanche-related fatalities increase
- 8000m+ → severe oxygen deprivation and exhaustion

## Interpretation

The 6400–7100m region acts as a transition zone where climbers attempt acclimatization and recovery before entering the Death Zone.

---

# 3. How Do Weather and Season Affect Fatalities?

## Weather Analysis

Extreme cold conditions resulted in the highest number of fatalities, primarily due to:
- Frostbite
- Hypothermia
- Oxygen system failures

Interestingly, snowstorms and whiteouts showed lower fatalities because climbers often avoid movement during those conditions.

## Seasonal Analysis

### Highest Fatalities
- Summer (June–August)

### Reasons
- Overcrowding
- Traffic jams
- Delayed summit attempts

### Second Highest
- Winter

### Reasons
- Severe weather
- Frostbite
- Rapid environmental deterioration

## Recommendation

- Summer requires better crowd management
- Winter requires specialized rescue infrastructure

---

# 4. Does Experience Level Affect Survival Risk?

## Findings

### Highest Fatalities
- Novice Climbers

### Reasons
- Poor acclimatization
- Lack of altitude experience
- Poor pacing

### Intermediate to Expert Climbers
Despite experience, fatalities remained high due to:
- Overconfidence
- Ignoring local guidance
- Aggressive summit attempts

### Lowest Fatalities
- Sherpas
- Professional Guides

### Reasons
- Elite altitude adaptation
- Extensive route knowledge

---

# 5. Which Route Offers the Safest Overall Expedition?

The safety score analysis showed:

| Route | Safety Score |
|---|---|
| East Face | Highest (~64) |
| West Ridge | Lowest (~57.6) |
| Northeast Ridge | Lowest (~57.6) |

## Interpretation

Although East Face showed higher safety scores statistically, this may result from fewer expedition attempts due to its dangerous reputation.

The Northeast Ridge and Southeast Ridge emerged as practical safer alternatives because of:
- Better infrastructure
- Easier rescue operations
- Lower icefall exposure

---

# 6. Machine Learning Model for Optimal Route Prediction

A Decision Tree Classifier was used to classify expedition risk levels based on altitude.

## Risk Classification

- Low Risk → below 7000m
- Medium Risk → 7000m–8000m
- High Risk → above 8000m

## Example

```python
model.predict([[8500]])
```

### Output

```python
['High Risk']
```

## Interpretation

The model successfully identified:
- High-altitude expeditions as highly dangerous
- Lower-altitude sections as comparatively safer

---

# 7. Geographical Mapping of the Five Safest Routes

An interactive Folium map was created to visualize:
- Southeast Ridge
- South Col Route
- Northeast Ridge
- North Col Route
- West Ridge

## Key Insight

The Southeast Ridge and Northeast Ridge were identified as safer due to:
- Better rescue accessibility
- Improved infrastructure
- More established expedition systems

The Tibet-side Northeast Ridge may become a stronger alternative in the future if infrastructure continues to improve.

---

# Technologies Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import folium
from sklearn.tree import DecisionTreeClassifier
```

---

# Key Insights

- Most fatalities occur above 8000 meters.
- Extreme cold is deadlier than storms in many cases.
- Summer overcrowding significantly increases expedition risk.
- Novice climbers remain the most vulnerable group.
- Southeast Ridge and Northeast Ridge emerged as comparatively safer routes.
- Risk on Everest is influenced by both environmental severity and human decision-making.

---

# Conclusion

This project demonstrates that Everest fatalities are rarely caused by a single factor. Instead, deaths result from a complex interaction between:
- Altitude
- Weather
- Seasonal crowding
- Route selection
- Human endurance
- Experience levels

The findings suggest:
- Summer expeditions should be reduced or better regulated.
- Spring and Autumn offer safer climbing windows.
- Local intelligence and rescue systems should be strengthened.
- Southeast Ridge and Northeast Ridge currently provide the safest balance between accessibility and survivability.

Ultimately, data-driven expedition planning can help reduce mortality risks and improve the safety of future Everest campaigns.

---

# Author

Sibankar Saha
