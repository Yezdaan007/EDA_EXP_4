# EXP 4 -  Titanic Survival Analysis using Univariate Analysis

## Aim

To perform univariate analysis on the Titanic dataset to understand the distribution and characteristics of individual variables (such as Age, Sex, Pclass, Fare, and Survived) and to draw insights about passengers and their survival patterns.


## Algorithm

## 1)Import Libraries:

Load the required Python libraries (pandas, numpy, matplotlib, seaborn).

## 2)Load the Dataset:

Read the Titanic dataset from available sources (e.g., seaborn’s built-in Titanic dataset or a CSV file).

## 3)Data Inspection:

View the first few rows using head().

Get dataset summary using info() and describe().

## 4)Handle Missing Data:
Identify missing values using isnull().sum() and handle them appropriately (e.g., fill or drop).

## 5)Univariate Analysis:
Perform univariate analysis for each variable:

## 6)Categorical Variables: (e.g., Sex, Pclass, Survived, Embarked)
Use frequency tables and count plots.

## 7)Numerical Variables: (e.g., Age, Fare)
Use histograms, box plots, and summary statistics.

## 8)Interpretation:
Analyze distributions, central tendencies, and spread.
Identify patterns (e.g., more passengers in 3rd class, survival differences by gender).


## Program:

## A. Data Understanding

```
import pandas as pd
import seaborn as sns

# Load dataset
df = sns.load_dataset('titanic')

# First 5 records
df.head()

print(df.shape)

df.isnull().sum()


```

## Output:
<img width="1228" height="442" alt="image" src="https://github.com/user-attachments/assets/8a6187e8-4c9d-43bb-84ed-2e35bc4ec8e4" />

<img width="350" height="110" alt="image" src="https://github.com/user-attachments/assets/b8d6586d-9ab2-4006-b1f8-9e96cb7d35b0" />
<img width="493" height="676" alt="image" src="https://github.com/user-attachments/assets/aea864b9-1f41-4fed-94df-f4d7c602c4db" />


## B. Categorical Variable Analysis

```
print(df['sex'].value_counts())
print(df['sex'].value_counts(normalize=True) * 100)

print(df['survived'].value_counts(normalize=True) * 100)

print(df['pclass'].value_counts())

print(df['embarked'].value_counts())

print(df['deck'].value_counts())

```

## Output:

<img width="818" height="655" alt="image" src="https://github.com/user-attachments/assets/cae5ee11-9733-450d-a2e0-9d7e33fb0cc7" />
<img width="738" height="451" alt="image" src="https://github.com/user-attachments/assets/7d71042a-89cb-45a9-b4ad-60b8934d8153" />

## C. Numerical Variable Analysis

```
import matplotlib.pyplot as plt

plt.hist(df['age'].dropna(), bins=30)
plt.title("Age Distribution")
plt.xlabel("Age")
plt.ylabel("Frequency")
plt.show()

print("Mean:", df['age'].mean())
print("Median:", df['age'].median())
print("Range:", df['age'].max() - df['age'].min())

import seaborn as sns

sns.boxplot(x=df['fare'])
plt.title("Fare Boxplot")
plt.show()

plt.hist(df['fare'], bins=40)
plt.title("Fare Distribution")
plt.show()

print("Mean Fare:", df['fare'].mean())
print("Median Fare:", df['fare'].median())

```


## Output:
<img width="826" height="595" alt="image" src="https://github.com/user-attachments/assets/15d76571-cf19-4b0c-91ec-65b2a7050db6" />

<img width="770" height="675" alt="image" src="https://github.com/user-attachments/assets/aa80592e-c41b-4550-b614-b1483accb99a" />

<img width="802" height="623" alt="image" src="https://github.com/user-attachments/assets/abb586e3-9f74-426d-952c-fc766622b6c5" />

<img width="718" height="152" alt="image" src="https://github.com/user-attachments/assets/ccd44ca2-7c2d-4d68-b126-555ebecf94d4" />


## D. Insights

## i)From your analysis, what kind of passengers were most common?

```
From analysis:

Male

3rd Class

Embarked from Southampton

Age 20–40

 Typical passenger = Young adult male in 3rd class.
```


## ii)What initial trends can you observe that may relate to survival?

```
From general Titanic patterns:

Females survived more than males

1st class passengers survived more

Children had better survival

Higher fare → Higher survival probability

 Suggests "Women and children first" policy
 Wealth (class) influenced survival chances

```



## iii)Why is univariate analysis an important first step in data analysis?

```
Univariate analysis:

* Understands each variable individually
* Detects missing values
* Identifies outliers
* Detects skewness
* Understands data distribution
* Helps decide preprocessing steps


```



## Result
From the univariate analysis:

Majority of passengers were male and in 3rd class.

Around 38% survived, majority being females and higher-class passengers.

Age is right-skewed with most passengers aged 20–40 years.

Fare distribution shows a few high outliers for 1st class passengers.

Thus, univariate analysis helps understand the distribution and spread of each individual feature in the Titanic dataset before moving to bivariate or multivariate analysis.


