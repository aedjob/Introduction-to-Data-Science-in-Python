# Plotting Data with matplotlib

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

