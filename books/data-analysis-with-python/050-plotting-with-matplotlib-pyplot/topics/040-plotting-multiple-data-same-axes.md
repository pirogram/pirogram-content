title: Plotting Multiple data same axis
--- |
  If you wish to plot multiple sets of data on the same `axes`, pyplot offers a convenient way to do so. One way is to pass the multiple sets of data to [pyplot.plot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.plot.html) along with string formatting if required. The order in which we pass the parameters should be X axis values, Y axis values followed by formatting string.
---
type: live-code
id: 3313a574-1a10-4181-989b-0bf4341df341
code: |
  import numpy as np
  import matplotlib.pyplot as plt

  x = np.arange(0,4, 0.2)
  y = x ** 2
  z = x ** 3
  plt.plot(x, x, 'bo', x, y, 'r*', x, z, 'g^')
  plt.show()
--- |
  Another way of plotting multiple sets of data on the same axes is by calling [pyplot.plot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.plot.html) multiple times but display the plot using plt.show at the end. Since pyplot works on the `current axes`, multiple calls to the plot method will keep plotting different sets of data on the same axes. In simple terms, `we are creating multiple plots but on the same axes and hence the points are overlaid`.

  Eg: Plot of sepal length vs sepal width from iris dataset with different color formatting by species (setosa, versicolor, verginica).
---
type: live-code
id: 22baa271-64d8-4d28-acb1-10fd9a67c424
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

  plt.figure()
  # Plot data corresponding to Setosa
  plt.plot(X_setosa, y_setosa, 'bo')
  # Add Versicolor. If you comment out the plot commands below, you will only see Setosa.
  plt.plot(X_versicolor, y_versicolor, 'ro')
  # Add Verginica. If you comment out the plot command below, you will only see Setosa and Versicolor.
  plt.plot(X_virginica, y_virginica, 'go')

  plt.show()
---
