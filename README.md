# Introduction-to-Data-Science-in-Python
*Data Analyst with Python track*

## Modules and variables
- Modules group functions together
```python
import pandas as pd
import numpy as np
```
- Add a module using `import`
- `import` happens at the beginning of a script file
- Variables store data: strings or floats.

## Using functions
- Perform a task
- Positional arguments
- Keyword arguments

## Work with tabular data
- `import pandas as pd`
- DataFrames store tabular data
- Inspect data using `.head()` or `info()`
- Select rows using logic
```python
credit_reports[
    credit_report.suspect == 
    'Freddy_frequentist']
```

## Creating line plots
- `from matplotlib import pyplot as plt`
- Use `plt.plot()` to create a line plot
- Modify line plots with keyword arguments 
- Add labels and legends

## More plot types
- `plt.scatter()` shows individual data points
- `plt.bar()`
- `plt.hist()` visualizes distributions
