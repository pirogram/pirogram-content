title: Plotting multiple data on same axes
--- |
  We can plot multiple sets of data on the same figure and axes by calling the `plot` function multiple times before the command plt.show().
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
  Another way to plot multiple sets of data on the same figure and axes is calling [Axes.plot](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.plot.html#matplotlib-axes-axes-plot) multiple times but display the plot using plt.show at the end. Multiple calls to the plot method will keep plotting different sets of data on the same axes.

  Eg: Plot of sepal length vs sepal width with different color formatting by species (setosa, versicolor, verginica).
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
