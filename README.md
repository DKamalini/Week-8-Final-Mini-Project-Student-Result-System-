# Week-8-Final-Mini-Project Student-Result-System

*Step 1: Create a CSV file of student marks*

students.csv:

Name,Math,Science,English

Asha,85,90,78

Rahul,70,65,80

Sneha,95,88,92

Vikram,60,72,68

*Step 2: Load CSV with Pandas*

```python

import pandas as pd

df = pd.read_csv("students.csv")

print("Student Marks Data:")

print(df)

```

*Step 3: Calculate Total, Average, and Result*

```python

df["Total"] = df["Math"] + df["Science"] + df["English"]

df["Average"] = df["Total"] / 3

df["Result"] = df["Average"].apply(lambda x: "Pass" if x >= 40 else "Fail")

print("\nFinal Result:")

print(df)

```

*Step 4: Find Class Topper*

```python

topper = df.loc[df["Total"].idxmax()]

print("\nClass Topper:", topper["Name"], "with Total Marks:", topper["Total"])

```

*Step 5: Export Final Results to CSV*

```python

df.to_csv("final_results.csv", index=False)

print("\nFinal results saved as final_results.csv")

```

Output will look like:

```python

     Name  Math  Science  English  Total    Average  Result

0    Asha    85       90       78    253  84.333333    Pass

1   Rahul    70       65       80    215  71.666667    Pass

2   Sneha    95       88       92    275  91.666667    Pass

3  Vikram    60       72       68    200  66.666667    Pass

Class Topper: Sneha with Total Marks: 275

```
