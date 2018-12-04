title: Plotting multiple data on same axes
--- |
  We can plot multiple sets of data on the same figure and axes by calling the `plot` function multiple times before the command plt.show(). For plots with multiple data on same axes, it becomes important to add a legend. [matplotlib.axes.Axes.legend](matplotlib.axes.Axes.legend) is used to add legend in object oriented approach. The default location of legend is 'best' for axes and 'upper right' for figures. It can be set to any other position using parameter `loc`.

---
type: live-code
id: daa3317d-816e-437a-9551-35c5c8a378ad
code: |
  import matplotlib.pyplot as plt
  import numpy as np

  x = np.arange(0,4, 0.2)
  y = x ** 2
  z = x ** 3

  fig, ax = plt.subplots()
  ax.plot(x, y, color='b', linestyle = '--')
  ax.plot(x, z, color='r', linestyle = ':')

  # Add gridlines
  ax.grid(linestyle='-', linewidth='0.5')

  plt.show()
--- |
  Another way to plot multiple sets of data on the same figure and axes is calling [Axes.plot](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.plot.html#matplotlib-axes-axes-plot) multiple times but display the plot using plt.show after all the data is passed to Axes.plot. Multiple calls to the plot method will keep plotting different sets of data on the same axes. Lets plot sepal length vs sepal width in iris dataset but choose different color formatting by species (setosa, versicolor, verginica), we can create three sets of arrays corresponding to the species and plot them by calling Axes.plot thrice. Use different color and/or format for differentiating the data.
---
type: live-code
id: f97ded30-a494-4b13-af03-585b7693286e
code: |
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  iris = pd.read_csv('data/iris.csv')

  X_setosa = iris.loc[iris['species'] == 'setosa','sepal_length']
  y_setosa = iris.loc[iris['species'] == 'setosa', 'petal_length']

  X_versicolor = iris.loc[iris['species'] == 'versicolor','sepal_length']
  y_versicolor = iris.loc[iris['species'] == 'versicolor', 'petal_length']

  X_virginica = iris.loc[iris['species'] == 'virginica','sepal_length']
  y_virginica = iris.loc[iris['species'] == 'virginica', 'petal_length']


  fig, ax = plt.subplots()
  ax.plot(X_setosa, y_setosa, 'bo')
  ax.plot(X_versicolor, y_versicolor, 'ro')
  ax.plot(X_virginica, y_virginica, 'go')
  ax.grid(True)
  plt.show()
---
