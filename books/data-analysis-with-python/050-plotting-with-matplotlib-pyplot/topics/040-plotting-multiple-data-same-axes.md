title: Plotting Multiple data same axis
--- |
  If you wish to plot multiple sets of data on the same axes, pyplot offers a convenient way to do so. One way is to pass the multiple sets of data to pyplot.plot along with string formatting if required. The order in which we pass the parameters should be X axis values, Y axis values followed by formatting string.
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
  Another way to plot multiple sets of data on the same figure and axes is calling pyplot.plot multiple times but display the plot using plt.show after all the data is passed to plt.plot. Since pyplot works on the current axes, multiple calls to the plot method will keep plotting different sets of data on the same axes. Lets say we want to plot sepal length vs sepal width in iris dataset but choose different color formatting by species (setosa, versicolor, verginica), we can create three sets of arrays corresponding to the species and plot them by calling pyplot.plot thrice. Use different color and/or format for differentiating the data.
---
type: live-code
id: 4fa93a59-4863-467f-974c-ec497a652f49
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


  plt.figure(1)
  plt.plot(X_setosa, y_setosa, 'bo')
  plt.plot(X_versicolor, y_versicolor, 'ro')
  plt.plot(X_virginica, y_virginica, 'go')
  plt.show()
---
