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
- X - Independent Variable
- y - Dependent Variable
pandas read_csv() method is used to read the csv file  
```python
iloc[:, :-1]
```  
**explanation of above syntax & intuition**    
the left side of comma is rows & right side of comma is columns  
1:3 means all the columns from index 1 to 2. Lower bound is ignored  
:-1 means all the columns except the last one  
```python
# Splitting the dataset into the Training set and Test set
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 1/3, random_state = 0)
```
**explanation of above syntax & intuition**  
we split the data into **Training set** (on which Machine Learning model learns) & **Test set** (on which we test if Machine Learning model learned the correlation). There should not be much difference in performance.  
**Machine Learning model is going to learn to do something (predict/other M/L goals) on the dataset by understanding some correlation when there is new dataset**  
```python
sklearn.model_selection.train_test_split(*arrays, **options)
```
**Parameters**  
- *arrays - sequence of indexables with same length / shape[0]
  - Allowed inputs are lists, numpy arrays, scipy-sparse matrices or pandas dataframes
- test_size - float or int, default=None
  - If float, should be between 0.0 and 1.0 and represent the proportion of the dataset to include in the test split. If int, represents the absolute number of test samples. If None, the value is set to the complement of the train size. If train_size is also None, it will be set to 0.25.
- random_state - int or RandomState instance, default=None
  - Controls the shuffling applied to the data before applying the split. Pass an int for reproducible output across multiple function calls.
```python
# Fitting Simple Linear Regression to the Training set
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train, y_train)
```
**explanation of above syntax & intuition**  





