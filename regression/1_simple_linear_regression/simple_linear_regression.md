### Simple Linear Regression Intuition & Code Explanation

**y = b0 + b1*x1**  
where, y = Dependent Variable (DV) (Something which we are trying to explain)  
       b0 = Constant  
       b1 = Co-efficient of DV  
       x1 = Independent Variable (IV) (Sometimes IV may be direct cause of change in DV, sometimes it may be not)  
In Simple Linear Regression there is only one IV  

**Data**  
salary_data.csv file consists of 30 employees years of experience & salary data  
- YearsExperience - Independent Variable
- Salary - Dependent Variable

```csv
YearsExperience      Salary
1.1                  39343
1.3                  46205
1.5                  37731
```

```python
# Importing the libraries
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
```
- numpy - mathematical tool to include any type of mathematics. Also used to make arrays, only allowed input for Neural Network.
- matplotlib.pyplot - plot charts to visualize the results
- pandas - best library to import/manage datasets

```python
# Importing the dataset
dataset = pd.read_csv('salary_data.csv')
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, 1].values
```
pandas read_csv() method is used to read the csv file
