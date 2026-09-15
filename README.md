Experiment 3: PYTHON DATA ANALYSIS (PANDAS)  
Negranza, Jake Andrei D.  
2ECE-A  
September 15, 2026
```
import pandas as pd

#Load the csv file
cars = pd.read_csv('cars.csv')
```
A. Positional and Label-based Slicing
```
# part a
print("Shape of DataFrame: ", cars.shape)
print("Column Names: ", cars.columns.tolist())

# part b
cars_6_to_10 = cars.iloc[5:10]

# part c
cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
B. Model Lookup
```
# part a
toyota = cars[cars['Model'] == 'Toyota Corolla']
display(toyota)

# part b
pontiac = cars[cars['Model'] == 'Pontiac Firebird'][['Model', 'mpg', 'hp', 'wt',]]
display(pontiac)
```

C. Multi-model Subsetting
```
selected_models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']
selected_cars = cars[cars['Model'].isin(selected_models)][['Model' ,'mpg', 'cyl', 'hp', 'gear']]

display(selected_cars)
print("Shape of selected_cars", selected_cars.shape)
```
