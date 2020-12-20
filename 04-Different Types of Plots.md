# Different Types of Plots

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
