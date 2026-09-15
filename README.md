# Experiment 3: PYTHON DATA ANALYSIS (PANDAS)  
## Negranza, Jake Andrei D.  
## 2ECE-A  
## September 15, 2026  
---
## 🖊 Intended Learning Outcomes
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.
---
## ❗️Instructions  
Use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Note-
book and import Pandas as pd. The dataset contains the Model column together with the vehicle
variables used in the original experiment.  
• Load the CSV file into a DataFrame named cars.  
• Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any
requested table or answer.  
• Do not modify values in cars; create a new DataFrame or Series for each requested subset.  
• Preserve the row order of the source dataset unless stated otherwise.  
• Display every requested result in an executed notebook cell.  

---
### This code imports the Pandas library (pd) and load the CSV file into the DataFrame named cars
```
import pandas as pd

cars = pd.read_csv('cars.csv')
```
---
## A. Positional and Label-based Slicing
Checks basic DataFrame structure by outputting its shape and columns, then extracts rows 6 through 10 using index-based slicing (iloc) and isolates specific vehicle attribute columns using label indexing.
```
# part a
print("Shape of DataFrame: ", cars.shape)
print("Column Names: ", cars.columns.tolist())

# part b
cars_6_to_10 = cars.iloc[5:10]

# part c
cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
## Sample Output:  
Shape of DataFrame:  (32, 12)  
Column Names:  ['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']  
| Model | mpg | cyl | hp |
| :--- | :--- | :--- | :--- |
| `rotate_word(text)` | `text` (str) | `str` | Moves index `0` to end using `text[1:] + text[0]` |
| `make_username(first_name, last_name)` | `first_name` (str), `last_name` (str) | `str` | Lowercases, strips spaces, joins with `.` |
| `swap_bookends(lst)` | `lst` (list) | `list` | Unpacks using `first, *middle, last`, swaps endpoints |

---
## B. Model Lookup
Demonstrates targeted row filtering using conditional criteria on the Model column to locate and display specific vehicle records (Toyota Corolla and Pontiac Firebird) without using fixed row numbers.  
```
# part a
toyota = cars[cars['Model'] == 'Toyota Corolla']
display(toyota)

# part b
pontiac = cars[cars['Model'] == 'Pontiac Firebird'][['Model', 'mpg', 'hp', 'wt',]]
display(pontiac)
```
---
## C. Multi-model Subsetting
Performs multi-value Boolean filtering using .isin() to retrieve records for three specific car models simultaneously, displaying a restricted 5-column subset verified to contain exactly 3 rows.  
```
selected_models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']
selected_cars = cars[cars['Model'].isin(selected_models)][['Model' ,'mpg', 'cyl', 'hp', 'gear']]

display(selected_cars)
print("Shape of selected_cars", selected_cars.shape)
```
