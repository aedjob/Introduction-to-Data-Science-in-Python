# Loading Data in pandas
`import pandas as pd`

## What is pandas
Module for working with tabular data (csv, sql, google sheet)
- Loading tabular data from different sources
- Search for **rows or columns**.
- Calculate **aggregate stats**.
- Combine data from **multiple sources**.
New data type: dataframe

### Loading a CSV
```python
import pandas as pd
df = pd.read_csv('ransom.csv')
print(df)
```

### Inspecting a dataframe
`print(df.head())` > shows df top rows
`print(df.info())` > shows dataframe schema

### Examples
```python 
# Import pandas under the alias pd
import pandas as pd

# Load the CSV "credit_records.csv"
credit_records = pd.read_csv('credit_records.csv')

# Display the first five rows of credit_records using the .head() method
print(credit_records.head())

#Use .info() to inspect the DataFrame credit_records
print(credit_records.info())
```

## Selecting columns
```python
# Two ways of selecting rows:

# select column with []
suspect = credit_records['suspect']
print(suspect)

# select column with . (do not use for columns with spaces or special chars)
price = credit_records.price
print(price)
```

## Selecting rows
```python
# logical statements (>, >=, <, <=, ==)
question = 12 * 8
solution = 96
question == solution #returns boolean 'True'

# not equal 
name = 'bayes'
name != 'Bayes' #returns 'True' (bayes is not equal to Bayes)

# using logic with dataframes
credit_records.price > 20.00  #returns true or false for every row
credit_records[credit_records.price > 20.00]  #returns only rows where condition fits
```
