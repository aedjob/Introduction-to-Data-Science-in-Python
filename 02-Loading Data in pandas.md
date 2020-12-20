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
```python
# Select the dogs where Age is greater than 2
greater_than_2 = mpr[mpr.Age > 2]
print(greater_than_2)

# Select the dogs whose Status is equal to Still Missing
still_missing = mpr[mpr.Status == 'Still Missing']
print(still_missing)

# Select all dogs whose Dog Breed is not equal to Poodle
not_poodle = mpr[mpr['Dog Breed']!='Poodle']
print(not_poodle)
```
```python
print(credit_records.head())

# Select purchases from 'Pet Paradise'
purchase = credit_records[credit_records.location == 'Pet Paradise']

# Display
print(purchase)
```

## Creating line plots
New module: `matplotlib`
### Matplotlib
```python
from matplotlib import pyplot as plt  #loads matplotlib

#create 2 different line plots and display them
plt.plot(data1.x_values, 
         data1.y_values)
plt.plot(data2.x_values, 
         data2.y_values)
plt.show()                    
```

### Adding labels and legends (to line plot)
```python
#plain plot
from matplotlib import pyplot as plt
plt.plot(ransom.letter,
         ransom.frequency)
plt.show()

#axes and title labels (before plt.show())
plt.xlabel("Letter")
plt.ylabel("Frequency")
plt.title("Ransom Note Letters")

#legends
plt.plot(aditya.days,
         aditya.cases,
         label="Aditya")
plt.legend()

#arbitraty text (quick note)
plt.text(xcoord,
        ycoord,
        "Text Message")   #generic
plt.text(5,
        9,
        "Low H frequency")   #example

#modifying text
plt.title("Plot title", fontsize = 20)  #change font size
plt.legend(color="green")               #change font color
```
https://en.wikipedia.org/wiki/Web_colors

### Adding some style
```python
plt.plot(x, y1, color="tomato")     #changing line color
plt.plot(x, y2, color="seagreen")
plt.plot(x, y1, linewidth = 2)      #changing line width
plt.plot(x, y1, linestyle = '-')      #changing line style (can be: '-',dashed:'--','-.',dotted:':')
plt.plot(x, y1, marker = 'x')      #adding markers (can be: 'x',square:'s',circle:'o',diamond:'d','*','h')

#setting a style
plt.style.use('fivethirtyeight')
plt.style.use('ggplot')
plt.style.use('seaborn')
plt.style.use('deafult')
```
### Full example
```python
# Plot each line
plt.plot(ransom.letter, ransom.frequency,
         label='Ransom', linestyle=':', color='gray')
plt.plot(suspect1.letter, suspect1.frequency, label='Fred Frequentist')
plt.plot(suspect2.letter, suspect2.frequency, label='Gertrude Cox')

# Add x- and y-labels
plt.xlabel("Letter")
plt.ylabel("Frequency")

# Add a legend
plt.legend()

# Display plot
plt.show()
```

## Scatter plot
```python
plt.scatter(df.age, df.height,
            color = 'green',
            marker = 's',
            alpha = 0.1)   #transparency

plt.xlabel('Age (in months)')
plt.ylabel('Height (in inches)')
plt.show()
```

## Bar chart
```python
#vertical bar charts
plt.bar(df.precint,
        df.pets_abducted,
        yerr=df.error)     #add error bar
plt.ylabel('Pet Abductions')
plt.show()

#horizontal bar charts
plt.barh(df.precint,
        df.pets_abducted)
plt.ylabel('Pet Abductions')
plt.show()

#stacked bar charts
plt.bar(df.precint, df.dog,
        label='Dog')
plt.bar(df.precint, df.cat,
        bottom=df.dog,
        label='Cat')
plt.legend()
plt.show()
```

## Histogram
```python
plt.hist(gravel.mass)
plt.show()

#changing bins
plt.hist(data, bins=nbins)
plt.hist(gravel.mass, bins=40)

#changing range (zoom in)
plt.hist(data,
         range=(xmin, xmax))
plt.hist(data,
         range=(50, 100))

#normalizing (when 2 different variables have a very different scale, this makes the sum of bar area = 1)
plt.hist(male_weight, density=True) 
plt.hist(female_weight, density=True) 
```







