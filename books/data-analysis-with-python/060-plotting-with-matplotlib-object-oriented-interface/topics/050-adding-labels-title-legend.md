title: Adding labels, title and legend to plots
--- |
  The axes properties like X and Y axis labels, plot title and legend are controlled by [Axes setters & getters] (https://matplotlib.org/api/axes_api.html#axis-labels-title-and-legend). Lets look at them one by one.
  ### Set xlabel and ylabel
  [Axes.set_xlabel](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_xlabel.html#matplotlib.axes.Axes.set_xlabel) and [Axes.set_ylabel](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_ylabel.html#matplotlib.axes.Axes.set_ylabel) are used to set X and Y axes labels respectively.
---
type: live-code
id: c9a0d406-92e3-48db-82aa-f078532ef377
code: |
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  iris = pd.read_csv('data/iris.csv')

  x = iris['sepal_length']
  y = iris['petal_length']
  fig, ax = plt.subplots()
  ax.plot(x, y, 'o')
  ax.set_xlabel('Sepal Length')
  ax.set_ylabel('Petal Length')
  plt.show()
--- |
  ### Set title
  [Axes.set_title](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_title.html#matplotlib.axes.Axes.set_title) sets title for the axes.
---
type: live-code
id: fcd559ab-29c9-48d7-9107-dfabdacb4fa4
code: |
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  iris = pd.read_csv('data/iris.csv')

  x = iris['sepal_length']
  y = iris['petal_length']
  fig, ax = plt.subplots()
  ax.plot(x, y, 'o')
  ax.set_title('Iris Sepal length vs Petal length')
  plt.show()
--- |
  ### Place legend
  [Axes.legend](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.legend.html#matplotlib.axes.Axes.legend) places a legend on the axes.
---
type: live-code
id: 6eca0f51-b339-4d36-b038-d696b76b899f
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
  ax.plot(X_setosa, y_setosa, 'bo', label = 'Setosa')
  ax.plot(X_versicolor, y_versicolor, 'ro', label = 'Versicolor')
  ax.plot(X_virginica, y_virginica, 'go', label = 'verginica')

  ax.set_title('Iris Sepal length vs Petal length')

  ax.set_xlabel('Sepal Length')
  ax.set_ylabel('Petal Length')

  ax.legend()
  ax.grid(True)
  plt.show()
--- |
  The Axes properties `label`, `title` and `legend` have corresponding `getters` which return the label and title as text strings and the legend instancey.
---
type: live-code
id: 2ef8ad6f-4b65-4c32-bba5-9bc10907dea9
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
  ax.plot(X_setosa, y_setosa, 'bo', label = 'Setosa')
  ax.plot(X_versicolor, y_versicolor, 'ro', label = 'Versicolor')
  ax.plot(X_virginica, y_virginica, 'go', label = 'verginica')

  ax.set_title('Iris Sepal length vs Petal length')

  ax.set_xlabel('Sepal Length')
  ax.set_ylabel('Petal Length')

  ax.legend()
  ax.grid(True)
  plt.show()

  print('X label: ', ax.get_xlabel())
  print('Y label: ', ax.get_ylabel())
  print('Title: ', ax.get_title())
  print('Legend: ', ax.get_legend())
---
