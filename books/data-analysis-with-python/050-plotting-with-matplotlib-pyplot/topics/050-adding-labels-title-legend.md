title: Adding labels, title and legend to plots
--- |
  ### Title, xlabel & ylabel
  The plots without titles and X and Y axis labels do not convey the intended information very efficiently. Title can be added to the axes using [plt.title](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.title.html#matplotlib.pyplot.title). Use [plt.xlabel](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xlabel.html#matplotlib.pyplot.xlabel) and [plt.ylabel](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.ylabel.html#matplotlib.pyplot.ylabel) to set the labels for X and Y axis respectively. Lets load iris dataset and plot the sepal length vs petal length with circle markers and add title and labels.
---
type: live-code
id: 76688d75-94b0-4884-abc1-041fc2be54bc
code: |
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  iris = pd.read_csv('data/iris.csv')
  x = iris['sepal_length']
  y = iris['petal_length']

  plt.plot(x, y, 'o')
  plt.title('Iris Sepal length vs Petal length')
  plt.xlabel('Sepal Length')
  plt.ylabel('Petal Length')
  plt.show()
--- |
  ### Legend
  When we have multiple data plotted on the same axes, like we saw in the earlier section, it is important to add a legend to the plot to identify the plots. We use [matplotlib.pyplot.legend](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.legend.html#matplotlib.pyplot.legend) which places a legend on the axes based on the labels. Here is the iris plot we created in the earlier section with the appropriate labels.
---
type: live-code
id: 8ce6f2c3-65f8-4dc0-a0bf-669b5dcc8fea
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

  plt.plot(X_setosa, y_setosa, 'bo', label = 'setosa')
  plt.plot(X_versicolor, y_versicolor, 'ro', label = 'versicolor')
  plt.plot(X_virginica, y_virginica, 'go', label = 'virginica')

  plt.legend()
  plt.title('Iris Sepal length vs Petal length')
  plt.xlabel('Sepal Length')
  plt.ylabel('Petal Length')

  plt.show()
---
